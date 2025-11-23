### Anexo A: Formulación y Evaluación de Proyectos de IA

Subtítulo: El Canvas de Viabilidad: De la Idea al Proyecto

#### Introducción: El Primer Filtro de Gobernanza

Antes de prototipar, debemos validar. Este anexo es la herramienta de **"Screening" (Triage)** mencionada en la **Guía 07 (Gobernanza)**.

Su propósito es evitar el "solucionismo tecnológico" (usar IA para problemas que no lo requieren) y asegurar que solo los proyectos que son **técnicamente viables**, **estratégicamente valiosos** y **éticamente robustos** pasen a la fase de desarrollo.

Este documento debe ser completado por el "Dueño del Proyecto" y visado por el "Comité de Gobernanza" antes de escribir la primera línea de código.

> **Instrucción de Uso:** Este documento no es un trámite. Es un mecanismo de defensa. Si al completarlo descubres que el proyecto no es viable, has ahorrado tiempo y presupuesto. **Descartar una mala idea aquí es un éxito.**

---

#### Sección 1: Definición Estratégica (El "Por Qué")

> **Contexto para el Arquitecto:**

> El error N°1 es empezar por la solución ("Queremos un chatbot") en lugar del problema. Aquí aplicamos el principio de **Proporcionalidad**. La IA es costosa y probabilística (a veces falla). Si el problema se puede resolver con software tradicional (determinista y barato), **no uses IA**.
> * **Referencia:** Guía 12 (Eficiencia vs. Innovación).

**1. El Dolor del Negocio:**

¿Qué problema específico estamos tratando de resolver? Describa el impacto negativo actual. No describa la solución ("necesito IA"), describa la carencia ("estamos perdiendo 4 horas diarias en clasificar facturas").
* **Respuesta:** `[Describe el problema raíz y su costo]`

**2. La Alternativa No-IA (El Filtro de Oro):**

¿Se puede resolver esto con reglas simples, una macro de Excel, un formulario web estándar o contratando a un pasante? **Si la respuesta es sí, el proyecto de IA debe descartarse o justificarse con extrema cautela.**
* **Justificación:** `[Por qué los métodos tradicionales fallan aquí (ej: variabilidad de datos no estructurados)]`

**3. Tipo de Valor (Según Guía 12):**

¿Buscamos hacer lo mismo más barato (Eficiencia/S1) o hacer algo nuevo que antes era imposible (Innovación/S2)? Esto define el presupuesto y la tolerancia al riesgo.
* **Selección:** `[ Eficiencia / Innovación ]`

---

#### Sección 2: Viabilidad Técnica (El "Cómo")

> **Contexto para el Arquitecto:**

> Aquí evaluamos si tenemos los "ingredientes" para la fábrica.
> 1.  **Datos (Guía 03):** La IA es un motor; los datos son el combustible. Sin combustible limpio (datos accesibles y legales), el motor se funde.
> 2.  **Cognición (Guía 10):** No todas las tareas son iguales. Automatizar el "Sistema 1" (rápido/patrones) es seguro. Automatizar el "Sistema 2" (juicio/moral) es peligroso y requiere supervisión humana estricta.

**1. Disponibilidad de Datos (El Combustible):**

¿Tenemos acceso a los datos necesarios? ¿Están digitalizados? ¿Tenemos el derecho legal de usarlos? (No basta con que existan; deben ser accesibles para la máquina).
* **Estado:** `[ No disponible / Crudo y sucio / Limpio y Catalogado ]`

**2. Complejidad Cognitiva (Clasificación de Riesgo S1/S2):**

* **Sistema 1 (Piloto Automático):** Tareas rápidas, repetitivas, basadas en patrones (ej. clasificar emails, extraer datos). -> *Riesgo Bajo/Medio.*
* **Sistema 2 (Piloto Manual):** Tareas de razonamiento profundo, juicio moral, estratégico o diagnóstico. -> *Riesgo Alto (Requiere Humano-en-el-Bucle estricto).*
* **Evaluación:** `[ Definir clasificación S1 / S2 ]`

---

#### Sección 3: Checklist de Validación Ética y de Impacto (El "Deberíamos")

> **Contexto para el Arquitecto:**

> Este es el núcleo de **GRC (Gobernanza, Riesgo y Cumplimiento)**. No basta con que sea técnicamente posible; debemos asegurar la **Licencia Social**. Si el proyecto se filtrara a la prensa mañana, ¿la explicación sería vergonzosa? Si la respuesta es sí, falta un control ético.

| Dimensión | Pregunta de Validación ("Go / No-Go") | Referencia | Estado |
| :--- | :--- | :--- | :--- |
| **1. Proporcionalidad** | ¿El valor justifica riesgos y costos? ¿Es la IA el medio proporcional o es "matar moscas a cañonazos"? | **Guía 06** | `[ ]` |
| **2. Licencia Social** | ¿Aprobarían los afectados (empleados/ciudadanos) este uso si se hiciera público? ¿El sistema se identifica como IA (evita el engaño)? | **Guía 10** | `[ ]` |
| **3. Protección de Datos** | ¿Hay datos sensibles? Si es así, ¿tenemos la arquitectura segura (Anexo 03) y la base legal para procesarlos? | **Guía 03** | `[ ]` |
| **4. Transparencia** | ¿Es explicable la decisión? ¿Podemos trazar *por qué* actuó así (logs de razonamiento) ante una auditoría? | **Guía 09** | `[ ]` |
| **5. Discriminación** | ¿Están los datos de origen libres de sesgos históricos? ¿Se ha evaluado el impacto en grupos vulnerables? | **Guía 03** | `[ ]` |
| **6. Responsabilidad** | ¿Existe un "Dueño del Sistema" humano designado? ¿Está definido quién paga los platos rotos si la IA falla? | **Anexo 02** | `[ ]` |

---

#### Sección 4: Definición de Éxito (El "Cuánto")

> **Contexto para el Arquitecto:**

> Si no puedes medirlo, no puedes gobernarlo. Evita métricas vanidosas ("que el chat se sienta fluido"). Necesitamos métricas de ingeniería (**Guía 08**). Debes definir el **"Golden Set"** (la prueba de la verdad) contra la cual se comparará al agente.

**1. Métrica de Calidad (El "Golden Set"):**

¿Contra qué vamos a comparar a la IA? Defina el umbral de aceptación. (Ej: "El agente debe igualar el 90% de precisión de nuestros auditores senior en una muestra de control de 100 casos").
* **KPI Objetivo:** `[Definir métrica objetiva]`

**2. Estimación de Costo (Tokenomics):**

¿Cuál es el costo estimado de operación mensual? (Considerando el costo por token de entrada/salida y volumen de transacciones). Evita el "Bucle de Costos".
* **Estimación:** `[$ / mes]`

---

#### Sección 5: Ciclo de Vida y Salida (El "Final")

> **Contexto para el Arquitecto:**

> Todo sistema de software se convierte eventualmente en deuda técnica. La responsabilidad final de GRC es saber cómo apagar el sistema antes de encenderlo (el **Plan de Retiro** o Decommissioning). No crees "Agentes Zombis" que sigan operando cuando ya no son necesarios.

**1. Plan de Retiro (Decommissioning):**

Cuando este proyecto termine o la tecnología quede obsoleta:
* ¿Cómo se eliminarán los datos vectorizados de la base de conocimiento (RAG)?
* ¿Cómo se revocan los permisos del agente?
* **Plan:** `[Definir protocolo de borrado seguro y apagado]`

**2. Resiliencia (Deuda Cognitiva):**

Si la IA falla catastróficamente o el servicio se cae, ¿el equipo humano mantiene la capacidad ("músculo cognitivo") de operar manualmente?
* **Mitigación:** `[Ej: Simulacro manual trimestral / Documentación de proceso manual]`

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="../conclusion.md">« Conclusión</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
  <div>
    <a href="./B-Politica-Institucional.md">Anexo B »</a>
  </div>
</div>
