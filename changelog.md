# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Inteligencia Artificial Aplicada: Guías para Decidir, Diseñar y Gobernar"**

---

### Versión 1.1 (Noviembre 2025)

**Motivo:** Transición a un marco de pensamiento estratégico completo. Integración de la arquitectura Transformer como límite fundacional y consolidación del enfoque GRC (Gobernanza, Riesgo y Cumplimiento) y Ciberseguridad.

#### Cambios Estratégicos y Fundacionales

* **Tesis Central:** El enfoque del libro se centró explícitamente en **GRC (Gobernanza, Riesgo y Cumplimiento)** y **Ciberseguridad**. Esta justificación fue integrada en el Prólogo, Conclusión, Guía 07 y el `README.md`.
* **Elevación Conceptual:** Se elevó el concepto de "Ingeniería de Prompts" a la disciplina de **"Ingeniería de Contexto"** (basado en investigaciones de Google 2025).
* **Fundamento de Límite (Transformer):** Se definió explícitamente que la arquitectura Transformer tiene dos límites estratégicos: el **Costo Cuadrático** y la **Amnesia Estática**.
* **Validación de Riesgo:** Integración del incidente de ciberespionaje de **Anthropic** (septiembre 2025) en la Guía 13 como la prueba empírica del **"Riesgo de la Agencia"** y la lealtad al *prompt*.

#### Gobernanza y Responsabilidad (GRC)

* **Arquitectura de Seguridad:**
    * **NUEVO:** Se añadió la capa **LOSA** (Layer of Safety & Alignment) como arquitectura para implementar los *guardrails* y el *Human-in-the-Loop* (Guía 07).
    * **Reestructuración Guía 07:** Se renombró la Parte 2 a **"El Nuevo Perímetro de Ciberseguridad de IA"**.
* **Marco Operacional (Sector Público - Política de IA):**
    * **Alcance:** Se añadió la subsección **"Definición de Sistema de IA"** para especificar las tecnologías cubiertas y excluir explícitamente tecnologías de bajo riesgo (ej. macros, dashboards de BI).
    * **Rendición de Cuentas:** Se incluyeron roles de gobernanza granular: **Dueño del Sistema de IA** y **Monitor de Cumplimiento**.
    * **Clasificación de Riesgo:** Se añadió el **Procedimiento de Screening (Triage)** obligatorio para clasificar todo nuevo caso de uso.
    * **Vigencia:** Se estableció un **ciclo de revisión anual** y disparadores para revisiones extraordinarias (incidente significativo, cambio regulatorio).

#### Consistencia, Estilo y Estructura

* **Nomenclatura Unificada:** Se eliminó el formato numérico genérico (#### 1.) y se unificó la nomenclatura de los encabezados (####) al estilo semántico (ej. `#### Parte X:`, `#### Solución X:`).
* **Estilo CSS:** Se forzó el ajuste de línea (`white-space: pre-wrap`) en los bloques de código para eliminar el scroll horizontal. Se corrigió el error de aumento de fuente en iPhone al rotar la pantalla.
* **Pies de Página:** Se reemplazaron todos los pies de página por un bloque `<div>` HTML/CSS para asegurar una alineación uniforme.

#### Bloques de Código y Agentes

* **Unificación de Acciones:** Todas las acciones de máquina (ciclos ReAct) se estandarizaron al formato **`yaml`**, reemplazando formatos anteriores (`json`, viñetas).
* **Etiquetado Visual de Roles:** Se implementó un sistema de etiquetado con emojis para diferenciar visualmente los roles en los ciclos de agente.

#### Actualizaciones de Contenido Detallado

| Guía / Anexo | Cambio Principal | Detalle / Conceptos Añadidos |
| :--- | :--- | :--- |
| **Guía 02** | Ingeniería de Contexto y Memoria | Detalle de límites estructurales (**Costo Cuadrático**, **Amnesia Estática**). Uso de las metáforas técnicas **"Bibliotecario vs. Asistente Personal"**. Detalle de Gestión de Memoria como flujo **ETL**. |
| **Guía 13** | Perspectivas y Futuro | Se añadió **"Nested Learning"** como tendencia futura. Riesgos añadidos: **"Lealtad Agéntica"** y **"Divulgación"** (Riedl & Desai, 2025). |
| **Guía 07** | Gobernanza | Se integró el framework **PPP** (Productividad, Proactividad y Personalización) como la Parte 3. |
| **Anexo 06** | Glosario Unificado | Se añadieron más de 30 términos, incluyendo: **Ingeniería de Contexto**, **Amnesia Estática**, **Costo Cuadrático**, **GRC**, **Divulgación** y **Lealtad Agéntica**. |
| **Anexo 07** | Bibliografía | Se integraron 4 referencias fundamentales de 2024-2025 (Anthropic, SAIF, Context Engineering, Nested Learning). |

---

### Versión 1.0 (Base Inicial)

**Motivo:** Publicación inicial del borrador de contenidos.

* **Publicación:** Se movió la publicación del libro a un dominio personalizado, consolidando la presencia en `iaa.jccarvajal.com`.
* **Contenido:** Cubría los Principios, la Filosofía central (**Delegar, No Abdicar**) y la gestión de Riesgos específicos del sector público (ej. Bucles de Costos, Basura Elocuente).
* **Revisión:** Se integró la táctica de **"Revisión IA-revisa-IA"** en la Guía 08 (Evaluación).