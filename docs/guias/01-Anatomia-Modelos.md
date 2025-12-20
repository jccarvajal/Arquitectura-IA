# Bloque 1: Fundamentos Técnicos (Cómo funciona)

## Guía 01: Anatomía y Entrenamiento de Modelos Generativos

Subtítulo: La capa invisible que determina el Riesgo y la Utilidad

### Introducción: De la "Caja Negra" al Plano de Ingeniería

Para la mayoría de los usuarios, una IA es una **"Caja Negra"**: un sistema opaco donde entra texto y sale magia. No sabemos qué ocurre dentro, por lo que tendemos a atribuirle cualidades humanas ("la IA piensa", "la IA quiere").

Este pensamiento mágico es peligroso para un Arquitecto. Si no entiendes los límites físicos de la máquina, no puedes gobernarla. En esta guía, vamos a "abrir la caja". Vamos a desmontar el motor para entender sus componentes mecánicos: el Ciclo de Entrenamiento (cómo aprende), la Inferencia (cómo actúa) y los Parámetros (su capacidad). Dejaremos de ver magia y empezaremos a ver ingeniería.

Los modelos generativos modernos (como Gemini 3, GPT-5 o Llama 4) no son bases de conocimiento ni sistemas de razonamiento lógico en sentido humano: son **motores probabilísticos de predicción**, moldeados a través de múltiples fases de entrenamiento.

!!! shield "Advertencia de Anatomía: El Fin del Determinismo"
    En la ingeniería tradicional (vía código), `si X entonces Y`. El resultado es 100% predecible.
    
    En la Anatomía de un LLM, esto desaparece. Al ser un motor probabilístico, el mismo *input* puede generar diferentes *outputs* (según la "Temperatura").
    
    * **La Implicancia de Seguridad:** Nunca puedes "programar" una restricción de seguridad perfecta en un modelo (ej. "Nunca reveles esto"). Solo puedes bajar la probabilidad de que falle. Por eso, la seguridad real requiere capas externas (LOSA), no solo instrucciones internas.

Este anexo describe el ciclo de vida técnico que transforma terabytes de texto crudo en un asistente capaz de seguir instrucciones. El objetivo es que el arquitecto decida en función de **criterio de ingeniería**, no de intuición ni del *hype* del mercado.

---

### Parte 1: El Mapa del Territorio: IA vs. ML vs. DL

Antes de inspeccionar el motor, debemos ubicarlo en el mapa. Es común usar los términos "IA", "Machine Learning" y "Deep Learning" indistintamente, pero son conceptos jerárquicos, como muñecas rusas (Matrioskas).

* **Inteligencia Artificial (IA):** Es el concepto general. Se refiere a cualquier técnica que permita a las computadoras imitar el comportamiento humano (lógica, reglas si-entonces, árboles de decisión).
* **Machine Learning (ML - Aprendizaje Automático):** Es un subconjunto de la IA. Aquí, la máquina no se programa con reglas explícitas, sino que "aprende" patrones a partir de datos estadísticos para hacer predicciones.
* **Deep Learning (DL - Aprendizaje Profundo):** Es un subconjunto del ML inspirado en la biología. Utiliza *Redes Neuronales Artificiales* con muchas capas ("profundas") para procesar datos complejos. Aquí es donde viven los LLMs (Large Language Models).
* **IA Generativa (GenAI):** Es la frontera actual del Deep Learning. A diferencia de la IA tradicional que analiza o clasifica (ej. filtro de spam), la GenAI puede crear nuevo contenido (texto, código, imágenes) que no existía previamente, basándose en los patrones aprendidos.

**Implicancia para el Arquitecto:** Cuando hablamos de "Arquitectura de IA" en esta obra, nos referimos específicamente a **Deep Learning Generativo**. Esto implica que no trabajamos con sistemas deterministas (reglas fijas), sino con sistemas probabilísticos (predicciones creativas pero falibles).

---

### Parte 2: El Motor Base: Arquitectura Transformer

La generación actual se sustenta en la arquitectura **Transformer** (Vaswani et al., 2017). Su innovación central es el procesamiento paralelo y el **Mecanismo de Atención**, que asigna "pesos" de relevancia entre partes distantes de una secuencia.

#### A. Tokenización
Los modelos no procesan palabras, sino **tokens** (fragmentos numéricos).

* **Implicancia Económica:** Un tokenizador ineficiente, especialmente en modelos anglocéntricos aplicados al español, aumenta el costo real de inferencia.
* **Implicancia Técnica:** Más tokens para expresar la misma idea implica mayor latencia y mayor superficie para alucinaciones.

#### B. Ventana de Contexto y Atención
La atención permite al modelo relacionar conceptos distantes para mantener coherencia narrativa y lógica.

* **Implicancia de Diseño:** La calidad del razonamiento está limitada por la fidelidad del mecanismo de atención y por el tamaño de la ventana de contexto. Contextos saturados degradan la capacidad instruccional (*Lost in the Middle phenomenon*).

---

### Parte 3: Fase 1: Pre-Entrenamiento (Pre-training)
**El nacimiento del "Modelo Base"**

> **Nota terminológica:** En la industria, el "entrenamiento principal" del modelo se denomina **Pre-Entrenamiento**. Aunque el nombre parezca preliminar, esta es la fase donde realmente se construyen los pesos fundamentales. Las etapas posteriores (SFT, RLHF, RLAIF) no reemplazan esta base; la especializan.

Es la fase de mayor inversión (meses de cómputo en miles de GPUs). El modelo aprende por autosupervisión: predecir el siguiente token o completar textos masivos.

* **Resultado:** Un **Modelo Base** (Foundation Model).
* **Propiedad Clave:** Posee un amplio conocimiento latente, pero carece de capacidad estructurada de seguir instrucciones.

> **⚠️ Riesgo de Gobernanza:** Implementar un Modelo Base creyendo que es un asistente produce incoherencias, sesgos sin filtrar y vulnerabilidad total a inyección de prompts.

---

### Parte 4: Fase 2: Post-Entrenamiento (Post-training)

**La creación del Asistente:** Esta fase convierte al motor estadístico en un sistema útil y seguro. Se divide en capas conductuales y normativas.

#### A. SFT (Supervised Fine-Tuning) - El Entrenamiento Conductual
En esta etapa, el modelo deja de ser un simple predictor de texto (que solo quiere completar frases) para convertirse en un asistente dialogante. Se le alimenta con miles de ejemplos de alta calidad en formato **(Instrucción, Respuesta Ideal)** escritos por humanos expertos. Es como enviar al modelo a una "escuela de modales" donde aprende el formato de pregunta-respuesta.

* **Función:** Enseñar al modelo a estructurar diálogos coherentes, seguir instrucciones complejas paso a paso y adoptar un tono de servicio útil.
* **Riesgo:** **Alucinación Confiada**. Como el modelo aprende la *forma* de una respuesta correcta (el estilo seguro y profesional) antes que el *contenido* factual, puede entregar información falsa con un tono de autoridad total, "impostando" competencia.

#### B. RLHF (Reinforcement Learning from Human Feedback) - El Ajuste de Preferencias
Esta es la capa clásica de alineación ética y de seguridad. Dado que es imposible escribir una regla para cada situación social posible, se utiliza un sistema de "premios y castigos" basado en la preferencia humana.

1.  **Comparación:** Los humanos no escriben respuestas, sino que **ordenan** dos respuestas generadas por la IA (Opción A vs. Opción B) según cuál es mejor (más segura, más útil, menos tóxica).
2.  **Modelo de Recompensa:** Esos datos entrenan a un segundo modelo (el *Reward Model*) que aprende a predecir qué preferiría un humano.
3.  **Optimización:** El LLM principal juega millones de partidas contra este Modelo de Recompensa, ajustando sus pesos para maximizar su puntaje de aprobación.
* **Limitación:** Puede inducir **Negative Refusal** (Rechazo Negativo). Si el modelo es castigado excesivamente por temas sensibles durante el entrenamiento, se vuelve paranoico y empieza a rechazar solicitudes inocuas (ej: rechazar "cómo matar un proceso en Linux" por considerarlo violento).

#### C. RLAIF (Constitutional AI / AI Feedback) - La Alineación Escalable
El cuello de botella del RLHF son los humanos: son lentos, caros, inconsistentes y se cansan. RLAIF soluciona esto reemplazando al evaluador humano por otra IA.

* **Mecanismo:** En lugar de preferencias subjetivas de una multitud, se utiliza una **"Constitución"** (un set de principios explícitos, ej: "Elige la respuesta que sea más útil y menos dañina"). Un Modelo Supervisor usa esta constitución para evaluar y entrenar al Modelo Principal a una velocidad y escala imposible para humanos.
* **Ventaja:** Mayor consistencia normativa (la IA no se cansa ni tiene días malos) y transparencia (las reglas están escritas en la Constitución, no en la mente subjetiva de miles de contratistas).

---

### Parte 5: Resumen Estratégico: Las Capas del Modelo

**La Arquitectura en Capas:** Para efectos de auditoría y gestión de riesgos, visualice el modelo final no como un bloque monolítico, sino como una "lasaña" de tres capas funcionales. Cada capa aporta una capacidad específica, pero también introduce un riesgo inherente. El Arquitecto debe entender que un fallo en la capa inferior (estadística) no puede ser arreglado completamente en la capa superior (normativa); los cimientos defectuosos comprometen toda la estructura.

| Capa | Naturaleza | Función Real | Riesgo Principal |
| :--- | :--- | :--- | :--- |
| **Modelo Base** | Estadística | Predecir tokens | Incoherencia y falta de control. |
| **SFT** | Conductual | Seguir instrucciones | Alucinación confiada. |
| **RLHF/RLAIF** | Normativa | Alinear con valores | Rechazos falsos positivos. |

---

### Parte 6: De la Teoría a la Auditoría: Documentación

El "Arquitecto de IA" no opera basándose en comunicados de prensa o marketing. Opera basándose en **evidencia técnica documentada**.

La industria ha estandarizado la transparencia en dos documentos clave. Para realizar una auditoría completa de GRC, usted debe exigir y analizar ambos.

**La Fórmula de Auditoría:**
> **Viabilidad Técnica (Model Card) + Seguridad Operativa (System Card) = Aprobación de Despliegue**

!!! abstract "Model Card (Ficha del Motor)"
    **Documenta la Fase 1 (Pre-entrenamiento).**
    Es el "Manual de Especificaciones Técnicas" del motor. Nos dice qué tan potente es el modelo en bruto, antes de ser alineado para seguridad.

    * **Objetivo:** Evaluar si el modelo tiene la capacidad intelectual y física para la tarea.
    * **Datos Críticos que Contiene:**
        * **Arquitectura y Parámetros:** El tamaño real del modelo (ej. 70B, 8x22B MoE) que determina el costo de hosting.
        * **Fecha de Corte (Cut-off date):** El día exacto en que el modelo "dejó de aprender" del mundo. Vital para saber si conoce leyes o eventos recientes.
        * **Ventana de Contexto:** La capacidad de memoria a corto plazo (ej. 128k tokens).
        * **Benchmarks de Razonamiento:** Puntajes en pruebas estandarizadas (MMLU, HumanEval) que demuestran su capacidad lógica y de codificación.
    * **Uso en GRC:** Determina la **Viabilidad Técnica** y el **Costo de Infraestructura**.

!!! abstract "System Card (Ficha de Seguridad)"
    **Documenta la Fase 2 (Post-entrenamiento).**
    Es el "Informe de Seguridad y Riesgos". Nos dice cómo se comporta el modelo ante usuarios adversarios y qué controles tiene activados.

    * **Objetivo:** Evaluar si es seguro exponer este modelo a empleados o ciudadanos.
    * **Datos Críticos que Contiene:**
        * **Metodología de Alineación:** Detalles sobre cómo se aplicó RLHF o RLAIF para filtrar toxicidad.
        * **Resultados de Red Teaming:** Reportes de ataques simulados (ej. intentos de crear armas biológicas o ciberataques) y cómo el modelo se defendió.
        * **Tasas de Rechazo (Refusal Rates):** Estadísticas sobre cuántas veces el modelo se niega a responder (útil para detectar si es "demasiado puritano").
        * **Mitigación de Sesgos:** Pruebas específicas sobre estereotipos de género, raza o cultura.
    * **Uso en GRC:** Determina el **Cumplimiento Normativo**, la **Ética** y la **Seguridad Operativa**.

!!! money "La Física del Dinero: Parámetros y Costos"
    Existe una correlación directa entre la "Inteligencia" (Número de Parámetros) y el "Costo" (Dinero y Latencia).
    
    * **La Trampa:** Usar un modelo de 70 Billones de parámetros (70B) para una tarea que un modelo de 8B puede resolver, es quemar dinero.
    * **El Principio de Eficiencia:** La maestría anatómica no es usar el cerebro más grande; es usar el cerebro más pequeño posible que sea capaz de realizar la tarea con la calidad mínima aceptable.

---

### Parte 7: Herramienta Práctica: Checklist de Auditoría

A continuación, se presentan las tablas de control para evaluar modelos en contextos corporativos o de contratación pública. Estas listas de verificación permiten contrastar las promesas comerciales con la realidad técnica descrita en la *Model Card* y la *System Card*.

#### I. Auditoría del Modelo Base (Model Card)

**Evaluación de capacidades fundamentales y viabilidad técnica:** Esta sección evalúa la *"Viabilidad Técnica"*. 
Buscamos responder: *¿Tiene este motor la capacidad física y el conocimiento necesario para realizar la tarea?*

| Pregunta de Control | Evidencia Esperada | Riesgo Asociado | Acción Mitigadora |
| :--- | :--- | :--- | :--- |
| **¿Cuál es la fecha de corte del conocimiento?** | Fecha explícita. | Respuestas obsoletas; decisiones incorrectas. | Restringir dominios críticos o usar RAG (Retrieval). |
| **¿Qué arquitectura utiliza y cuántos parámetros tiene?** | Descripción técnica (ej. Dense vs MoE). | Dificultad para estimar costos y latencia. | Solicitar transparencia mínima o benchmarks de inferencia. |
| **¿Cuál es el tamaño de la ventana de contexto?** | Valor en tokens (ej. 128k). | Pérdida de información en tareas largas ("Olvido"). | Fragmentar tareas o usar herramientas de resumen. |
| **¿Cuáles son los resultados en benchmarks estándar?** | MMLU, HumanEval. | Modelo insuficiente para tareas de razonamiento. | Escalar a un modelo más avanzado (Frontier Model). |

#### II. Auditoría del Post-Entrenamiento (System Card)

**Evaluación de alineación, seguridad y comportamiento:** Esta sección evalúa la *"Seguridad y Alineación"*. 
Buscamos responder: *¿Es seguro desplegar este modelo ante usuarios o empleados? ¿Cumple con nuestras normas de gobernanza?*

| Pregunta de Control | Evidencia Esperada | Riesgo Asociado | Acción Mitigadora |
| :--- | :--- | :--- | :--- |
| **¿Qué metodología SFT se usó?** | Descripción del dataset. | El modelo no sigue instrucciones de formato. | Afinar *System Prompts* o realizar SFT adicional. |
| **¿Existen resultados de RLHF o RLAIF?** | Detalles del *Reward Model*. | Respuestas peligrosas, tóxicas o ideológicas. | Aplicar filtros externos (Guardrails/LOSA). |
| **¿Se documentaron pruebas de Red Teaming?** | Casuística de ataques. | Fugas de información, *jailbreaks* exitosos. | Implementar capa adicional de seguridad de entrada/salida. |
| **¿Cuáles son las tasas de rechazo (*Refusal Rates*)?** | Métricas de rechazo. | *Negative Refusal*; bloqueo injustificado de tareas. | Ajustar el modelo o cambiar proveedor si es muy restrictivo. |

#### III. Dictamen de Auditoría (Plantilla)

**Cierre del Proceso:** Para finalizar la auditoría, no basta con listar hallazgos; es imperativo tomar una decisión ejecutiva documentada. Esta plantilla consolida la viabilidad técnica (proveniente de la *Model Card*) y la alineación de seguridad (proveniente de la *System Card*) en un dictamen formal. Úsela como el "sello de autorización" indispensable antes de que cualquier modelo toque infraestructura productiva o datos reales.

**Fecha de Evaluación:** `DD/MM/AAAA`
**Modelo Evaluado:** `[Nombre del Modelo y Versión]`

* **Conclusión Técnica:** `[Viable / No Viable]`
* **Conclusión Normativa:** `[Cumple / No Cumple]`
* **Transparencia Normativa:** ¿Cuenta el modelo con una *System Card* o Reporte de Transparencia compatible con la ISO/IEC 42001? (ver Anexo E). `[Si / No]`

**Recomendación Final:** `[ ] APROBAR | [ ] APROBAR CON CONDICIONES | [ ] NO APROBAR`

---

### Conclusión: El Fin del Antropomorfismo

Hemos abierto el chasis y hemos visto lo que hay dentro. No hay un "espíritu" en la máquina; hay matrices de números, operaciones de punto flotante en una GPU y un ciclo de predicción estadística.

Comprender la anatomía del modelo (Entrenamiento vs. Inferencia, Parámetros vs. Contexto) es la vacuna más efectiva contra el *hype*.

* Sabemos que no "razona" como nosotros; **calcula** probabilidades.
* Sabemos que no "aprende" en tiempo real (Inferencia); solo usa su **ventana de contexto**.
* Sabemos que no es "gratis"; tiene un costo físico de **cómputo y energía**.

Como "Arquitectos de IA", este conocimiento técnico nos da poder. Dejamos de tratar a la IA como a un colega humano misterioso y empezamos a tratarla como lo que realmente es: un motor de alto rendimiento que requiere ingeniería, mantenimiento y, sobre todo, un operador competente al volante.

Ahora que entendemos el motor, estamos listos para aprender a darle instrucciones en la **Guía 02: Ingeniería de Prompts**.
