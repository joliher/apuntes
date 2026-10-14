# 🦈 Wireshark — Análisis de Tráfico para Blue Team

**Wireshark** es un analizador de tráfico de red (*packet sniffer*) de código abierto ampliamente utilizado en tareas de Blue Team para el análisis forense de capturas de red (archivos `.pcap`/`.pcapng`), detección de intrusiones y análisis de comportamiento malicioso.

---

## 🗂️ Herramientas de Estadística

### Statistics → Conversations
`Statistics` → `Conversations` es una de las vistas más útiles para obtener una visión global rápida de una captura. Muestra todas las **direcciones IP únicas** involucradas y el tráfico intercambiado entre cada par, agrupado por protocolo (Ethernet, IPv4, IPv6, TCP, UDP).

Permite identificar de un vistazo:
- Equipos que generan un volumen de tráfico anormalmente alto.
- Comunicaciones con IPs externas desconocidas (posibles **C2**).
- Múltiples conexiones en poco tiempo a diferentes puertos (posible **escaneo de puertos**).

---

## 🔍 Filtros de Análisis

### Escaneo de Puertos (TCP Flags)

El análisis de los flags TCP permite identificar comportamientos típicos de escaneo de puertos:

| Filtro | Interpretación |
| :--- | :--- |
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Paquete SYN sin ACK: intento de inicio de conexión. Muchos en poco tiempo = **indicio de escaneo de puertos** |
| `tcp.flags.syn == 1 && tcp.flags.ack == 1` | SYN-ACK: el servidor ha respondido. Indica que el **puerto está abierto** |
| `tcp.flags.reset == 1` | RST: el servidor ha rechazado la conexión. Indica que el **puerto está cerrado o filtrado** |

> 💡 **Patrón de escaneo típico (ej. Nmap SYN scan):** se observarán muchos paquetes SYN hacia puertos distintos del mismo host, con respuestas SYN-ACK en los abiertos y RST en los cerrados.

---

### HTTP / Web

| Filtro | Uso |
| :--- | :--- |
| `http.request.method == "POST"` | Filtrar peticiones POST. Útil para detectar envío de formularios, credenciales o payloads maliciosos |
| `http.authbasic` | Credenciales de **HTTP Basic Auth** (usuario:contraseña codificado en Base64). Son **decodificables en texto plano** → credenciales comprometidas visibles directamente |

> ⚠️ **HTTP Basic Auth:** el mecanismo codifica las credenciales en Base64 (no las cifra). Base64 es trivialmente reversible, por lo que cualquiera con acceso a la captura puede recuperar usuario y contraseña en texto plano.

---

### HTTPS / TLS

| Filtro | Uso |
| :--- | :--- |
| `tls contains "cadena"` | Busca una cadena de texto en el tráfico TLS. Útil para identificar dominios en el SNI (*Server Name Indication*) del TLS Handshake, visible incluso en tráfico cifrado |

> 📝 **Nota:** `https` como prefijo de filtro está **deprecado** en versiones modernas de Wireshark. Usar `tls` en su lugar. Dado que el contenido de HTTPS va cifrado, este filtro solo detectará strings visibles en las partes no cifradas del handshake (como el SNI).

---

### Bases de Datos

| Filtro | Uso |
| :--- | :--- |
| `mysql.login.request` | Peticiones de inicio de sesión contra un servidor MySQL. Útil para detectar intentos de autenticación o ataques de fuerza bruta sobre bases de datos |

---

### Windows / Active Directory / SMB (Samba)

| Filtro | Uso |
| :--- | :--- |
| `smb \|\| smb2` | Todos los paquetes del protocolo SMB (v1) y SMB2/3 (Samba). Útil para detectar movimiento lateral, uso de **PsExec** o acceso a recursos compartidos |
| `ntlmssp.challenge.target_name` | Mensajes de **NTLM Challenge** en autenticación Samba. Suelen revelar el **nombre del equipo o dominio** del servidor, útil para mapear la red comprometida |

---

## 🎯 Tipos de Ataques Detectables

### C2 — Command & Control
Un servidor **C2** (*Command and Control*) es la infraestructura desde la que el atacante envía órdenes y recibe datos del malware instalado en los equipos comprometidos. En Wireshark, se puede identificar por:
- Conexiones periódicas y regulares a una IP externa desconocida (*beaconing*).
- Tráfico saliente cifrado hacia IPs sin hostname o dominios recientes/sospechosos.
- Uso de protocolos inusuales para exfiltrar datos (DNS tunneling, ICMP, etc.).

### XXE — XML External Entity Injection
Vulnerabilidad en parsers XML que permite a un atacante leer archivos del servidor o realizar SSRF. Se detecta en Wireshark analizando **peticiones HTTP POST** con cuerpos XML que referencian entidades externas:
```xml
<?xml version="1.0"?>
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<foo>&xxe;</foo>
```
Filtro útil: `http.request.method == "POST"` combinado con inspección del cuerpo del paquete.

### PsExec
Herramienta legítima de Sysinternals frecuentemente utilizada por atacantes para **ejecutar comandos remotamente** en otros equipos de la red (movimiento lateral). Se manifiesta como tráfico **SMB** con el pipe nombrado `\PSEXESVC`.  
Filtro útil: `smb || smb2` buscando referencias a `PSEXESVC` en los paquetes.
