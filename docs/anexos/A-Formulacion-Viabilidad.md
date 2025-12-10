## Anexo A: Formulación y Viabilidad de Proyectos

Subtítulo: Estructura base para Casos de Seguridad (Safety Cases)

### Introducción: El Primer Filtro de Gobernanza

Antes de prototipar, debemos validar. Este documento es la herramienta de **"Screening" (Triage)** mencionada en la **Guía 09 (Gobernanza)**.

Su propósito es evitar el "solucionismo tecnológico" y asegurar que solo los proyectos que son **técnicamente viables** (datos enlazables), **estratégicamente valiosos** (transforman una actividad real) y **éticamente robustos** pasen a desarrollo.

> **Nota Técnica:** Al completar este documento, estás construyendo la evidencia estructurada (Safety Case) requerida para futuras auditorías de seguridad. Si descubres aquí que el proyecto no es viable, **descartarlo es un éxito**.

---

### Sección 1: Definición Estratégica (La Transformación)

> **Contexto:** No basta con tener un "dolor". Debemos identificar qué *actividad humana* específica va a cambiar. Si no puedes describir el "Antes" y el "Después" operativo, no tienes un proyecto, tienes solo una idea.

| Criterio Estratégico | Pregunta Clave | Respuesta / Placeholder | Referencia |
| :--- | :--- | :--- | :--- |
| **1. El Dolor (Why)** | ¿Qué problema raíz resolvemos y cuál es el costo de no hacer nada? | `[Describe el problema y su impacto económico]` | Guía 01 |
| **2. La Transformación (What)** | Flujo Operativo: ANTES (Humano) vs DESPUÉS (IA + Humano). | *Antes:* `[Ej: Lee 100 contratos]`<br>*Después:* `[Ej: IA filtra, Humano valida 5]` | Guía 02 |
| **3. La Zona ROI (Value)** | ¿Dónde cae en el Mapa de Inversión? (Verde, Amarillo, Rojo, Azul). | `[Ej: Zona Verde - Eficiencia Inmediata]` | Guía 12 |
| **4. Los Datos (RAG)** | ¿Qué conocimiento necesita leer el agente y cuán sensible es? | `[Ej: Manuales técnicos (Público) + Emails (Confidencial)]` | Guía 07/11 |
| **5. La Gobernanza (LOSA)** | ¿Qué controles (human-in-the-loop) evitarán la atrofia o el error? | `[Ej: Auditoría aleatoria del 10% de las respuestas]` | Guía 09/15 |

---

### Sección 2: Viabilidad Técnica y de Datos (El Combustible)

> **Contexto:** El 80% de los proyectos fallan aquí. No basta con "tener datos". Necesitamos saber si esos datos pueden "hablar" entre sí (Identificador Único) y si tienen el detalle suficiente (Granularidad).

| Criterio Técnico | Pregunta Clave | Diagnóstico Técnico (Placeholder) | Referencia |
| :--- | :--- | :--- | :--- |
| **Disponibilidad y Enlace** | ¿Tenemos acceso y, crucialmente, ¿tienen un **identificador único** (ID) para cruzar distintas fuentes? | `[No enlazable / Conectable y Limpio]` | Guía 04 |
| **Granularidad** | ¿El dato tiene el nivel de detalle necesario para la decisión? | `[Granularidad Insuficiente / Granularidad Adecuada]` | Guía 04 |
| **Complejidad Cognitiva** | ¿Es tarea de S1 (Patrón) o S2 (Juicio/Riesgo Alto)? | `[Sistema 1 / Sistema 2]` | Guía 15 |

---

### Sección 3: Checklist de Validación Ética (El "Safety Case")

> **Contexto:** Este es el núcleo de **GRC**. Validamos la **Proporcionalidad** y la **Licencia Social**.

| Dimensión | Pregunta de Validación ("Go / No-Go") | Referencia | Estado |
| :--- | :--- | :--- | :--- |
| **1. Proporcionalidad** | ¿Es la IA el medio adecuado? *¿Existe una alternativa No-IA (Excel, Regla simple) más barata y efectiva?* | **Guía 12** | `[ ]` |
| **2. Licencia Social** | ¿Aprobarían los afectados (ciudadanos/empleados) este uso si apareciera en la prensa mañana? | **Guía 15** | `[ ]` |
| **3. Protección de Datos** | ¿Hay datos personales? Si es así, ¿tenemos base legal para tratarlos y arquitectura segura (LOSA)? | **Guía 09** | `[ ]` |
| **4. Transparencia** | ¿Es explicable la decisión? ¿Podemos trazar *por qué* actuó así (logs de razonamiento) ante una auditoría? | **Guía 09** | `[ ]` |
| **5. Sesgos** | ¿Los datos históricos ("Antes") contienen prejuicios que la IA podría aprender y amplificar? | **Guía 04** | `[ ]` |
| **6. Responsabilidad** | ¿Existe un "Dueño del Sistema" humano designado que asuma la responsabilidad final del resultado? | **Anexo B** | `[ ]` |

---

### Sección 4: Definición de Éxito (El "Golden Set")

> **Contexto:** Si no puedes medirlo, no puedes gobernarlo. Define contra qué vamos a comparar.

| Métrica | Definición / Pregunta Clave | Umbral / Estimación | Referencia |
| :--- | :--- | :--- | :--- |
| **Calidad / Golden Set** | ¿Contra qué estándar de verdad (ej. humano o proceso anterior) compararemos a la IA? | `[KPI Objetivo y Umbral]` | Guía 10 |
| **Costo (Tokenomics)** | ¿Cuál es el costo estimado de operación mensual vs. el ahorro proyectado? | `[$ Costo vs. $ Ahorro]` | Guía 12 |

---

### Sección 5: Ciclo de Vida y Salida (El "Final")

> **Contexto:** Todo sistema de software se convierte eventualmente en deuda técnica. La responsabilidad final de GRC es saber cómo apagar el sistema *antes* de encenderlo. Debemos evitar crear "Agentes Zombis" y prevenir la "Atrofia Cognitiva".

| Criterio | Pregunta Clave | Plan de Mitigación / Protocolo | Referencia |
| :--- | :--- | :--- | :--- |
| **Plan de Retiro** | ¿Cómo se apaga el sistema y se borran los datos vectorizados (RAG) cuando el proyecto termine? | `[Protocolo de borrado seguro]` | Guía 09 |
| **Resiliencia** | Si el sistema falla, ¿mantenemos la capacidad humana de operar manualmente (Actividad "Antes")? | `[Simulacro manual trimestral]` | Guía 15 |

---

### Dictamen Final (Triage)

**Decisión del Comité de Gobernanza / Sponsor:**
Basado en la evidencia de este Canvas, el proyecto se califica como:

* `[ ]` **VIABLE (APROBADO):** El valor es claro, los riesgos están mitigados y los datos están listos. -> *Pasa a Prototipado.*
* `[ ]` **CONDICIONAL:** Requiere resolver la brecha de datos o ética antes de avanzar. -> *Volver a Formulación.*
* `[ ]` **NO VIABLE (RECHAZADO):** El riesgo supera al valor o existe una alternativa No-IA mejor. -> *Fin del proceso.*

**Firma del Responsable:** ______________________________

**Fecha del Dictamen:** ______________________________

**Firma del Responsable:** <span style="border-bottom: 1px solid #000; display: inline-block; width: 300px;"></span>

**Fecha del Dictamen:** <span style="border-bottom: 1px solid #000; display: inline-block; width: 150px;"></span>
