# Anexo G: Orquestación, Automatización y Gobernanza de la Inferencia

## 1. Introducción: De la Generación a la Ejecución Determinística

Este anexo establece el marco técnico-normativo para transformar los *outputs* probabilísticos de una IA (Sistema 1) en insumos para acciones operativas determinísticas y auditables. Se define la arquitectura necesaria para conectar la **descomposición interna probabilística** con la ejecución de procesos de negocio, bajo estricta supervisión del Sistema 2 (humano).

El objetivo es asegurar que la automatización no dependa de una "intención" inexistente en el modelo, sino de **reglas de negocio duras** y **evidencia de ejecución** trazable.

---

## 2. Definiciones Normativas

Para efectos de este marco de arquitectura y en alineación con estándares de gobernanza (ISO/IEC 42001):

### Chain-of-Thought (CoT)
Mecanismo interno y no expuesto de descomposición probabilística utilizado por modelos generativos para producir una respuesta. **No constituye razonamiento deliberativo**, no es auditable directamente como lógica humana y no debe ser revelado al usuario final como explicación causal. En sistemas gobernados, el CoT puede ser instrumentado indirectamente mediante registros técnicos y evidencias post-hoc sin exponer el proceso interno del modelo.

### Sistema 1 (IA Generativa)
Motor de inferencia estadística capaz de procesar patrones y generar sintaxis. Carece de responsabilidad legal, juicio moral o comprensión semántica real.

### Sistema 2 (Humano / Regla Dura)
Entidad responsable de la validación, el juicio crítico y la autorización final. Puede ser un operador humano o un código determinístico (if/then) diseñado, aprobado y responsablemente mantenido por humanos.

---

## 3. Niveles de Implementación y Control

La automatización se estructura en capas de control para mitigar la variabilidad estocástica del modelo.

### A. Nivel de Negocio: Captura de Valor
* **Eficiencia Unitaria:** Eliminación de latencia en tareas de transformación de datos.
* **Disponibilidad 24/7:** Ejecución continua sin dependencia de disponibilidad cognitiva humana.
* **Consistencia de Formato:** Estandarización de *outputs* mediante esquemas rígidos (JSON/XML), independientemente de la variabilidad del *prompt*.

### B. Nivel de Supervisión: Frontera de Decisión
* **Capa de Desacoplamiento:** El modelo nunca escribe directamente en sistemas de registro (*System of Record*). Requiere un *middleware* de validación.
* **Modalidades de Interacción:**
    * **Interlock (Human-in-the-Loop):** El humano valida la **justificación estructurada post-hoc** antes de la ejecución.
    * **Shadow (Human-on-the-Loop):** El sistema ejecuta y el humano audita la **evidencia de ejecución** en tiempo diferido.
    * **Full Auto (Human-out-of-the-Loop):** Permitido exclusivamente para acciones reversibles (lectura) o acotadas por límites físicos inmutables.

### C. Nivel Ingeniería: Protocolos de Seguridad
* **Validación de Esquema:** Todo *payload* generado debe aprobar una validación sintáctica estricta antes de ser procesado.
* **Gatekeepers Lógicos (Capa LOSA):** Implementación de reglas de negocio determinísticas que rechazan instrucciones del modelo si violan parámetros de seguridad (ej: *Circuit Breakers* financieros), independientemente de la "confianza" estadística del modelo.

---

## 4. Control de Gobernanza del Procesamiento Interno

Este apartado regula el tratamiento de los estados intermedios del modelo.

### Política de No Exposición
**El sistema no expone ni persiste Chain-of-Thought legible por humanos.** La visualización del "diálogo interno" del modelo induce a alucinación antropomórfica en el operador y falsas expectativas de causalidad.

### Registro Técnico de Inferencia
Para fines de auditoría y control, se almacenan exclusivamente **metadatos técnicos de ejecución**, incluyendo:
* Identificadores de *prompt* y *completion*.
* Versión exacta del modelo y temperatura.
* Herramientas invocadas y parámetros de llamada.
* Políticas de seguridad activadas (guardrails).
* Validaciones humanas asociadas (si aplica).

La responsabilidad interpretativa sobre estos metadatos recae exclusivamente en el Sistema 2 humano.

Estos registros no constituyen explicaciones causales, sino evidencia operacional para fines de control, auditoría y mejora del sistema. lo

---

## 5. Matriz de Riesgo y Supervisión Operativa

El nivel de control no se basa en la "calidad del razonamiento" (inexistente), sino en el impacto de la acción.

| Categoría de Acción | Impacto | Mecanismo de Control Técnico | Supervisión Sugerida |
| :--- | :--- | :--- | :--- |
| **Consulta** | Nulo (Lectura) | Caché / Listas de Control de Acceso (ACL) | Auditoría de logs de acceso |
| **Transformación** | Bajo (Procesamiento) | Validación de esquema JSON estricto | Revisión por muestreo aleatorio |
| **Transacción** | Alto (Escritura/Gasto) | **Circuit Breaker** + Firma Digital | Aprobación Humana Previa (Interlock) |

**Nota sobre Monitoreo:** No se monitorea el "pensamiento", se monitorean las desviaciones, inconsistencias y señales de riesgo a partir de *inputs*, *outputs*, estados intermedios no semánticos y eventos de ejecución.

---

## 6. Checklist de Readiness para Automatización
*El Arquitecto debe validar estos puntos antes de habilitar actuadores en producción.*

### I. Determinismo del Proceso
* [ ] **Definición de Salida:** ¿Existe un esquema de datos (Schema) rígido que el modelo deba completar?
* [ ] **Manejo de Error:** ¿El sistema de destino sabe rechazar una solicitud mal formada sin corromperse?

### II. Factibilidad Técnica
* [ ] **Aislamiento:** ¿Existe un entorno *Sandbox* donde el actuador pueda fallar sin impacto en producción?
* [ ] **Principio de Mínimo Privilegio:** ¿La credencial de la API tiene permisos limitados exclusivamente a la tarea requerida?

### III. Seguridad y Trazabilidad (CoT-Safe)
* [ ] **Evidencia Post-Hoc:** ¿El sistema guarda el *output* final y la justificación estructurada, descartando la traza cognitiva bruta?
* [ ] **Límites Duros:** ¿Existen *Circuit Breakers* de negocio (monto/volumen) que el modelo no puede sobreescribir?
* [ ] **Rollback:** ¿Existe un procedimiento técnico para revertir la acción si la inferencia fue estadísticamente correcta pero operativamente errónea?

---

## 7. Restricciones, Exclusiones y Anti-Patrones de Automatización

Esta sección define los **límites formales de la automatización basada en IA generativa (Sistema 1)**. 
No describe capacidades técnicas, sino **condiciones de prohibición**, **corte** y **responsabilidad**, derivadas directamente de la inexistencia estructural de un Sistema 2 en la IA.

### 7.1 Principio de No Delegación de Juicio

Queda prohibida la delegación de juicio humano a sistemas de IA generativa en cualquier contexto que requiera:

- Interpretación normativa no codificada
- Evaluación moral o ética
- Determinación de responsabilidad
- Toma de decisiones con consecuencias legales directas

**Fundamento:**  

La IA (Sistema 1) carece de criterio, intención y responsabilidad. No existe Sistema 2 de IA.  
Toda delegación de juicio constituye una falla de gobernanza, no una limitación tecnológica.

### 7.2 Anti-Patrón: Automatización de Decisiones Irreversibles

No se permite automatización cuando la acción cumple una o más de las siguientes condiciones:

- Es irreversible o no mitigable post-hoc
- Produce daño no compensable
- Impacta derechos fundamentales o garantías básicas

**Ejemplos no exhaustivos:**

- Terminación contractual
- Sanciones o penalizaciones
- Denegación de servicios esenciales
- Clasificación con efectos jurídicos o reputacionales

### 7.3 Anti-Patrón: Simulación de Razonamiento

Queda explícitamente prohibido:

- Exponer Chain-of-Thought al usuario final
- Utilizar narrativas generadas como explicación causal
- Tratar *rationales* sintéticos como evidencia de razonamiento

**Riesgo asociado:**  

Antropomorfismo operacional, falsa percepción de comprensión y desplazamiento indebido de responsabilidad.

### 7.4 Anti-Patrón: Confianza por Consistencia Estadística

La consistencia o repetibilidad de un *output* **no constituye**:

- Veracidad
- Corrección normativa
- Cumplimiento regulatorio
- Justificación suficiente para la acción

La estabilidad estadística es una propiedad del modelo, no del dominio de verdad.

### 7.5 Condiciones de Corte Operacional (Kill Criteria)

La automatización debe ser deshabilitada inmediatamente si se detecta:

- *Drift* semántico o de datos no explicado
- Relajación progresiva de la supervisión humana
- Operación por inercia organizacional (“así siempre ha funcionado”)
- Uso del sistema fuera del dominio originalmente aprobado

La continuidad operativa sin revisión humana periódica constituye una falla de control.

### 7.6 Responsabilidad Organizacional

La responsabilidad no es delegable.

- La decisión de automatizar es humana
- La decisión de mantener la automatización es humana
- La responsabilidad por los efectos de la automatización es siempre humana

La IA no responde, no explica y no asume consecuencias.  
El Sistema 2 humano es el único sujeto responsable ante la organización y la ley.

---

!!! success "Declaración de Responsabilidad (Cierre del Anexo)"
    **El Chain-of-Thought pertenece íntegramente al Sistema 1 (IA) y no constituye Sistema 2, criterio ni juicio. Toda validación, interpretación y responsabilidad corresponde al humano en el bucle.**
