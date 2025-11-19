### Anexo 01: Formulación y Evaluación de Proyectos de IA

Subtítulo: El Canvas de Viabilidad: De la Idea al Proyecto

#### Introducción: El Primer Filtro de Gobernanza

Antes de prototipar, debemos validar. Este anexo es la herramienta de **"Screening" (Triage)** mencionada en la **Guía 07 (Gobernanza)**.

Su propósito es evitar el "solucionismo tecnológico" (usar IA para problemas que no lo requieren) y asegurar que solo los proyectos que son **técnicamente viables**, **estratégicamente valiosos** y **éticamente robustos** pasen a la fase de desarrollo.

Este documento debe ser completado por el "Dueño del Proyecto" y visado por el "Comité de Gobernanza" antes de escribir la primera línea de código.

---

#### Sección 1: Definición Estratégica (El "Por Qué")

*El filtro de negocio. Si no hay dolor real, no hay proyecto.*

**1. El Dolor del Negocio:**
¿Qué problema específico estamos tratando de resolver? ¿Cuál es el costo actual (en dinero, tiempo o riesgo) de no hacer nada?
* **Respuesta:** `[Describe el problema raíz, no la solución]`

**2. La Alternativa No-IA (El Filtro de Oro):**
¿Se puede resolver esto con reglas simples, una macro de Excel o software tradicional? (Ver principio de Proporcionalidad). **Si la respuesta es sí, el proyecto de IA debe descartarse o justificarse con extrema cautela.**
* **Justificación:** `[Por qué los métodos deterministas tradicionales fallan aquí]`

**3. Tipo de Valor (Según Guía 12):**
* **Eficiencia:** Hacer lo mismo que hacemos hoy, pero más barato o rápido (Automatización de Sistema 1).
* **Innovación:** Hacer algo nuevo que antes era inviable (ej. Hiper-personalización).
* **Selección:** `[ Eficiencia / Innovación ]`

---

#### Sección 2: Viabilidad Técnica (El "Cómo")

*El filtro de ingeniería. Sin datos y sin definición cognitiva, la IA falla.*

**1. Disponibilidad de Datos (El Combustible - Guía 03):**
¿Tenemos acceso a los datos necesarios? ¿Están digitalizados? ¿Tenemos el derecho legal de usarlos?
* **Estado:** `[ No disponible / Crudo y sucio / Limpio y Catalogado ]`

**2. Complejidad Cognitiva (S1 vs S2 - Guía 10):**
* **Sistema 1 (Piloto Automático):** Tareas rápidas, repetitivas, basadas en patrones (ej. clasificar emails, extraer datos). -> *Riesgo Bajo/Medio.*
* **Sistema 2 (Piloto Manual):** Tareas de razonamiento profundo, juicio moral o estratégico. -> *Riesgo Alto (Requiere Humano-en-el-Bucle estricto).*
* **Evaluación:** `[ Definir clasificación S1 / S2 ]`

---

#### Sección 3: Checklist de Validación Ética y de Impacto (El "Deberíamos")

*El filtro de GRC. Evalúa las 6 dimensiones de riesgo antes de aprobar.*

| Dimensión | Pregunta de Validación ("Go / No-Go") | Referencia de Solución | Estado |
| :--- | :--- | :--- | :--- |
| **1. Proporcionalidad** | ¿El valor del proyecto justifica los riesgos y costos? ¿Es la IA el medio adecuado y proporcional, o estamos "matando moscas a cañonazos"? | **Guía 06:** Filtro "Quick Win".<br>**Anexo 02:** Política Inst. | `[ ]` |
| **2. Licencia Social** | ¿Aprobarían los usuarios/ciudadanos este uso de sus datos si se hiciera público hoy en las noticias? ¿El sistema evita el engaño (se identifica como IA)? | **Guía 10:** Confianza.<br>**Guía 13:** Divulgación. | `[ ]` |
| **3. Protección de Datos** | ¿Hay datos sensibles o personales involucrados? Si es así, ¿tenemos la arquitectura segura (ej. Modelo Local vs API Pública) y la base legal? | **Guía 03:** Privacidad.<br>**Guía 07:** Fuga de Datos. | `[ ]` |
| **4. Transparencia** | ¿Es explicable la decisión? ¿Podemos trazar *por qué* la IA tomó una decisión (logs de razonamiento/CoT) si nos auditan? | **Guía 09:** Observabilidad.<br>**Guía 05:** Cadena de Pensamiento. | `[ ]` |
| **5. Discriminación** | ¿Están limpios los datos de origen de sesgos históricos (ej. género, raza, nivel socioeconómico)? ¿Existen grupos vulnerables afectados? | **Guía 03:** Auditoría de Datos.<br>**Guía 10:** Sesgo Algorítmico. | `[ ]` |
| **6. Responsabilidad** | ¿Existe un "Dueño del Sistema" humano designado formalmente? ¿Está definido el protocolo de supervisión humana significativa? | **Anexo 02:** Roles.<br>**Guía 07:** Rendición de Cuentas. | `[ ]` |

---

#### Sección 4: Definición de Éxito (El "Cuánto")

*Si no puedes medirlo, no puedes gobernarlo (Guía 08).*

**1. Métrica de Calidad (El "Golden Set"):**
¿Contra qué vamos a comparar a la IA? (Ej: "Debe igualar el 90% de precisión de nuestros auditores senior en una muestra de control de 100 casos").
* **KPI Objetivo:** `[Definir métrica objetiva]`

**2. Estimación de Costo (Tokenomics):**
¿Cuál es el costo estimado de operación mensual? (Considerando el costo por token, licencias y volumen de transacciones).
* **Estimación:** `[$ / mes]`

---

#### Sección 5: Ciclo de Vida y Salida (El "Final")

*La responsabilidad final de GRC es saber cómo apagar el sistema.*

**1. Plan de Retiro (Decommissioning):**
Cuando este proyecto termine o la tecnología quede obsoleta:
* ¿Cómo se eliminarán los datos vectorizados de la base de conocimiento (RAG)?
* ¿Cómo se revocan los permisos del agente?
* **Plan:** `[Definir protocolo de borrado seguro y apagado]`

**2. Resiliencia (Deuda Cognitiva):**
Si la IA falla catastróficamente o el servicio se cae, ¿el equipo humano mantiene la capacidad de operar manualmente?
* **Mitigación:** `[Ej: Simulacro manual trimestral / Documentación de proceso manual]`

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
    <div>
      <a href="../conclusion.html">« Conclusión</a>
    </div>
    <div>
      <a href="../">Volver al Índice</a>
    </div>
    <div>
      <a href="./02-Politica-Institucional.html">Siguiente Anexo »</a>
    </div>
</div>
