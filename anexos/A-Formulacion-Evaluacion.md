## Anexo A: Formulación y Viabilidad de Proyectos

Subtítulo: Estructura base para Casos de Seguridad (Safety Cases)

### Introducción: El Primer Filtro de Gobernanza

Antes de prototipar, debemos validar. Este documento es la herramienta de **"Screening" (Triage)** mencionada en la **Guía 09 (Gobernanza)**.

Su propósito es evitar el "solucionismo tecnológico" y asegurar que solo los proyectos que son **técnicamente viables** (datos enlazables), **estratégicamente valiosos** (transforman una actividad real) y **éticamente robustos** pasen a desarrollo.

> **Nota Técnica:** Al completar este documento, estás construyendo la evidencia estructurada (Safety Case) requerida para futuras auditorías de seguridad. Si descubres aquí que el proyecto no es viable, **descartarlo es un éxito**.

---

### Sección 1: Definición Estratégica (La Transformación)

> **Contexto:** No basta con tener un "dolor". Debemos identificar qué *actividad humana* específica va a cambiar. Si no puedes describir el "Antes" y el "Después" operativo, no tienes un proyecto, tienes solo una idea.

**1. El Dolor del Negocio:**
¿Qué problema raíz estamos resolviendo? Describa la carencia y su costo actual, no la solución.
* **Respuesta:** `[Describe el problema raíz y su impacto económico/operativo]`

**2. La Actividad a Transformar (Flujo Antes/Después):**
Describa la tarea específica tal como se hace HOY y cómo se propone que la haga la IA.
* **Antes (Manual/Actual):** `[Ej: Un analista descarga 500 contratos y lee uno por uno buscando cláusulas de riesgo. Tarda 40 horas.]`
* **Después (Con IA):** `[Ej: La IA pre-clasifica los 500 contratos en minutos. El analista solo revisa los 15 marcados como "Alto Riesgo". Tarda 2 horas.]`

**3. Tipo de Valor (Según Guía 13):**
¿Buscamos hacer lo mismo más barato (**Eficiencia/S1**) o hacer algo nuevo que antes era imposible (**Innovación/S2**)?
* **Selección:** `[ Eficiencia / Innovación ]`

---

### Sección 2: Viabilidad Técnica de Datos (El Combustible)

> **Contexto:** El 80% de los proyectos fallan aquí. No basta con "tener datos". Necesitamos saber si esos datos pueden "hablar" entre sí (Identificador Único) y si tienen el detalle suficiente (Granularidad).

**1. Disponibilidad y Enlace (El "Killer" del Proyecto):**
¿Tenemos acceso a los datos? Y crucialmente: **¿Tienen un identificador único (ej: RUT, N° Ticket, SKU) que permita cruzar distintas fuentes?** Sin ID, no hay sistema.
* **Estado:** `[ No disponible / Silos desconectados (Sin ID) / Enlazable y Limpio ]`

**2. Granularidad y Frecuencia:**
¿El dato tiene el nivel de detalle necesario para la decisión? (Ej: Si quieres predecir ventas diarias, ¿tienes datos diarios o solo resúmenes mensuales?).
* **Evaluación:** `[ Granularidad Insuficiente / Granularidad Adecuada ]`

**3. Complejidad Cognitiva (Riesgo S1/S2):**
* **Sistema 1 (Piloto Automático):** Tareas rápidas, patrones, clasificación. -> *Riesgo Bajo.*
* **Sistema 2 (Piloto Manual):** Razonamiento profundo, juicio moral o estratégico. -> *Riesgo Alto (Requiere Humano-en-el-Bucle).*
* **Clasificación:** `[ Sistema 1 / Sistema 2 ]`

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

**1. Métrica de Calidad (El "Golden Set"):**
¿Contra qué estándar de verdad compararemos a la IA? (Ej: "Debe coincidir con la clasificación del auditor senior en el 90% de los casos").
* **KPI Objetivo:** `[Definir métrica objetiva y umbral]`

**2. Estimación de Costo (Tokenomics):**
¿Cuál es el costo estimado de operación mensual vs. el ahorro proyectado?
* **Estimación:** `[$ Costo vs. $ Ahorro]`

---

### Sección 5: Ciclo de Vida y Salida (El "Final")

> **Contexto:** Todo sistema de software se convierte eventualmente en deuda técnica. La responsabilidad final de GRC es saber cómo apagar el sistema *antes* de encenderlo. Debemos evitar crear "Agentes Zombis" (que operan sin propósito) y prevenir la "Atrofia Cognitiva" (que el equipo humano olvide cómo hacer el trabajo).

**1. Plan de Retiro (Decommissioning):**
¿Cómo se apaga el sistema y se borran los datos vectorizados (RAG) cuando el proyecto termine?
* **Plan:** `[Protocolo de borrado seguro]`

**2. Resiliencia (Deuda Cognitiva):**
Si el sistema falla, ¿mantenemos la capacidad humana de operar manualmente (Actividad "Antes")?
* **Mitigación:** `[Ej: Simulacro manual trimestral]`

---

### Dictamen Final (Triage)

**Decisión del Comité de Gobernanza / Sponsor:**
Basado en la evidencia de este Canvas, el proyecto se califica como:

* [ ] **VIABLE (APROBADO):** El valor es claro, los riesgos están mitigados y los datos están listos. -> *Pasa a Prototipado (Guía 08).*
* [ ] **CONDICIONAL:** Requiere resolver la brecha de datos o ética antes de avanzar. -> *Volver a Formulación.*
* [ ] **NO VIABLE (RECHAZADO):** El riesgo supera al valor o existe una alternativa No-IA mejor. -> *Fin del proceso.*

**Firma del Responsable:** ___________________________

**Fecha del Dictamen:** ___________________________

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="../conclusion.html">« Conclusión</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
  <div>
    <a href="./B-Politica-Institucional.html">Anexo B »</a>
  </div>
</div>