## Anexo E: Glosario Unificado

### Introducción: Un Lenguaje Común

Este anexo es el léxico centralizado de "Arquitectura de Inteligencia Artificial". La terminología en este campo es precisa, y un malentendido conceptual puede llevar a errores de arquitectura. Este glosario no es solo una lista de definiciones; es un mapa de referencia cruzada que conecta los conceptos clave con las guías donde se exploran en profundidad. Úsalo para solidificar tu comprensión y asegurar que todo el equipo hable el mismo idioma.

---

### Léxico de "Arquitectura de Inteligencia Artificial"

**Abdicación vs. Aumento (Abdication vs. Augmentation)**

* **Definición:** El dilema central de la sinergia. **Abdicación** es la tendencia humana a confiar ciegamente en la IA, dejando de pensar y convirtiéndose en un "pulsador de botones". **Aumento** es el uso de la IA para eliminar el trabajo de "Sistema 1" y liberar al humano para que se enfoque en el "Sistema 2" (criterio, estrategia).  
* **Referencia Principal:** Guía 15 (Ética y Confianza).

**Agente (Agent)**

* **Definición:** Un sistema de IA que va más allá de la simple respuesta. Un agente puede razonar, planificar, descomponer tareas complejas y utilizar "herramientas" (como APIs o bases de datos) para ejecutar acciones de forma autónoma.  
* **Referencia Principal:** Guía 05 (Ingeniería de Agentes), Guía 06 (Sistemas Cognitivos).

**Agente Enrutador (Router Agent)**

* **Definición:** Un tipo de agente "gerente" (o de metacognición) cuyo único trabajo es analizar una solicitud y dirigirla al agente especialista o al modelo de IA (LLM) más adecuado para esa tarea específica (ej: enviar tareas analíticas a Claude 3 Opus y tareas simples a Haiku).  
* **Referencia Principal:** Guía 06 (Sistemas Cognitivos), Guía 14 (Modelos y Mercado).

**Agentes-como-Servicio (AaaS)**

* **Definición:** Una estrategia de adquisición donde se "contrata al especialista". Es un producto de IA terminado (ej. Perplexity, Copilot) que se consume vía suscripción, ofreciendo rápida implementación a cambio de baja flexibilidad técnica.
* **Referencia Principal:** Guía 14 (Modelos y Mercado).

**Ajuste Fino (Fine-Tuning)**

* **Definición:** El proceso de re-entrenar un modelo de IA preexistente (como Llama 3) usando un conjunto de datos más pequeño y específico. No le enseña nuevo conocimiento, sino que ajusta su comportamiento, tono, estilo o su habilidad para realizar una tarea muy específica.  
* **Referencia Principal:** Guía 07 (Ajuste Fino).

**Alucinación (Hallucination)**

* **Definición:** Un riesgo operacional crítico donde el LLM genera información que es factualmente incorrecta, inventada o contradictoria, pero la presenta con total confianza y elocuencia. Es una "mentira" no intencional.  
* **Referencia Principal:** Guía 09 (Gobernanza), Guía 10 (Evaluación y QA).

**Amnesia Estática (Static Amnesia)**

* **Definición:** Un término conceptual propio de esta obra para describir la limitación fundamental de la arquitectura Transformer. Es la incapacidad estructural del modelo para consolidar nueva información (aprendida de las interacciones) en su memoria a largo plazo (los pesos del modelo) después de que finaliza su entrenamiento.
* **Referencia Principal:** Guía 03 (Contexto y Memoria), Guía 17 (Perspectivas).

**Aprendizaje Anidado (Nested Learning)**

* **Definición:** Un paradigma de arquitectura de IA que se perfila como el sucesor del Transformer. Propuesto por Google Research (NeurIPS 2025), abandona las "capas de cómputo" estáticas por "capas de cognición" que operan y se actualizan a múltiples frecuencias (escalas de tiempo).
* **Referencia Principal:** Guía 17 (Perspectivas).

**Aprendizaje Continuo (Continual Learning)**

* **Definición:** El objetivo de las arquitecturas de próxima generación (como "Nested Learning"). Es la capacidad de un modelo de IA para aprender continuamente de nuevas interacciones y datos sin sufrir un "olvido catastrófico" (olvidar lo que sabía antes). Es la solución a la "Amnesia Estática".
* **Referencia Principal:** Guía 17 (Perspectivas).

**Auto-Modificable (Self-Modifying)**

* **Definición:** Una característica clave de los modelos de Aprendizaje Anidado. Es la capacidad del sistema para aprender y modificar su propio algoritmo de actualización, en lugar de depender de una regla de aprendizaje fija.
* **Referencia Principal:** Guía 17 (Perspectivas).

**Basura Elocuente (Eloquent Bullshit)**

* **Definición:** El principal producto de riesgo de la IA. Es el resultado de combinar una "basura cognitiva" (un prompt vago, sin criterio o mal formulado) con un LLM potente. La IA produce una respuesta fluida, profesional y convincente que es fundamentalmente incorrecta o inútil.  
* **Referencia Principal:** Guía 16 (Aprender a Pensar).

**Blueprint**

* **Definición:** Un caso de estudio práctico y un plano de arquitectura. Es la plantilla que conecta la teoría de las Guías y la técnica de los Anexos para resolver un problema de negocio específico, detallando los ingredientes, el flujo y la sinergia resultante.  
* **Referencia Principal:** Anexo C (Blueprints).

**Brecha de Aprendizaje (Learning Gap)**

* **Definición:** El concepto central de la obra. Describe por qué la mayoría de los pilotos de IA fracasan (el 95%). Se debe a que las herramientas genéricas son "tontas" y operan sin memoria, lo que se manifiesta en tres fallos: no recuerdan el contexto, no aprenden del feedback y no se adaptan al flujo de trabajo.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Brecha GenAI (GenAI Divide)**

* **Definición:** Término de la industria (2025) que describe la amplia brecha entre la alta experimentación con IA Generativa (la mayoría de las organizaciones) y el bajo retorno de inversión tangible (el 5% que logra impacto real en el negocio).
* **Referencia Principal:** Guía 13 (Estrategia y Valor).

**Bucle de Costos (Cost Loop)**

* **Definición:** Un riesgo operacional crítico donde un agente autónomo, usualmente operando en un ciclo ReAct, entra en un bucle (loop) infinito. Esto causa que el agente ejecute miles de llamadas a la API sin control, generando un gasto masivo e imprevisto.
* **Referencia Principal:** Guía 09 (Gobernanza), Guía 06 (Sistemas Cognitivos).

**Chain-of-Thought (CoT)**

* **Definición:** Una técnica de *prompting* y un patrón de razonamiento. Consiste en forzar al modelo a explicar su razonamiento "paso a paso" antes de dar la respuesta final, lo que aumenta la precisión en tareas lógicas.
* **Referencia Principal:** Guía 02 (Ingeniería de Prompts), Guía 06 (Sistemas Cognitivos).

**Co-Piloto Estratégico**

* **Definición:** El rol humano evolucionado en la sinergia Humano-IA. El Co-Piloto no es un "usuario" pasivo que "pide" tareas, sino un "operador" activo que "instruye", "valida" y "audita" a la IA, usando su criterio de "Sistema 2" para dirigir la herramienta.
* **Referencia Principal:** Guía 16 (Aprender a Pensar).

**Compactación (de Contexto)**

* **Definición:** Una estrategia de ingeniería de contexto donde, en una conversación larga, el sistema usa un LLM para resumir automáticamente el historial de chat anterior, preservando el contexto clave sin exceder la Ventana de Contexto.  
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Consolidación (de Memoria)**

* **Definición:** Un proceso crítico en la gestión de Memoria. Es la etapa de "curaduría" donde un LLM analiza la nueva información extraída y la compara con los recuerdos existentes para fusionar duplicados, resolver contradicciones y eliminar datos obsoletos.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Costo Cuadrático (Quadratic Cost)**

* **Definición:** La principal limitación de costo y rendimiento de la arquitectura Transformer. Se refiere al hecho de que el costo computacional y el uso de memoria crecen exponencialmente (O(n<sup>2</sup>)) con la longitud de la Ventana de Contexto.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**CRF-R**

* **Definición:** Acrónimo mnemotécnico propio de esta obra para el diseño de prompts robustos: **C**ontexto, **R**ol, **F**ormato, **R**estricciones.
* **Referencia Principal:** Guía 02 (Ingeniería de Prompts), Anexo D (Plantillas).

**Datos Sintéticos (Synthetic Data)**

* **Definición:** Una táctica donde se utiliza un modelo de IA potente para generar un gran volumen de ejemplos de entrenamiento de alta calidad. Es la fuente de datos clave para el Ajuste Fino.
* **Referencia Principal:** Guía 04 (Estrategia de Datos), Guía 07 (Ajuste Fino).

**Divulgación (Disclosure)**

* **Definición:** Un principio legal y técnico para Agentes Autónomos. Requiere que el agente se identifique transparentemente como una IA y revele ante Terceros a quién representa (quién es su "Principal").
* **Referencia Principal:** Guía 17 (Perspectivas), Anexo F (Bibliografía).

**Entrenamiento (Training)**

* **Definición:** La fase inicial y masiva del ciclo de vida de un modelo (Guía 01), donde el LLM aprende patrones a partir de terabytes de datos. Es distinto a la Inferencia y al Ajuste Fino.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**ESG (Environmental, Social, and Governance)**

* **Definición:** Marco de criterios corporativos que mide la sostenibilidad. En IA, el factor 'E' (Ambiental) vigila el consumo energético de los modelos, y el 'S' (Social) vigila el sesgo y el impacto laboral.
* **Referencia Principal:** Guía 15 (Ética y Confianza).

**Estrategia de Datos (Data Strategy)**

* **Definición:** El plan maestro para la adquisición, almacenamiento, limpieza, seguridad y (crucialmente) vectorización de los datos propietarios. Define el "combustible" que alimentará a los sistemas RAG.
* **Referencia Principal:** Guía 04 (Estrategia de Datos).

**ETL-V**

* **Definición:** Adaptación propia del estándar de ingeniería de datos (ETL). Pipeline que Extrae, Transforma, Carga y **Vectoriza** los datos para alimentar la memoria RAG de la IA.
* **Referencia Principal:** Guía 04 (Estrategia de Datos).

**Evaluación de Impacto Algorítmico (EIA)**

* **Definición:** Una práctica preventiva de gobernanza que analiza los posibles riesgos, sesgos y daños de un sistema de IA antes de su implementación.
* **Referencia Principal:** Guía 09 (Gobernanza), Anexo A (Formulación).

**Foso Competitivo (Moat)**

* **Definición:** La ventaja estratégica defendible que una empresa construye con IA. Reside en los datos propietarios (para RAG), los datos de juicio humano (para Ajuste Fino) y la eficiencia de la Gobernanza, no en el modelo LLM.
* **Referencia Principal:** Guía 13 (Estrategia y Valor).

**Framework PPP (Productividad, Proactividad y Personalización)**

* **Definición:** Un framework de Gobernanza y Evaluación para medir la calidad de un agente de IA más allá de la simple eficacia.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Gobernanza de Datos (Data Governance)**

* **Definición:** El marco de políticas para controlar la *fuente* de datos (el "combustible"). Incluye la Catalogación, el Control de Acceso y la Gestión del Ciclo de Vida.
* **Referencia Principal:** Guía 04 (Estrategia de Datos).

**Gobernanza de IA (AI Governance)**

* **Definición:** El marco de políticas, procesos y controles técnicos para gestionar la IA de forma segura, ética y eficiente.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Golden Set Vivo (Living Golden Set)**

* **Definición:** La evolución del *benchmark* tradicional. Un protocolo de evaluación continua donde los fallos de producción (*Edge Cases*) son curados por humanos (S2) y reintegrados automáticamente como nuevas preguntas para el test de regresión del agente.
* **Referencia Principal:** Guía 10 (Evaluación y QA).

**GRC (Gobernanza, Riesgo y Cumplimiento)**

* **Definición:** La tesis central de la obra. El marco estratégico que una organización utiliza para gestionar su Gobernanza (el "cómo" se opera), su Riesgo (el "por qué" se controla) y su Cumplimiento (la "prueba" de que se hace bien).
* **Referencia Principal:** Prólogo, Guía 09, Guía 15.

**Green AI**

* **Definición:** Enfoque de investigación y operación de IA que prioriza la eficiencia energética y la reducción de la huella de carbono, en contraposición a la "Red AI" (que busca precisión pura a cualquier costo computacional).
* **Referencia Principal:** Guía 15 (Ética y Confianza), Guía 12 (ROI).

**Hiper-Personalización**

* **Definición:** Un modelo de negocio habilitado por la IA que permite ofrecer un servicio de "conserje" personalizado a millones de clientes simultáneamente.
* **Referencia Principal:** Guía 13 (Estrategia y Valor).

**Humano-en-el-Bucle (Human-in-the-Loop)**

* **Definición:** Un control de Gobernanza. Es un punto de control obligatorio donde un agente autónomo debe detenerse y pedir validación a un humano antes de ejecutar una acción crítica.
* **Referencia Principal:** Guía 08 (Prototipado), Guía 06 (Sistemas Cognitivos), Guía 15 (Ética).

**IA Corpórea (Embodied AI)**

* **Definición:** La fusión de los LLM (para entender el lenguaje natural) con cuerpos robóticos (para ejecutar acciones físicas en el mundo real).  
* **Referencia Principal:** Guía 17 (Perspectivas).

**IA en la Sombra (Shadow AI)**

* **Definición:** El uso no autorizado de herramientas de IA públicas por parte de empleados para tareas laborales. Es un riesgo de gobernanza principal.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Industrialización (Industrialization)**

* **Definición:** El proceso de llevar un prototipo de IA funcional a un sistema de nivel de producción: escalable, confiable, monitoreado y mantenible.
* **Referencia Principal:** Guía 11 (Industrialización).

**Inferencia (Inference)**

* **Definición:** El momento de ejecución del modelo. Cuando el usuario envía un prompt y el modelo genera una respuesta (costo bajo). Se contrapone al Entrenamiento (costo alto).
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Ingeniería de Contexto (Context Engineering)**

* **Definición:** La disciplina técnica de ensamblar dinámicamente *toda* la información necesaria (instrucciones, herramientas, RAG, memoria y sesión) dentro de la ventana de contexto de un LLM.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Ingeniería de Prompts (Prompt Engineering)**

* **Definición:** La disciplina de diseñar y estructurar instrucciones (prompts) de manera clara y precisa para obtener respuestas controladas.
* **Referencia Principal:** Guía 02 (Ingeniería de Prompts).

**Inyección de Prompts (Prompt Injection)**

* **Definición:** El principal riesgo de seguridad de los LLM. Ocurre cuando un atacante introduce instrucciones ocultas dentro de un prompt legítimo para secuestrar el comportamiento del agente.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Latencia (Latency)**

* **Definición:** Métrica de rendimiento. El tiempo total que tarda el sistema de IA en procesar una solicitud y entregar la respuesta.
* **Referencia Principal:** Guía 10 (Evaluación y QA).

**Lealtad Agéntica (Agentic Loyalty)**

* **Definición:** Un nuevo riesgo de gobernanza para agentes autónomos. El conflicto de interés potencial donde un agente podría priorizar los intereses comerciales de su plataforma sobre los de su usuario.
* **Referencia Principal:** Guía 17 (Perspectivas).

**Ley de Agencia (Agency Law)**

* **Definición:** El marco legal que regula las relaciones donde una persona (Agente) actúa en nombre de otra (Principal). Referencia crítica para la responsabilidad de la IA.
* **Referencia Principal:** Anexo F (Bibliografía).

**Licencia Social (Social License)**

* **Definición:** La aceptación y confianza continua que la sociedad otorga a un proyecto de IA.
* **Referencia Principal:** Guía 15 (Ética y Confianza).

**LLM (Large Language Model)**

* **Definición:** Un modelo de IA entrenado con un volumen masivo de texto. Su función es predecir la siguiente palabra más probable.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos), Guía 02 (Ingeniería de Prompts).

**LLM-como-Juez (LLM-as-a-judge)**

* **Definición:** Táctica de Evaluación donde se usa un LLM de máxima potencia como un "robot de QA" para calificar respuestas.
* **Referencia Principal:** Guía 10 (Evaluación y QA).

**LLM-Ops (Large Language Model Operations)**

* **Definición:** El conjunto de prácticas de ingeniería para gestionar el ciclo de vida completo de las aplicaciones de LLM en producción.
* **Referencia Principal:** Guía 11 (Industrialización).

**LoRA / QLoRA**

* **Definición:** (Low-Rank Adaptation) Técnica de ingeniería para el Ajuste Fino eficiente que entrena solo una pequeña "capa adaptadora".
* **Referencia Principal:** Guía 07 (Ajuste Fino).

**LOSA (Layer of Safety & Alignment)**

* **Definición:** Arquitectura de seguridad propuesta en esta obra. Es una capa *middleware* desacoplada que impone controles de entrada, proceso y salida sobre el modelo para garantizar la gobernanza técnica.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Memoria (vs. RAG)**

* **Definición:** Distinción arquitectónica clave. **RAG** es el "bibliotecario" (hechos externos estáticos), la **Memoria** es el "asistente personal" (contexto del usuario dinámico).
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Memoria Continua (Continuum Memory)**

* **Definición:** Sistema de memoria que permite el acceso y consolidación fluidos a través de múltiples escalas de tiempo.
* **Referencia Principal:** Guía 17 (Perspectivas).

**Metacognición (Metacognition)**

* **Definición:** La capacidad de un sistema (usualmente un Agente Enrutador) para analizar una tarea y decidir qué proceso usar para resolverla.
* **Referencia Principal:** Guía 06 (Sistemas Cognitivos).

**Model Card (Ficha del Motor)**

* **Definición:** Documento técnico que reporta las capacidades de la Fase 1 (Pre-Entrenamiento) de un modelo. Detalla la arquitectura, parámetros, fecha de corte de conocimientos y benchmarks de rendimiento puro. Es esencial para evaluar la viabilidad técnica.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Modelos Open-Source (Ejecución Local)**

* **Definición:** Estrategia de adquisición donde se "compra la máquina". El modelo se ejecuta en infraestructura propia.
* **Referencia Principal:** Guía 14 (Modelos y Mercado).

**Modelos Pequeños (SLMs)**

* **Definición:** (Small Language Models). Modelos diseñados para ejecutarse localmente en dispositivos (On-Device).
* **Referencia Principal:** Guía 17 (Perspectivas).

**Modelos Propietarios (APIs)**

* **Definición:** Estrategia de adquisición donde se "arrienda el cerebro". Se accede al modelo a través de una API.
* **Referencia Principal:** Guía 14 (Modelos y Mercado).

**Multimodalidad (Multimodality)**

* **Definición:** La capacidad de procesar texto, imágenes, audio y video simultáneamente.
* **Referencia Principal:** Guía 17 (Perspectivas), Guía 03 (Contexto y Memoria).

**Observabilidad Ampliada (Expanded Observability)**

* **Definición:** La evolución de la práctica tradicional de Observabilidad. Es la capacidad extendida para monitorear la salud de la decisión cognitiva y la seguridad del resultado (GRC). Captura y registra trazas de razonamiento, costos y calidad a escala industrial.
* **Referencia Principal:** Guía 09 (Gobernanza), Guía 11 (Industrialización).

**Patrones de Razonamiento (Reasoning Patterns)**

* **Definición:** Estructuras de pensamiento algorítmico diseñadas para los agentes (CoT, ReAct, ToT).
* **Referencia Principal:** Guía 06 (Sistemas Cognitivos).

**Pensamiento Algorítmico**

* **Definición:** Habilidad humana de descomponer un problema complejo en una secuencia de pasos lógicos para un Co-Piloto de IA.
* **Referencia Principal:** Guía 16 (Aprender a Pensar).

**Personalización (dentro del Framework PPP)**

* **Definición:** Métrica de calidad que mide la habilidad del agente para adaptar su estilo a las preferencias del usuario.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Portabilidad del Prompt (Prompt Portability)**

* **Definición:** Práctica de ingeniería que busca diseñar instrucciones (prompts) agnósticas al modelo, permitiendo que una misma "fábrica" cognitiva opere con distintos motores (ej. cambiar de GPT-4 a Llama 3) con ajustes mínimos.
* **Referencia Principal:** Guía 11 (Industrialización).

**Post-Entrenamiento (Post-training)**

* **Definición:** La segunda fase del ciclo de vida, donde el "Modelo Base" se refina mediante SFT y RLHF para convertirse en un asistente útil y seguro. Aquí se definen el comportamiento, el tono y los límites de seguridad.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Pre-Entrenamiento (Pre-training)**

* **Definición:** La primera y más costosa fase de creación de una IA, donde el modelo aprende patrones estadísticos a partir de datos masivos para convertirse en un "Modelo Base". En esta etapa, el modelo predice, pero aún no sabe seguir instrucciones.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Proactividad (dentro del Framework PPP)**

* **Definición:** Métrica de calidad que mide la habilidad del agente para gestionar la ambigüedad haciendo preguntas aclaratorias.
* **Referencia Principal:** Guía 09 (Gobernanza).

**Procedencia (de Memoria)**

* **Definición:** El registro del origen y el historial de un recuerdo.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Productividad (dentro del Framework PPP)**

* **Definición:** Métrica *baseline* que mide la eficacia del agente (Tasa de Éxito en la Tarea).
* **Referencia Principal:** Guía 09 (Gobernanza), Guía 10 (Evaluación y QA).

**Prosumer**

* **Definición:** Un "productor" y "consumidor" experto de IA. El "power user" que se convierte en "Co-Piloto Estratégico".
* **Referencia Principal:** Guía 16 (Aprender a Pensar).

**Prompt**

* **Definición:** La instrucción que el usuario proporciona al LLM.
* **Referencia Principal:** Guía 02 (Ingeniería de Prompts).

**Prototipado (Prototyping)**

* **Definición:** Proceso rápido para validar una hipótesis de IA. Su objetivo es "matar malas ideas rápidamente".
* **Referencia Principal:** Guía 08 (Prototipado).

**Quick Win (Victoria Rápida)**

* **Definición:** Caso de uso piloto que busca el **Máximo Valor** con el **Mínimo Riesgo**.
* **Referencia Principal:** Guía 08 (Prototipado).

**RAG (Retrieval-Augmented Generation)**

* **Definición:** Arquitectura que conecta al LLM con una "biblioteca" externa de datos vectorizados para inyectar conocimiento *just-in-time*.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**ReAct (Reason + Act)**

* **Definición:** El "motor" o patrón de razonamiento fundamental de un Agente. Opera en un bucle de Razonamiento + Acción.
* **Referencia Principal:** Guía 05 (Ingeniería de Agentes), Guía 06 (Sistemas Cognitivos).

**Red Teaming**

* **Definición:** Práctica de seguridad ofensiva donde un equipo (humano o automatizado) actúa como adversario simulando ataques contra el modelo. Su objetivo es forzar fallos, lograr *jailbreaks* o generar contenido dañino deliberadamente para identificar y parchar vulnerabilidades antes del despliegue.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Reflexión (Reflection)**

* **Definición:** Patrón de razonamiento donde un agente critica y corrige su propio trabajo.
* **Referencia Principal:** Guía 06 (Sistemas Cognitivos).

**RLAIF (Constitutional AI / AI Feedback)**

* **Definición:** Evolución escalable del RLHF. En lugar de humanos, es otra IA la que supervisa y califica al modelo basándose en una "Constitución" o conjunto de reglas explícitas.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**RLHF (Reinforcement Learning from Human Feedback)**

* **Definición:** Técnica de alineación donde el modelo aprende a preferir ciertas respuestas sobre otras basándose en un sistema de recompensas derivado de la calificación humana. Se usa para ajustar el tono y la seguridad.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Rotura de Contexto (Context Rot)**

* **Definición:** Problema operacional cuando la Ventana de Contexto se sobrecarga y la IA "olvida" instrucciones.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Rúbrica de Evaluación (Evaluation Rubric)**

* **Definición:** Plantilla de calificación usada para medir objetivamente la calidad de la respuesta de un agente.
* **Referencia Principal:** Guía 10 (Evaluación y QA), Anexo D (Plantillas).

**Sesión (de Agente)**

* **Definición:** El "mesón de trabajo" temporal del agente. Contenedor cronológico de una conversación.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**SFT (Supervised Fine-Tuning)**

* **Definición:** "Ajuste Fino Supervisado". Es la técnica de la Fase 2 donde se entrena al modelo con ejemplos de *Instrucción -> Respuesta* escritos por humanos, enseñándole a conversar y seguir órdenes en lugar de solo autocompletar texto.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Sinergia Humano-IA (Human-AI Synergy)**

* **Definición:** Arquitectura de trabajo donde la IA ejecuta el "Sistema 1" y el humano el "Sistema 2".
* **Referencia Principal:** Guía 15 (Ética y Confianza).

**Sistema 1 / Sistema 2**

* **Definición:** Modelo de psicología (Kahneman). S1 es rápido/automático (IA). S2 es lento/analítico (Humano).
* **Referencia Principal:** Guía 15 (Ética y Confianza).

**Sistema Cognitivo (Cognitive System)**

* **Definición:** Sistema de IA que razona, planifica, usa herramientas y aprende, imitando un proceso de pensamiento.
* **Referencia Principal:** Guía 06 (Sistemas Cognitivos).

**Sistema Inmunológico Corporativo**

* **Definición:** Metáfora para describir la resistencia natural de una organización al cambio. Se manifiesta cuando mandos medios sabotean iniciativas de innovación (como la IA) para proteger su estatus, presupuesto o headcount existente.
* **Referencia Principal:** Guía 15 (Ética y Confianza).

**System Card (Ficha de Seguridad)**

* **Definición:** Documento de seguridad que reporta los resultados de la Fase 2 (Post-Entrenamiento). Detalla las pruebas de *Red Teaming*, las tasas de rechazo y los protocolos de alineación utilizados para hacer seguro al modelo. Es esencial para evaluar el cumplimiento normativo.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos).

**Token**

* **Definición:** Unidad fundamental de procesamiento de un LLM.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos), Guía 03 (Contexto).

**Transformer**

* **Definición:** Arquitectura fundamental de la IA generativa actual. Limitada por el Costo Cuadrático y la Amnesia Estática.
* **Referencia Principal:** Guía 01 (Anatomía de Modelos), Guía 03 (Contexto).

**Tree of Thoughts (ToT)**

* **Definición:** Patrón de razonamiento donde el agente explora múltiples caminos paralelos.
* **Referencia Principal:** Guía 06 (Sistemas Cognitivos).

**Triángulo de Adquisición**

* **Definición:** El marco de decisión para elegir un modelo de IA, balanceando tres fuerzas: **Rendimiento** (Potencia), **Costo** (Economía) y **Control** (Soberanía de datos).
* **Referencia Principal:** Guía 14 (Modelos y Mercado).

**Vectorización (Vectorization)**

* **Definición:** Proceso de convertir datos en representaciones numéricas (vectores) para búsqueda semántica (RAG).
* **Referencia Principal:** Guía 04 (Estrategia de Datos), Guía 03 (Contexto).

**Vendor Lock-in (Secuestro del Proveedor)**

* **Definición:** Riesgo estratégico donde una organización se vuelve dependiente de un proveedor único (ej. OpenAI, AWS) debido a que su código o prompts están acoplados a tecnologías propietarias, haciendo el costo de migración prohibitivo.
* **Referencia Principal:** Guía 11 (Industrialización), Guía 14 (Modelos).

**Ventana de Contexto (Context Window)**

* **Definición:** La cantidad máxima de información que el modelo puede "recordar" en una sola conversación.
* **Referencia Principal:** Guía 03 (Contexto y Memoria).

**Vigilante Estratégico**

* **Definición:** El rol permanente del arquitecto de IA que escanea el horizonte en busca de la próxima disrupción tecnológica.
* **Referencia Principal:** Guía 17 (Perspectivas).

**Web Agéntica (Agentic Web)**

* **Definición:** Red interconectada de agentes autónomos que pueden colaborar y negociar tareas entre sí a través de internet.
* **Referencia Principal:** Guía 17 (Perspectivas).

**Zonas de ROI**

* **Definición:** Marco de clasificación financiera para proyectos de IA. Se divide en Zona Verde (Ganadores), Amarilla (Tácticos), Naranja (Vanidosos) y Roja (Destrucción de Valor).
* **Referencia Principal:** Guía 12 (ROI Financiero).

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="./D-Plantillas-Recursos.html">« Anexo D</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
  <div>
    <a href="./F-Bibliografia.html">Anexo F »</a>
  </div>
</div>