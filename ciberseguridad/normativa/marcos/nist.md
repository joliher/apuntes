# 🇺🇸 NIST — National Institute of Standards and Technology

El **NIST** (*National Institute of Standards and Technology*) es un organismo gubernamental **estadounidense** dependiente del Departamento de Comercio de EE.UU. Publica marcos normativos y guías técnicas de ciberseguridad que, aunque son **de origen y ámbito nacional estadounidense**, se utilizan como referencia a nivel internacional por su rigor y detalle técnico.

> ⚠️ **Nota sobre el ámbito:** El NIST no es un organismo internacional (como ISO) ni europeo (como ENISA). Sus publicaciones son técnicamente de aplicación en EE.UU., aunque su adopción como referencia es global.

---

## 📋 Publicaciones Principales

### NIST CSF 2.0 — Cybersecurity Framework

El **CSF** (*Cybersecurity Framework*) es el marco de gestión del riesgo de ciberseguridad más conocido del NIST. La versión 2.0 (2024) organiza las actividades de ciberseguridad en **6 funciones**:

```mermaid
flowchart LR
    G["🏛️ Gobernar\n(Govern)"] --> I["🔍 Identificar\n(Identify)"]
    I --> P["🛡️ Proteger\n(Protect)"]
    P --> D["📡 Detectar\n(Detect)"]
    D --> R["🚨 Responder\n(Respond)"]
    R --> RE["🔄 Recuperar\n(Recover)"]
    RE --> G
```

| Función | Descripción |
| :--- | :--- |
| **Gobernar** *(nuevo en 2.0)* | Establecer la estrategia, políticas y responsabilidades de ciberseguridad de la organización |
| **Identificar** | Comprender el contexto de la organización, sus activos y los riesgos asociados |
| **Proteger** | Implementar salvaguardas para limitar el impacto de un posible incidente |
| **Detectar** | Identificar la ocurrencia de eventos de ciberseguridad |
| **Responder** | Actuar ante un incidente de ciberseguridad detectado |
| **Recuperar** | Restablecer las capacidades y servicios afectados por un incidente |

---

### SP 800-53 — Security and Privacy Controls

El **NIST SP 800-53** es un catálogo exhaustivo de **controles de seguridad y privacidad** para sistemas de información. Está orientado principalmente a agencias federales estadounidenses, pero se usa ampliamente como referencia en el sector privado y en otros países.

Proporciona cientos de controles organizados en familias temáticas (control de acceso, auditoría, gestión de configuración, respuesta a incidentes, etc.).

---

### SP 800-171 — Protecting CUI

El **NIST SP 800-171** establece los requisitos de seguridad para proteger **CUI** (*Controlled Unclassified Information*, información no clasificada pero sensible) en sistemas de información no federales, es decir, en empresas privadas que trabajan con el gobierno de EE.UU.

---

## 📌 Obligatoriedad

| Contexto | Obligatoriedad |
| :--- | :--- |
| Agencias federales de EE.UU. | ✅ Obligatorio (SP 800-53, CSF en algunos casos) |
| Contratistas del gobierno de EE.UU. | ✅ Obligatorio (SP 800-171, CMMC) |
| Sector privado (EE.UU. y resto del mundo) | ❌ Voluntario (usado como referencia) |
