# 📚 Repositorio de Apuntes de Tecnología

¡Bienvenido/a a mi repositorio personal de apuntes y notas sobre tecnología, desarrollo de software, redes y arquitectura!

Este repositorio está organizado por **dominios tecnológicos** para facilitar la navegación y el aprendizaje estructurado.

---

## 🗂️ Estructura del Repositorio

La arquitectura del repositorio sigue una jerarquía por dominios generales y subtemas específicos, acompañada de una carpeta `assets/` en espejo para diagramas e imágenes:

```text
apuntes/
├── assets/                          # Imágenes, esquemas y diagramas (estructura espejo)
│   ├── ciberseguridad/
│   │   ├── blue-team/
│   │   └── normativa/
│   │       └── marcos/
│   ├── linux/
│   │   ├── contenedores/
│   │   └── procesos/
│   └── web-y-redes/
│       └── http/
├── ciberseguridad/
│   ├── blue-team/
│   │   └── wireshark.md
│   └── normativa/
│       ├── marcos-regulatorios.md   # Índice y tabla comparativa de marcos
│       └── marcos/
│           ├── iso-27001.md
│           ├── ens.md
│           ├── rgpd.md
│           ├── nis2.md
│           ├── cis.md
│           ├── nist.md
│           └── soc-ii.md
├── linux/
│   ├── contenedores/
│   │   └── namespaces.md
│   └── procesos/
│       └── cgroups.md
├── web-y-redes/
│   └── http/
│       └── tls-ssl.md
└── README.md
```

---

## 🗺️ Índice de Contenidos

| Categoría / Dominio | Tema / Subtema | Apunte | Descripción |
| :--- | :--- | :--- | :--- |
| 🐧 **Linux** | **Contenedores** | [Namespaces](linux/contenedores/namespaces.md) | Network namespaces, tipos, aislamiento y base de los contenedores. |
| 🐧 **Linux** | **Procesos** | [cgroups](linux/procesos/cgroups.md) | Control Groups: limitación de recursos para procesos y contenedores. |
| 🔒 **Ciberseguridad** | **Blue Team** | [Wireshark](ciberseguridad/blue-team/wireshark.md) | Filtros de análisis, detección de escaneos, C2, PsExec, XXE y SMB. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [Índice de Marcos Regulatorios](ciberseguridad/normativa/marcos-regulatorios.md) | Tabla comparativa de todos los marcos y enlace a cada uno. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [ISO 27001 y SGSI](ciberseguridad/normativa/marcos/iso-27001.md) | Norma internacional, SGSI, cláusulas 4–10 y ciclo PDCA. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [ENS](ciberseguridad/normativa/marcos/ens.md) | Esquema Nacional de Seguridad, DICAT, medidas y refuerzos. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [RGPD, LOPDGDD y AEPD](ciberseguridad/normativa/marcos/rgpd.md) | Protección de datos personales y derechos ARCO+. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [NIS 2](ciberseguridad/normativa/marcos/nis2.md) | Directiva europea para infraestructuras y servicios críticos. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [CIS Controls y Benchmarks](ciberseguridad/normativa/marcos/cis.md) | Buenas prácticas técnicas y guías de bastionado. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [NIST](ciberseguridad/normativa/marcos/nist.md) | CSF 2.0, SP 800-53 y SP 800-171. |
| 🔒 **Ciberseguridad** | **Normativas y Marcos** | [SOC II](ciberseguridad/normativa/marcos/soc-ii.md) | Informe de auditoría para proveedores de servicios tecnológicos. |
| 🌐 **Web y Redes** | **HTTP & Seguridad** | [TLS / SSL](web-y-redes/http/tls-ssl.md) | Cifrado, Handshake TLS, certificados y TLS Inspection. |



---

## 📝 Convenciones de Estilo

- **Formato:** Todo el contenido está escrito en Markdown estándar.
- **Diagramas:** Se utilizan diagramas de [Mermaid.js](https://mermaid.js.org/) para explicaciones visuales interactiva (Handshakes, arquitecturas, flujos).
- **Nomenclatura:** Archivos y carpetas nombrados en `kebab-case` (`tls-ssl.md`, `cookies-y-sesiones.md`).
