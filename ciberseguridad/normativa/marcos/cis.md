# 🛡️ CIS — Center for Internet Security

El **CIS** (*Center for Internet Security*) es una organización **sin ánimo de lucro** de referencia internacional que publica recursos prácticos para el bastionado técnico de sistemas. Sus dos publicaciones más relevantes son los **CIS Controls** y los **CIS Benchmarks**.

---

## 📋 CIS Controls

Los **CIS Controls** son un listado priorizado de **buenas prácticas técnicas** organizadas para ayudar a las organizaciones a proteger sus sistemas de las amenazas más comunes y frecuentes.

Se organizan en **Grupos de Implementación (IG)** según la madurez, tamaño y capacidad de recursos de la organización:

| Grupo | Perfil objetivo | Descripción |
| :---: | :--- | :--- |
| **IG1** | Pequeñas organizaciones / recursos limitados | Controles básicos imprescindibles. Representan la **higiene cibernética esencial** mínima recomendada para cualquier organización |
| **IG2** | Organizaciones medianas | IG1 + controles adicionales para gestionar riesgos más específicos y entornos más complejos |
| **IG3** | Grandes organizaciones / sectores críticos | IG1 + IG2 + controles avanzados diseñados para hacer frente a amenazas sofisticadas y persistentes (APT) |

> 💡 Cada grupo es acumulativo: IG2 incluye todo lo de IG1, e IG3 incluye todo lo de IG1 e IG2.

### Áreas que cubren los CIS Controls (versión 8)

Los 18 controles se agrupan en áreas como:
- Inventario y control de activos (hardware y software).
- Gestión de configuraciones seguras.
- Gestión de accesos y privilegios.
- Auditoría y monitorización de logs.
- Protección de datos y correo electrónico.
- Gestión de vulnerabilidades y respuesta a incidentes.

---

## 📖 CIS Benchmarks

Los **CIS Benchmarks** son guías prácticas y detalladas para **bastionar configuraciones de sistemas concretos**. Proporcionan instrucciones paso a paso con los valores de configuración recomendados.

Existen benchmarks para multitud de tecnologías:

| Categoría | Ejemplos |
| :--- | :--- |
| **Sistemas Operativos** | Windows Server, Ubuntu, Debian, RHEL, macOS |
| **Servidores Web** | Apache HTTP Server, Nginx, IIS |
| **Bases de Datos** | MySQL, PostgreSQL, Microsoft SQL Server, Oracle |
| **Contenedores y Cloud** | Docker, Kubernetes, AWS, Azure, GCP |
| **Navegadores** | Chrome, Firefox |

Cada benchmark tiene dos niveles de perfil:

| Nivel | Descripción |
| :---: | :--- |
| **Level 1** | Configuraciones básicas de seguridad con mínimo impacto en el funcionamiento del sistema |
| **Level 2** | Configuraciones más restrictivas para entornos de alta seguridad; puede requerir ajustes según el caso de uso |
