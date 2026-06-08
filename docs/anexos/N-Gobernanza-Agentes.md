# ANEXO N: Gobernanza Operacional de Agentes Autónomos 

**Del Control Estático a los Guardrails Dinámicos**

### Introducción

Las organizaciones han desarrollado durante décadas mecanismos robustos para gobernar personas, procesos, sistemas y datos. Sin embargo, la incorporación de agentes autónomos introduce una nueva categoría ontológica en la arquitectura empresarial: entidades digitales capaces de observar, razonar, decidir y actuar dentro de los procesos de negocio.

A diferencia del software determinista tradicional, los agentes no se limitan a ejecutar árboles de decisión predefinidos. Interpretan objetivos abiertos, seleccionan herramientas, interactúan con sistemas críticos y producen efectos materiales sobre la operación y el entorno normativo. Consecuentemente, los mecanismos tradicionales de administración de aplicaciones son estructuralmente insuficientes para gobernar su comportamiento.

Este anexo establece el marco de **Gobernanza Operacional de Agentes Autónomos**, destinado a administrar estas poblaciones digitales dentro del apetito de riesgo organizacional. 

La tesis central de este documento es que **la autonomía es un recurso gobernable**. Al igual que el presupuesto, los privilegios de red o el acceso a datos, la autonomía es una capacidad que la organización puede otorgar, restringir, degradar o revocar. No es un derecho tecnológico del sistema, sino una concesión operacional directamente proporcional a la confianza que la organización puede medir y auditar. 

El objetivo de la gobernanza operacional no es maximizar la autonomía de los agentes, sino optimizar la relación entre autonomía, valor y riesgo.

---

### 1 El agente como actor organizacional digital

A efectos de gobierno corporativo, un agente autónomo pierde la categoría de "aplicación" y se considera un **actor organizacional digital**. 

Al igual que un colaborador humano, este actor posee:

* **Objetivos:** Mandatos de negocio que debe satisfacer.
* **Capacidades:** Habilidades de procesamiento y toma de decisiones.
* **Restricciones:** Límites normativos, éticos y operacionales.
* **Acceso a recursos:** Privilegios sobre datos, APIs e infraestructura.
* **Capacidad de producir efectos:** Impacto real sobre transacciones, clientes o procesos.

Su gobierno debe integrarse armónicamente con los mecanismos institucionales de gestión, supervisión y rendición de cuentas, trascendiendo los controles puramente tecnológicos.

---

### 2 Inventario, Clasificación y Criticidad

Ningún agente está autorizado a operar fuera del **inventario corporativo de agentes e inteligencia artificial**. El registro es un pre-requisito ineludible para el despliegue.

Los agentes se clasificarán según su impacto en la cadena de valor:

* **Informativos:** Sintetizan y presentan datos (riesgo operativo nulo).
* **Analíticos:** Producen inferencias o diagnósticos que informan decisiones humanas.
* **Operativos:** Ejecutan tareas repetitivas dentro de flujos de trabajo cerrados.
* **Decisionales:** Toman resoluciones sobre transacciones, recursos o interacciones con clientes.
* **Orquestadores:** Coordinan y delegan tareas a otros agentes o sistemas.

---

### 3 Propietario y Responsabilidad Institucional

Todo agente debe tener un responsable humano identificable a nivel directivo o gerencial (*Business Owner*). **La responsabilidad por las decisiones, acciones y externalidades de un agente es indelegable al modelo subyacente, al proveedor tecnológico o al equipo de ingeniería.**

El propietario tiene el mandato ineludible de:

* Aprobar el propósito y el caso de uso.
* Asumir el riesgo operacional derivado de su actuación.
* Supervisar el desempeño a través de métricas de confianza.
* Autorizar modificaciones estructurales o la ampliación de capacidades.
* Dictaminar su desactivación o retiro.

#### 3.1 Modelo de Responsabilidad Organizacional

La gobernanza operacional de agentes requiere la distribución explícita de responsabilidades sobre el ciclo de vida del agente:

* **Propietario del Negocio (Business Owner):** Define el objetivo, aprueba el caso de uso y asume el riesgo operacional de las decisiones del agente.
* **Propietario Técnico (AI/System Owner):** Garantiza que la implementación respeta los guardrails estáticos y asegura el mantenimiento del inventario.
* **Arquitectura:** Valida que el nivel de autonomía asignado es coherente con la criticidad del proceso y la capacidad de supervisión.
* **Riesgo Operacional y Seguridad:** Define los umbrales que activan los guardrails dinámicos y certifica los mecanismos de degradación elegante y contención.
* **Auditoría:** Verifica retrospectivamente (HOOTL) que la evidencia de razonamiento y la trazabilidad cumplen con la normativa interna y regulatoria.

---

### 4 Capacidades, Privilegios y Segregación de Funciones

Los agentes están sujetos al principio de **Mínimo Privilegio**. Las herramientas (APIs, bases de datos, interfaces) a las que un agente tiene acceso deben declararse explícitamente y limitarse a las estrictamente necesarias para su objetivo. 

Asimismo, la arquitectura técnica debe incorporar mecanismos de **verificación continua (Zero Trust)** para validar el contexto de cada invocación.

Cuando los agentes operen sobre procesos de alta criticidad o riesgo financiero, se aplicarán estrictos principios de **Segregación de Funciones (SoD)**. Un agente encargado de proponer una transacción financiera no puede ser el mismo agente (o compartir la misma instancia de modelo) que aprueba o audita dicha transacción.

---

### 5 Niveles de Autonomía y Matriz de Riesgo

La autonomía es una escala graduada, no una característica binaria. Todo agente debe tener asignado y justificado uno de los siguientes niveles (N0 a N5):

| Nivel de Autonomía | Descripción del Comportamiento | Límite Operacional según Criticidad |
| :--- | :--- | :--- |
| **N0 - Asistencia** | Recupera y organiza información sin modificar el estado del sistema. | Permitido en todos los niveles de criticidad. |
| **N1 - Recomendación** | Propone cursos de acción; requiere acción humana deliberada para su ejecución. | Permitido en todos los niveles de criticidad. |
| **N2 - Ejecución Supervisada** | Ejecuta secuencias automáticas, pero se detiene para solicitar aprobación humana en nodos críticos. | Permitido en alta criticidad solo con guardrails dinámicos. |
| **N3 - Autonomía Limitada** | Actúa de principio a fin sin aprobación, confinado a escenarios de bajo riesgo y alta certidumbre. | Requiere excepción formal para procesos de alta criticidad. |
| **N4 - Orquestación Autónoma** | Delega, planifica y administra flujos de trabajo complejos con otros agentes. | Estrictamente prohibido en procesos de alta criticidad. |
| **N5 - Autonomía Plena** | Administra de manera integral procesos. La autonomía no altera la responsabilidad institucional. | Limitado a entornos de experimentación aislados (Sandboxes). |

La supervisión diferida establecida para el Nivel 5 constituye una optimización del control, no una transferencia de la obligación fiduciaria del propietario.

---

### 6 Guardrails Estáticos: La Primera Línea de Defensa

Los guardrails estáticos son restricciones absolutas programadas a nivel de infraestructura y arquitectura. Constituyen los "muros de contención" del agente y no pueden ser alterados por el modelo bajo ninguna circunstancia.

Incluyen:

* **Restricciones de IAM:** Controles de acceso basados en roles (RBAC).
* **Restricciones de Red:** Confinamiento a VPCs específicas y listas de IPs permitidas.
* **Restricciones Presupuestarias:** Límites duros de consumo de tokens o llamadas a APIs (Rate Limiting).
* **Filtros de Contenido Duros:** Bloqueo léxico y semántico de entradas/salidas prohibidas.

---

### 7 Guardrails Dinámicos y Degradación Elegante

Mientras los guardrails estáticos definen *dónde* puede operar un agente, los guardrails dinámicos definen *cómo* se comporta el agente en respuesta a las condiciones cambiantes del entorno. 

La autonomía se gestiona como una variable dinámica. El sistema debe monitorizar continuamente el contexto e implementar una **Degradación Elegante (Graceful Degradation)** de la autonomía si se detectan anomalías.

**Triggers (Disparadores) de Degradación:**

* Incremento súbito de la latencia o inestabilidad en la infraestructura base.
* Detección de desviación semántica o lógica por parte de sistemas de evaluación paralelos.
* Indicadores de incerteza operacional o anomalías en el patrón de resolución del agente.
* Modificaciones abruptas en el contexto operativo o volumen transaccional.

**Respuestas Dinámicas:**

* **Downgrade de Autonomía:** El agente pasa automáticamente de N3 (Autonomía Limitada) a N1 (Recomendación), requiriendo que un humano retome el control de la ejecución.
* **Cuarentena de Herramientas:** Revocación temporal de permisos de escritura, manteniendo habilitados los permisos de lectura.
* **Activación de Corto Circuito:** Suspensión inmediata de la tarea hasta la validación de un supervisor.

---

### 8 Supervisión y Mecanismos de Intervención

La arquitectura debe soportar tres modelos de supervisión, seleccionados según el nivel de autonomía y la criticidad:

1. **HITL (Human-in-the-Loop):** Para decisiones irreversibles o de alto impacto. El humano es el cuello de botella intencional.
2. **HOTL (Human-on-the-Loop):** El humano actúa como un supervisor pasivo con capacidad de veto en tiempo real sobre las acciones del agente.
3. **HOOTL (Human-out-of-the-Loop):** Intervención humana puramente asíncrona mediante auditoría retrospectiva.

**Mecanismos de Contención y Aislamiento:**

Todo agente de Nivel 2 o superior debe estar sujeto a mecanismos de interrupción controlada, independientes de su propio sistema cognitivo. Dependiendo de la arquitectura, estos incluirán:

* Degradación forzada de nivel de autonomía.
* Cuarentena de red (aislamiento del ecosistema).
* Revocación automatizada de credenciales de acceso.
* Suspensión total del procesamiento.

---

### 9 Evidencia, Licencia Operacional y Trazabilidad

Todo agente sujeto a este marco opera bajo una **Licencia Operacional**. Un agente mantiene esta licencia únicamente mientras conserve métricas de desempeño, trazabilidad y alineación superiores a los umbrales definidos por la organización. 

Para sostener dicha licencia, toda actuación debe generar telemetría inmutable. La cadena de trazabilidad mínima requerida es:

* **Mandato de entrada** (Contexto u objetivo inicial).
* **Justificación observable de la decisión** (Evidencia del razonamiento aplicado, independientemente del método de inferencia del modelo subyacente).
* **Invocación de herramientas** (Peticiones enviadas a sistemas externos).
* **Decisión o acción final ejecutada.**

Un descenso en la calidad de las decisiones o un incremento anómalo en la tasa de intervención humana revoca automáticamente la licencia operacional, suspendiendo el permiso de despliegue en producción.

---

### 10 Ciclo de Vida y Retiro del Agente

Los agentes no se despliegan; se gestionan de forma continua. El ciclo de vida mandatorio abarca: 
Diseño > Evaluación de Riesgos > Aprobación de Arquitectura y Seguridad > Despliegue en Sombra (Shadow Mode) > Liberación por Fases > Monitoreo Continuo > Auditoría Recurrente.

Ningún agente podrá avanzar a una fase superior de despliegue sin demostrar métricas de desempeño, estabilidad, trazabilidad y alineación compatibles con los umbrales definidos por la organización.

**Retiro (Sunsetting):** La desactivación de un agente exige un procedimiento formal que incluya la rotación/destrucción de todas las credenciales asociadas, la preservación de los registros de auditoría por motivos normativos y el re-enrutamiento de los procesos de negocio dependientes hacia sistemas de contingencia.

---

### 11 Gobernanza de Poblaciones y Riesgo Sistémico

A medida que la organización escala la adopción de inteligencia artificial, el desafío de gobernanza transita desde el control del agente individual hacia la administración de ecosistemas de agentes.

La interacción entre múltiples agentes autónomos introduce el potencial de **riesgo sistémico**, donde decisiones subóptimas pueden amplificarse a través de fallas en cascada o bucles de retroalimentación no previstos.

Para mitigar este riesgo, la arquitectura de poblaciones de agentes debe asegurar:

* **Límites de Delegación:** Un agente no puede delegar tareas a otro agente que posea un nivel de autonomía o privilegios de acceso superiores a los propios.
* **Prevención de Bucles de Decisión (Deadlocks y Loops):** Los ecosistemas que involucran interacciones agente-agente deben contar con mecanismos de tiempo de espera (timeouts) y límites de iteración estructurales.
* **Trazabilidad Inter-agente:** La evidencia auditable debe permitir la reconstrucción completa del flujo de información y decisiones a través de múltiples agentes involucrados en un mismo proceso.
* **Aislamiento de Dominios:** Agentes operando en procesos de alta criticidad no deben compartir instancias de memoria de corto o largo plazo con agentes orientados a procesos de baja criticidad.

#### 11.1 Principio de Contención Sistémica

Ningún ecosistema de agentes debe permitir que una falla individual escale sin restricciones a través de toda la organización. La arquitectura debe incorporar límites de propagación, segmentación de dominios, desacoplamiento operacional y mecanismos de recuperación que permitan contener el impacto de errores locales.

---

### PRINCIPIO RECTOR

> **La organización no gobierna modelos algorítmicos. La organización gobierna capacidades y delegaciones operacionales.**
>
> Un agente autónomo constituye la delegación de una facultad institucional. Su despliegue exige límites comprobables, supervisión asimétrica y un diseño consciente del riesgo. En procesos de alta criticidad, una ejecución restringida es siempre arquitectónicamente superior a una autonomía plena.
> 
> En la era de la inteligencia artificial:
>
> **Delegar la acción jamás implica abdicar la responsabilidad.**
> 
> La gobernanza operacional garantiza que la autonomía técnica opere como un instrumento de valor, jamás como un vector de vulnerabilidad sistémica.