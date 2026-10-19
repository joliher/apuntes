# 🇪🇸 ENS — Esquema Nacional de Seguridad

El **ENS** (*Esquema Nacional de Seguridad*), regulado por el **Real Decreto 311/2022**, establece los principios y requisitos mínimos de seguridad para la protección de la información y los servicios prestados por medios electrónicos.

Es de **obligado cumplimiento** para:
- **Administraciones Públicas (AAPP)** españolas en todos sus niveles (estatal, autonómico y local).
- **Entidades privadas** que presten servicios o proporcionen soluciones a las AAPP dentro del territorio español.

> 📝 **Nota:** Aunque no está vinculado oficialmente, el ENS puede considerarse una adaptación nacional muy cercana al espíritu de la Directiva **NIS 2** europea. Ver [nis2.md](nis2.md).

---

## 📐 Dimensiones de Seguridad: DICAT

El ENS amplía la tríada DIC del [ISO 27001](iso-27001.md) añadiendo dos dimensiones más, formando el modelo **DICAT**:

| Dimensión | Descripción | ISO 27001 | ENS |
| :--- | :--- | :---: | :---: |
| **D**isponibilidad | La información y los servicios deben estar accesibles cuando se necesiten | ✅ | ✅ |
| **I**ntegridad | La información no debe ser alterada de forma no autorizada | ✅ | ✅ |
| **C**onfidencialidad | Solo los usuarios autorizados deben poder acceder a la información | ✅ | ✅ |
| **A**utenticidad | Se debe poder verificar la identidad del origen de la información | ❌ | ✅ |
| **T**razabilidad | Debe existir un registro auditable de quién accede y qué hace con la información | ❌ | ✅ |

---

## ⚖️ Evaluación de Riesgos

Para cumplir con el ENS, una organización debe evaluar los riesgos de sus activos midiendo el **impacto potencial sobre cada una de las 5 dimensiones DICAT**. En función del resultado se determina:

- El **nivel de riesgo** del activo o sistema (Bajo, Medio o Alto).
- Las **medidas de seguridad obligatorias** a aplicar sobre ese sistema.

---

## 🗂️ Estructura de Medidas de Seguridad

El ENS organiza las medidas de seguridad en tres marcos:

| Marco | Código | Descripción |
| :--- | :---: | :--- |
| **Marco Organizativo** | `org` | Políticas de seguridad, normativa interna, roles y responsabilidades |
| **Marco Operacional** | `op` | Medidas técnicas y operativas del día a día (gestión de activos, accesos, backups…) |
| **Medidas de Protección** | `mp` | Controles específicos sobre tipos concretos de activos (comunicaciones, soportes, aplicaciones…) |

### Refuerzos

Sobre cada medida base se pueden aplicar **refuerzos** (`R01`, `R02`, etc.) que añaden requisitos adicionales en función del nivel de riesgo. A mayor nivel de riesgo del sistema, mayor obligación de aplicar refuerzos sobre las medidas base.

---

## ⏱️ Plazos de Corrección (Convención no oficial)

Al identificar y tratar vulnerabilidades o no conformidades, aunque no está estipulado de forma oficial en la norma, se suele utilizar la siguiente clasificación de urgencia:

| Prioridad | Plazo | Descripción |
| :--- | :---: | :--- |
| **Inmediata** | < 24 h | Vulnerabilidades críticas activas o en explotación |
| **Corto plazo** | 24 – 72 h | Riesgos altos sin explotación activa conocida |
| **Medio / Largo plazo** | > 72 h | Mejoras preventivas o riesgos de menor impacto |

---

## 📄 ITS — Instrucciones Técnicas de Seguridad

Las **ITS** son concreciones técnicas de los requisitos del ENS, aprobadas mediante **órdenes ministeriales**. Desarrollan aspectos específicos y prácticos del ENS tales como:

- Notificación de incidentes de seguridad.
- Realización de auditorías de seguridad.
- Requisitos para el uso de servicios en la nube.
- Interconexión de sistemas.

Su función es proporcionar una guía práctica y detallada para implementar los requisitos del ENS en escenarios concretos.
