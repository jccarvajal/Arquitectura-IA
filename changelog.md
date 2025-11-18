# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Inteligencia Artificial Aplicada: Guías para Decidir, Diseñar y Gobernar"**

---

### Versión 1.1 (Noviembre 2025)

**Motivo:** Transición a un marco de pensamiento estratégico completo. Integración de la arquitectura Transformer como límite fundacional, consolidación del enfoque GRC (Gobernanza, Riesgo y Cumplimiento) y refinamiento de la consistencia interna.

#### Cambios Estratégicos y Fundacionales

* **Tesis Central:** El enfoque del libro se centró explícitamente en **GRC (Gobernanza, Riesgo y Cumplimiento)** y **Ciberseguridad**. Esta justificación fue integrada en el Prólogo, Conclusión, Guía 07 y el `README.md`.
* **Elevación Conceptual:** Se elevó el concepto de "Ingeniería de Prompts" a la disciplina de **"Ingeniería de Contexto"** (basado en investigaciones de Google 2025).
* **Fundamento de Límite (Transformer):** Se definió explícitamente que la arquitectura Transformer tiene dos límites estratégicos: el **Costo Cuadrático** y la **Amnesia Estática**.
* **Validación de Riesgo:** Integración del incidente de ciberespionaje de **Anthropic** (septiembre 2025) en la **Guía 07 (Gobernanza)**, como el caso de estudio clave para la **Inyección de Prompts**, y en la **Guía 13 (Perspectivas)** como la prueba empírica del **"Riesgo de la Agencia"** y la lealtad al *prompt*.

#### Gobernanza y Responsabilidad (GRC)

* **Arquitectura de Seguridad:**
    * **NUEVO:** Se añadió la capa **LOSA** (Layer of Safety & Alignment) como arquitectura para implementar los *guardrails* y el *Human-in-the-Loop* (Guía 07).
    * **Reestructuración Guía 07:** Se renombró la Parte 2 a **"El Nuevo Perímetro de Ciberseguridad de IA"** y se unificó el rol de liderazgo bajo el término **"Gobernador"** para eliminar inconsistencias.
* **Marco Operacional (Sector Público - Política de IA):**
    * **Alcance:** Se añadió la subsección **"Definición de Sistema de IA"** para especificar las tecnologías cubiertas y excluir explícitamente tecnologías de bajo riesgo.
    * **Rendición de Cuentas:** Se incluyeron roles de gobernanza granular: **Dueño del Sistema de IA** y **Monitor de Cumplimiento**.
    * **Clasificación de Riesgo:** Se añadió el **Procedimiento de Screening (Triage)** obligatorio.

#### Consistencia, Estilo y Estructura

* **Nomenclatura Unificada:** Se eliminó el formato numérico genérico y se unificó la nomenclatura de los encabezados.
* **Estilo CSS:** Se forzó el ajuste de línea (`white-space: pre-wrap`) en los bloques de código para eliminar el scroll horizontal en móviles.
* **Tablas y Matrices:** Se corrigió el formato de la **Matriz 3.2 (Anexo 03)** completando los 4 cuadrantes y se optimizó la tabla del **Anexo 05** eliminando columnas redundantes.

#### Bloques de Código y Agentes

* **Unificación de Acciones:** Todas las acciones de máquina (ciclos ReAct) se estandarizaron al formato **`yaml`**.
* **Etiquetado Visual de Roles:** Se implementó un sistema de etiquetado con emojis (`👤`, `💭`, `⚙️`, `💬`) consistente en las Guías 02 y 04 para diferenciar visualmente los roles en los ciclos de agente.
* **Lógica ReAct:** Se estandarizó la separación entre **Observación** (dato) y **Reflexión** (pensamiento) en los ejemplos prácticos.

#### Actualizaciones de Contenido Detallado

| Guía / Anexo | Cambio Principal | Detalle / Conceptos Añadidos |
| :--- | :--- | :--- |
| **Guía 02** | Reestructuración Didáctica | Se reorganizó el flujo (Problema -> Causa -> Criterio -> Solución), se añadió la sección **"Criterio del Arquitecto"** y se eliminó la tabla redundante. |
| **Guía 04** | Coherencia ReAct | Se alineó el formato del ciclo ReAct y los emojis con el estándar de la Guía 02. |
| **Guía 10** | Fundamentos S1/S2 | Se añadió la atribución explícita a **Daniel Kahneman** y se eliminó la referencia confusa a la "Lista de Fitts". |
| **Guía 13** | Perspectivas y Futuro | Se añadió **"Nested Learning"** y **"Web Agéntica"** (Agentic Web) como tendencias futuras. |
| **Anexo 03** | Plantillas | Se explicitaron las siglas **"CRF-R"** (Contexto, Rol, Formato, Restricciones) en la Plantilla 1.1 y se corrigió el formato de código. |
| **Anexo 06** | Glosario Unificado | Se añadieron más de 30 términos, incluyendo: **Ingeniería de Contexto**, **Amnesia Estática**, **Web Agéntica**, **GRC** y **Lealtad Agéntica**. |

---

### Versión 1.0 (Base Inicial)

**Motivo:** Publicación inicial del borrador de contenidos.

* **Publicación:** Se movió la publicación del libro a un dominio personalizado, consolidando la presencia en `iaa.jccarvajal.com`.
* **Contenido:** Cubría los Principios, la Filosofía central (**Delegar, No Abdicar**) y la gestión de Riesgos específicos del sector público.
* **Revisión:** Se integró la táctica de **"Revisión IA-revisa-IA"** en la Guía 08 (Evaluación).
