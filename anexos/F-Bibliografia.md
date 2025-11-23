## Anexo F: Bibliografía Fundamental

Subtítulo: Lecturas Clave para el Arquitecto y el Vigilante Estratégico

### Introducción: Las Fuentes del Criterio

Este anexo no es una lista exhaustiva, sino un conjunto curado de lecturas fundacionales. Su objetivo es proporcionar al "Arquitecto" y al "Vigilante Estratégico" las fuentes primarias sobre las que se construye el "criterio" de esta obra.

---

### Sobre el Bloque 1: Los Fundamentos

*(Ingeniería de Prompts, Contexto y Datos)*

* **Vaswani, A., et al. (2017). "Attention Is All You Need".** 
  * **Por qué leerlo:** Es el *paper* seminal que introdujo la arquitectura "Transformer", el motor fundamental de todos los LLM modernos que se discuten en esta obra.  
* **Lewis, P., et al. (2020). "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks".** 
  * **Por qué leerlo:** Es el *paper* que introduce formalmente la arquitectura **RAG**, la solución técnica clave para el problema de la "Ventana de Contexto" discutido en la Guía 02.  
* **Hu, E., et al. (2021). "LoRA: Low-Rank Adaptation of Large Language Models".**
  * **Por qué leerlo:** Es el paper técnico seminal que introduce LoRA (Low-Rank Adaptation), la técnica de ingeniería clave definida en el Anexo 07 (Glosario). Proporciona el fundamento de ingeniería esencial para el Anexo 05: Ajuste Fino y Adaptación de Modelos.
* **Boonstra, L. (Febrero 2025). "Prompt Engineering".**
  * **Por qué leerlo:** Es el whitepaper técnico que define la disciplina de la Ingeniería de Prompts (Guía 01). Detalla las técnicas fundamentales como zero-shot , few-shot , role prompting y los patrones de razonamiento como Chain-of-Thought y ReAct  que son la base del "Método de 7 Pasos".
* **Milam, K., & Gulli, A. (Noviembre 2025). "Context Engineering: Sessions, Memory".**
  * **Por qué leerlo:** El *whitepaper* fundacional de Google que define la "Ingeniería de Contexto" (la evolución de la Ingeniería de Prompts). Proporciona el "criterio de arquitecto" clave para diferenciar **RAG** (el "bibliotecario" experto en hechos) de la **Memoria** (el "asistente personal" experto en el usuario).
* **Gobierno de Chile. (1999). "Ley N° 19.628 sobre protección de la vida privada".**
  * **Por qué leerlo:** Es el pilar legal de la **Gobernanza de Datos** (Guía 03) en Chile. Define "dato personal" y "dato sensible", estableciendo la base legal de la "Estrategia de Datos".  
* **Cavoukian, A. (2009). "Privacy by Design: The 7 Foundational Principles".** 
  * **Por qué leerlo:** Establece el marco internacional para la "Privacidad desde el Diseño" y "por Defecto", un concepto central de la "Guía Ética" (BID/UAI) para la formulación de proyectos.

---

### Sobre el Bloque 2: La Construcción

*(Ingeniería de Agentes, Sistemas Cognitivos y Prototipado)*

* **Wei, J., et al. (2022). "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models".** 
  * **Por qué leerlo:** Es la investigación clave que demuestra cómo forzar a un LLM a "pensar paso a paso", introduciendo el patrón de razonamiento **Chain of Thought (CoT)** (Guía 05).  
* **Yao, S., et al. (2022). "ReAct: Synergizing Reasoning and Acting in Language Models".** 
  * **Por qué leerlo:** Introduce el **Ciclo ReAct (Reason \+ Act)**, el "motor" fundamental de los **Agentes** (Guía 04\) que les permite usar "Herramientas".  
* **Yao, S., et al. (2023). "Tree of Thoughts: Deliberate Problem Solving with Large Language Models".** 
  * **Por qué leerlo:** Define el patrón de razonamiento avanzado **Tree of Thoughts (ToT)** (Guía 05), que permite a los agentes explorar múltiples caminos de solución.
* **Wiesinger, J., Marlow, P., & Vuskovic, V. (Septiembre 2024). "Agents".**
  * **Por qué leerlo:** Es el whitepaper conceptual que introduce la arquitectura de un Agente (Guía 04) como la composición de un Modelo (el cerebro), Herramientas (las manos) y una Capa de Orquestación (el ciclo de razonamiento). Distingue formalmente entre "Modelos" (solo predicen) y "Agentes" (toman acciones).
* **Gulli, A., et al. (Febrero 2025). "Agents Companion".**
  * **Por qué leerlo:** Es el "102" de las guías de construcción. Define formalmente la arquitectura de un Agente (Guía 04) como la combinación de Modelo, Herramientas y Orquestación. Explora los Sistemas Cognitivos (Guía 05) a través de patrones de "múltiples agentes" (jerárquicos, colaborativos) y detalla la Evaluación de Agentes (Guía 08), incluyendo la evaluación de trayectoria y el Human-in-the-Loop.

---

### Sobre el Bloque 3: La Operación

*(Gobernanza, Evaluación e Industrialización)*

* **Gobierno de Chile. (2008). "Ley N° 20.285 sobre acceso a la información pública".** 
  * **Por qué leerlo:** Es el fundamento legal de la **Transparencia y Rendición de Cuentas** (Accountability) en el sector público, un pilar de la **Gobernanza de IA** (Guía 07).  
* **Burrell, J. (2016). "How the machine 'thinks': Understanding opacity in machine learning algorithms".** 
  * **Por qué leerlo:** Define los tres tipos de **Opacidad** (intrínseca, intencional, analfabeta), que justifican la necesidad de la **Observabilidad** (Guía 07 y Guía 09).  
* **Zheng, L., et al. (2023). "Judging LLM-as-a-judge with MT-Bench and Chatbot Arena".** 
  * **Por qué leerlo:** Proporciona el fundamento técnico y las métricas para la "Evaluación Asistida por IA" (el **"LLM Juez"**), un concepto central de la **Guía 08: Evaluación**.
* **Google. (2023-2024). "Secure AI Framework (SAIF)".**
  * **Por qué leerlo:** Es el marco de seguridad fundamental de Google (referenciado en el whitepaper "Prototype to Production") que aborda la seguridad de la IA en la infraestructura y el producto. Proporciona un respaldo conceptual clave para la Gobernanza (Guía 07) y la Industrialización (Guía 09).
* **Huyen, Chip (2024). "AI Engineering".** 
  * **Por qué leerlo:** Es el complemento técnico directo de esta obra. Si este libro es el "tratado de criterio" (qué y por qué), "AI Engineering" es el manual de "industrialización" (el cómo). Detalla la implementación de ingeniería para Agentes, RAG, Evaluación y "Guardrails" (Gobernanza) en producción.
* **Kartakis, S., et al. (Noviembre 2025). "Prototype to Production".**
  * **Por qué leerlo:** Es el manual de "AgentOps" que fundamenta la Guía 09: Industrialización. Detalla el "último tramo" para mover un prototipo (Guía 06) a un sistema de producción robusto. Se enfoca en los pilares de la industrialización: Evaluación como compuerta de calidad, Pipelines de CI/CD y Observabilidad (costos, latencia y seguridad).

---

### Sobre el Bloque 4: El Impacto

*(Humanidad, Ética, Estrategia y Valor)*

* **Challapally, A., et al. (Julio 2025). "The GenAI Divide: State of AI in Business 2025". MIT / Project NANDA.** 
  * **Por qué leerlo:** Es el informe de mercado clave de 2025. Proporciona los datos estadísticos que validan la tesis de esta obra: la **"Brecha GenAI"** (el 95% de las empresas con ROI cero). Define los conceptos de **"Shadow AI"** (IA en la sombra), **"Prosumers"** (usuarios expertos) y la superioridad de la estrategia "Comprar" vs. "Construir", que son fundamentales para la Gobernanza (Guía 07), la Sinergia (Guía 11) y la Estrategia (Guía 12). 
* **Singla, A., Sukharevsky, A., Yee, L., & Chui, M. (Noviembre 2025). "The state of AI in 2025: Agents, innovation, and transformation". QuantumBlack, AI by McKinsey.**
  * **Por qué leerlo:** Valida estadísticamente la "Brecha de Escalamiento", demostrando que la mayoría de las empresas están atascadas en pilotaje y no logran impacto en el EBIT . Identifica la "validación humana" y el enfoque en la "innovación" como los diferenciadores clave de los "high performers".
* **Kahneman, D. (2011). "Thinking, Fast and Slow".** 
  * **Por qué leerlo:** Es la fuente del marco **"Sistema 1 / Sistema 2"**, el pilar conceptual de la **Guía 10 (Sinergia Humano-IA)** para la división del trabajo cognitivo.  
* **Heath, C., & Heath, D. (2010). "Switch: How to Change Things When Change Is Hard".** 
  * **Por qué leerlo:** Es el manual práctico para la **gestión del cambio**. Mientras Kahneman *diagnostica* el conflicto cognitivo (S1/S2), "Switch" (Jinete/Elefante/Camino) proporciona el *método* para implementarlo. Esencial para ejecutar la **Guía 10**, gestionar la resistencia cultural y lograr la "Licencia Social".  
* **Gobierno de Chile (BID Lab, Gob Digital, UAI). (2022). "Guía Formulación ética de proyectos de ciencia de datos".** 
  * **Por qué leerlo:** Proporciona el **marco legal y fundacional chileno** (Leyes 19.628, 20.285, 20.609) para la ética de datos, la transparencia y la no discriminación. Define los conceptos clave de **"Opacidad"** y **"Licencia Social"** en el contexto del sector público.  
* **Angwin, J., Larson, J., Mattu, S., & Kirchner, L. (2016). "Machine Bias". ProPublica.** 
  * **Por qué leerlo:** Una investigación periodística fundamental que expone los **sesgos y la discriminación** en los algoritmos de predicción, justificando la **Guía 03** y la **Brújula Ética** (Guía 10).  
* **Buolamwini, J., & Gebru, T. (2018). "Gender shades: Intersectional accuracy disparities..."** 
  * **Por qué leerlo:** La investigación seminal que demostró **sesgos masivos** en los sistemas de reconocimiento facial, un caso de uso clave de la "Guía Ética" (BID/UAI).  
* **Data Futures Partnership (2017). "A Path to Social Licence: Guidelines for Trusted Data Use".**
  * **Por qué leerlo:** Define el concepto de **"Licencia Social"**, un requisito ético central (Guía 10\) y de la "Guía Ética" (BID/UAI) para la aceptación pública.  
* **Gobierno de Chile. (2012). "Ley N° 20.609 que establece medidas contra la discriminación".** 
  * **Por qué leerlo:** Proporciona la definición legal de **"discriminación arbitraria"** y las categorías protegidas, el "guardarraíl" legal para la **Guía 08 (Evaluación)** y la **Guía 10 (Ética)**.
* **Unión Europea. (2024). "Reglamento del Parlamento Europeo [...] por el que se establecen normas armonizadas en materia de inteligencia artificial (Ley de Inteligencia Artificial)".**
  * **Por qué leerlo:** Es el primer marco regulatorio integral de IA del mundo. Proporciona el fundamento legal que convierte la **Gobernanza** (Guía 07), la **Evaluación** (Guía 08) y la **Gobernanza de Datos** (Guía 03) de "mejores prácticas" en "obligaciones legales" para sistemas de alto riesgo.

---

### Sobre el Bloque 5: La Expansión

*(Perspectivas, Futuro y el Rol del "Vigilante Estratégico")*

* **Tendencia 1: La Explosión de la Multimodalidad** 
  * **Google DeepMind (2025). "Gemini 3 Pro Model Card".** 
    * **Por qué leerlo:** El documento técnico oficial que detalla la arquitectura multimodal nativa y las capacidades de razonamiento ("Deep Think") del modelo Gemini 3, validando las capacidades descritas en la Guía 13 y superando a los reportes de 2024.
  * **OpenAI / Anthropic (2025). "System Cards: GPT-5 and Claude 4".** 
    * **Por qué leerlo:** Detallan la implementación a escala industrial y sus nuevos y complejos **riesgos de gobernanza** (ej. desinformación audiovisual, razonamiento autónomo).

* **Tendencia 2: IA en el Dispositivo (SLMs)** 
  * **Microsoft / Apple / Meta (2025). "Technical Reports: Phi-4, Llama 4-8B, and On-Device Core Intelligence".** 
     * **Por qué leerlo:** Los *papers* de 2024 (Phi-3) fueron pruebas de concepto. Los reportes de 2025 demuestran la *madurez* de los SLMs. Son la referencia clave para el "Control" (Soberanía de Datos) y el "Costo" (Latencia Cero) del **Triángulo de Adquisición** (Anexo 03).

* **Tendencia 3: De Agentes-Herramienta a Agentes Autónomos** 
  * **Anthropic. (Noviembre 2025). "Disrupting the first reported AI-orchestrated cyber espionage campaign".**
    * **Por qué leerlo:** Detalla el incidente GTG-1002. Proporciona la evidencia empírica de que la "lealtad del agente" es al prompt y no al usuario, validando el riesgo central de la autonomía sin supervisión.
  * **Riedl, M. O., & Desai, D. R. (Agosto 2025). "AI Agents and the Law". arXiv.**
    * **Por qué leerlo:** Un análisis crítico que conecta la ingeniería con la "Ley de Agencia". Identifica el "Problema de la Lealtad" (¿para quién trabaja el agente?) y propone deberes fiduciarios para la IA.
  * **Cognition Labs / Adept (2025). "Frameworks for Reliable Autonomous Agents in Production".** 
    * **Por qué leerlo:** El *paper* "Generative Agents" (2023) fue una simulación académica. Los *white papers* de 2025 (de las startups que lideran esta área) describen las arquitecturas de **Gobernanza** (Guía 07\) necesarias para desplegar agentes autónomos *en el mundo real*.  

* **Tendencia 4: La Web Agéntica (El Ecosistema)**
  * **Google. (Noviembre 2025). "Google Antigravity: A platform for autonomous agents".**
    * **Por qué leerlo:** El *white paper* de lanzamiento de la plataforma que habilita la orquestación de agentes a escala global. Es la referencia técnica para entender cómo los agentes saldrán de la "intranet" corporativa a la "web abierta".
  * **Anthropic. (2025). "The Model Context Protocol (MCP): Standardizing Agent Interoperability".**
    * **Por qué leerlo:** Define el estándar técnico que permite a los agentes conectarse con sistemas de datos de forma universal, la "tubería" esencial de la Web Agéntica.

* **Tendencia 5: IA Corpórea (Embodied AI)** 
  * **LeCun, Y. / AMI (Noviembre 2025). "Advanced Machine Intelligence: World Models for Physical Understanding".**
    * **Por qué leerlo:** El manifiesto de la nueva startup de Yann LeCun. Explica por qué los LLM actuales no sirven para la robótica y propone "Modelos de Mundo" que entienden física y causalidad, respondiendo técnicamente a la crítica filosófica de Dreyfus.
  * **Figure AI / Boston Dynamics (2025). "Fleet Learning: Bridging Vision-Language-Action Models".** 
    * **Por qué leerlo:** Demuestra la fusión práctica de la multimodalidad (visión) con la acción física (robótica).

* **Tendencia 6: Más Allá del Transformer (Aprendizaje Continuo)** 
  * **Dao, T., et al. (2025). "Mamba-2 and State Space Models: Production-Scale Efficiency".** 
    * **Por qué leerlo:** Es el paper de referencia para las arquitecturas **no-Transformers** (SSMs) que resuelven el **Costo Cuadrático** (Guía 02), permitiendo eficiencia a escala y costo lineal.
  * **Behrouz, A., et al. (2025). "Nested Learning: The Illusion of Deep Learning Architectures".**
    * **Por qué leerlo:** Aborda el segundo límite del Transformer (Guía 02): la **Amnesia Estática**. Introduce el paradigma del "Aprendizaje Anidado" y prototipos capaces de auto-modificación, clave para el "Vigilante Estratégico".

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="./E-Glosario.md">« Anexo E</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
</div>