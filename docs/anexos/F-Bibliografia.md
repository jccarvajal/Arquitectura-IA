## Anexo F: Bibliografía Fundamental

Subtítulo: Lecturas Clave para el Arquitecto y el Vigilante Estratégico

### Introducción: Las Fuentes del Criterio

Este anexo no es una lista exhaustiva, sino un conjunto curado de lecturas fundacionales. Su objetivo es proporcionar al "Arquitecto" y al "Vigilante Estratégico" las fuentes primarias sobre las que se construye el "criterio" de esta obra.

---

### Sobre el Bloque 1: Los Fundamentos

*(Ingeniería de Prompts, Contexto y Datos)*

* **Goodfellow, I., Bengio, Y., & Courville, A. (2016). "Deep Learning". MIT Press.** [[Web]](https://www.deeplearningbook.org/)
    * **Por qué leerlo:** Es la "biblia" técnica que define formalmente la jerarquía: Inteligencia Artificial (la meta) > Machine Learning (la técnica) > Deep Learning (la arquitectura de redes neuronales que hace posible la IA moderna).
* **Vaswani, A., et al. (2017). "Attention Is All You Need".** [[PDF]](https://arxiv.org/abs/1706.03762)
    * **Por qué leerlo:** Es el *paper* seminal que introdujo la arquitectura "Transformer", el motor fundamental de todos los LLM modernos que se discuten en esta obra.
* **Lewis, P., et al. (2020). "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks".** [[PDF]](https://arxiv.org/abs/2005.11401)
    * **Por qué leerlo:** Es el *paper* que introduce formalmente la arquitectura **RAG**, la solución técnica clave para el problema de la "Ventana de Contexto" discutido en la Guía 03.
* **Hu, E., et al. (2021). "LoRA: Low-Rank Adaptation of Large Language Models".** [[PDF]](https://arxiv.org/abs/2106.09685)
    * **Por qué leerlo:** Introduce LoRA, la técnica de ingeniería clave para el **Ajuste Fino** (Guía 07) eficiente, permitiendo adaptar modelos masivos con recursos limitados.
* **Boonstra, L. (Febrero 2025). "Prompt Engineering Guide".** [[Web]](https://www.kaggle.com/whitepaper-prompt-engineering)
    * **Por qué leerlo:** Es el whitepaper técnico que define la disciplina de la Ingeniería de Prompts (Guía 02). Detalla las técnicas fundamentales como zero-shot, few-shot, role prompting y los patrones de razonamiento como Chain-of-Thought y ReAct.
* **Milam, K., & Gulli, A. (Noviembre 2025). "Context Engineering: Sessions, Memory".** [[Web]](https://www.kaggle.com/whitepaper-context-engineering-sessions-and-memory)
    * **Por qué leerlo:** El *whitepaper* fundacional que define la "Ingeniería de Contexto". Proporciona el "criterio de arquitecto" clave para diferenciar **RAG** (el "bibliotecario" experto en hechos) de la **Memoria** (el "asistente personal" experto en el usuario).
* **Gobierno de Chile. (1999). "Ley N° 19.628 sobre protección de la vida privada".** [[Web]](https://www.bcn.cl/leychile/navegar?idNorma=141599)
    * **Por qué leerlo:** Es el pilar legal de la **Gobernanza de Datos** (Guía 04) en Chile. Define "dato personal" y "dato sensible", estableciendo la base legal de la "Estrategia de Datos".
* **Cavoukian, A. (2009). "Privacy by Design: The 7 Foundational Principles".** [[PDF]](https://iapp.org/media/pdf/resource_center/pbd_implement_7found_principles.pdf)
    * **Por qué leerlo:** Establece el marco internacional para la "Privacidad desde el Diseño" y "por Defecto", un concepto central de la "Guía Ética" (BID/UAI) para la formulación de proyectos.
* **Souly, A., et al. (2025). "Poisoning Attacks on LLMs Require a Near-Constant Number of Poison Samples". arXiv.** [[WEB]](http://arxiv.org/abs/2510.07192)
    * **Por qué leerlo:** El estudio técnico citado en el reporte internacional que demuestra la fragilidad de los modelos ante ataques de envenenamiento de datos con muy pocos recursos (aprox. 250 muestras). Fundamental para justificar la **Gobernanza de la Fuente** en la Guía 04.
* **Laboratorio de Gobierno & UAI. (2022). "Guía Permitido Innovar: ¿Cómo podemos desarrollar proyectos de ciencia de datos?".** [[Web]](https://lab.gob.cl/permitido-innovar)
    * **Por qué leerlo:** Provee herramientas prácticas universales para la etapa de fundamentación, destacando la "Matriz de Madurez de Datos" (evaluación de calidad, acceso y privacidad de la fuente) y el análisis de pre-factibilidad PESTL.
  
---

### Sobre el Bloque 2: La Construcción

*(Ingeniería de Agentes, Sistemas Cognitivos y Prototipado)*

* **Wei, J., et al. (2022). "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models".** [[PDF]](https://arxiv.org/abs/2201.11903)
    * **Por qué leerlo:** Investigación clave que demuestra cómo forzar a un LLM a "pensar paso a paso", introduciendo el patrón de razonamiento **Chain of Thought (CoT)** (Guía 06).
* **Yao, S., et al. (2022). "ReAct: Synergizing Reasoning and Acting in Language Models".** [[PDF]](https://arxiv.org/abs/2210.03629)
    * **Por qué leerlo:** Introduce el **Ciclo ReAct (Reason + Act)**, el "motor" fundamental de los **Agentes** (Guía 05) que les permite usar "Herramientas".
* **Yao, S., et al. (2023). "Tree of Thoughts: Deliberate Problem Solving with Large Language Models".** [[PDF]](https://arxiv.org/abs/2305.10601)
    * **Por qué leerlo:** Define el patrón de razonamiento avanzado **Tree of Thoughts (ToT)** (Guía 06), que permite a los agentes explorar múltiples caminos de solución.
* **Wiesinger, J., Marlow, P., & Vuskovic, V. (Septiembre 2024). "Agents".** [[Web]](https://www.kaggle.com/whitepaper-agents)
    * **Por qué leerlo:** Whitepaper conceptual que introduce la arquitectura de un Agente (Guía 05) como la composición de un Modelo (el cerebro), Herramientas (las manos) y una Capa de Orquestación.
* **Gulli, A., et al. (Febrero 2025). "The Agents Companion".** [[Web]](https://www.kaggle.com/whitepaper-agent-companion)
    * **Por qué leerlo:** Es la profundización técnica de las guías de construcción. Explora patrones de "múltiples agentes" (jerárquicos, colaborativos) y detalla la Evaluación de Agentes (Guía 10).
* **Baker, B., et al. (OpenAI). (2025). "Monitoring Reasoning Models for Misbehavior and the Risks of Promoting Obfuscation".** [[Web]](https://arxiv.org/abs/2503.11926)
    * **Por qué leerlo:** Profundiza en los desafíos de supervisar modelos que "piensan" (CoT), advirtiendo sobre cómo una mala supervisión puede incentivar al modelo a ocultar sus verdaderos razonamientos. Lectura clave para la Guía 11.

---

### Sobre el Bloque 3: La Operación

*(Gobernanza, Evaluación e Industrialización)*

* **Gobierno de Chile. (2008). "Ley N° 20.285 sobre acceso a la información pública".** [[Web]](https://www.bcn.cl/leychile/navegar?idNorma=276363)
    * **Por qué leerlo:** Es el fundamento legal de la **Transparencia y Rendición de Cuentas** en el sector público, un pilar de la **Gobernanza de IA** (Guía 09).
* **Burrell, J. (2016). "How the machine 'thinks': Understanding opacity in machine learning algorithms".** [[PDF]](https://journals.sagepub.com/doi/abs/10.1177/2053951715622512)
    * **Por qué leerlo:** Define los tres tipos de **Opacidad** (intrínseca, intencional, analfabeta), que justifican la necesidad de la **Observabilidad** (Guía 09 y Guía 11).
* **Zheng, L., et al. (2023). "Judging LLM-as-a-judge with MT-Bench and Chatbot Arena".** [[PDF]](https://arxiv.org/abs/2306.05685)
    * **Por qué leerlo:** Proporciona el fundamento técnico para la "Evaluación Asistida por IA" (el **"LLM Juez"**), un concepto central de la **Guía 10: Evaluación**.
* **Google. (2024). "Secure AI Framework (SAIF)".** [[Web]](https://safety.google/cybersecurity-advancements/saif/)
    * **Por qué leerlo:** Marco de seguridad fundamental que aborda la protección de la IA en la infraestructura y el producto. Respaldo conceptual para la Gobernanza (Guía 09).
* **ISO/IEC. (2023). "ISO/IEC 42001:2023 Information technology — Artificial intelligence — Management system".** [[Web]](https://www.iso.org/standard/81230.html)
    * **Por qué leerlo:** Es el primer estándar internacional certificable para sistemas de gestión de IA. Referencia técnica definitiva para operacionalizar el marco GRC.
* **Huyen, Chip (2024). "AI Engineering".** [[Web]](https://www.oreilly.com/library/view/ai-engineering/9781098166298/)
    * **Por qué leerlo:** Complemento técnico directo de esta obra. Detalla la implementación de ingeniería para Agentes, RAG y "Guardrails" en producción.
* **Kartakis, S., et al. (Noviembre 2025). "Prototype to Production".** [[Web]](https://www.kaggle.com/whitepaper-prototype-to-production)
    * **Por qué leerlo:** Manual de "AgentOps" que fundamenta la **Guía 11: Industrialización**. Detalla CI/CD y Observabilidad para agentes.
* **Zaharia, M., et al. (Berkeley AI Research). (2024). "The Shift from Models to Compound AI Systems".** [[Web]](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/)
    * **Por qué leerlo:** Paper visionario que valida la tesis de la **Guía 11**. Argumenta que el "Estado del Arte" ya no se logra con un mejor modelo, sino con un mejor *sistema* (componentes modulares, RAG, herramientas), justificando la necesidad de **Portabilidad** y arquitectura sobre la elección del motor.
* **Department for Science, Innovation and Technology (DSIT). (2025). "International AI Safety Report: Second Key Update". UK Government.** [[Web]](https://www.gov.uk/government/publications/international-ai-safety-report-2025)
    * **Por qué leerlo:** Es la auditoría global del estado de la seguridad en IA a fines de 2025. Valida la necesidad de la "Defensa en Profundidad" (LOSA), cuantifica el riesgo de *Data Poisoning* y establece el estándar para el monitoreo de agentes autónomos.
* **Sun, W., et al. (2025). "Training Proactive and Personalized LLM Agents". arXiv.** [[Web]](https://arxiv.org/abs/2511.02208)
    * **Por qué leerlo:** Estudio que fundamenta el marco de gobernanza de calidad para agentes en la **Guía 09**, proponiendo el equilibrio entre **Productividad**, **Proactividad** y **Personalización**.
* **Zou, A., et al. (2023). "Universal and Transferable Adversarial Attacks on Aligned Language Models". arXiv.** [[PDF]](https://arxiv.org/abs/2307.15043)
    * **Por qué leerlo:** El estudio que demostró que *cualquier* modelo (incluso los más seguros) puede ser "hackeado" mediante sufijos adversarios universales. Es la prueba científica definitiva de que la seguridad no puede delegarse al modelo, justificando la necesidad de una capa externa (**LOSA**) en la **Guía 09**.
* **Consejo para la Transparencia (CPLT). (Junio 2025). "Guía para la adopción de las Recomendaciones sobre Transparencia Algorítmica".** [[PDF]](https://www.consejotransparencia.cl/wp-content/uploads/page/2024/05/GUIA-Transparencia-Algoritmica-junio-2025.pdf)
    * **Por qué leerlo:** Define la taxonomía técnica de publicación de algoritmos. **Para el Sector Público:** Es el manual de cumplimiento obligatorio. **Para el Sector Privado:** Es el mejor *benchmark* disponible para estructurar políticas de transparencia corporativa y ESG.
* **Shaib, C., et al. (2025). "Learning the Wrong Lessons: Syntactic-Domain Spurious Correlations in Language Models". NeurIPS 2025.** [[PDF]](http://arxiv.org/abs/2509.21155v2)
    * **Por qué leerlo:** Es un estudio clave que demuestra cómo la **sintaxis** puede anular la **semántica**, creando una nueva vulnerabilidad de seguridad que permite *bypass* (saltarse) las negativas éticas del modelo (*jailbreaks*). Es la prueba científica de que la seguridad no puede delegarse al LLM, justificando la arquitectura **LOSA** y el **Monitoreo de CoT** (Guía 09, 11).
* **UiPath (2024). "The Future of Automation: Integrating GenAI with RPA". Whitepaper.** [[Web]](https://www.uipath.com/resources/whitepapers)
    * **Por qué leerlo:** Fundamenta la necesidad técnica de mantener herramientas de RPA (robots que hacen clics) para conectar la IA moderna con la infraestructura bancaria y gubernamental antigua ("Legacy") que no tiene APIs.

---

### Sobre el Bloque 4: El Impacto

*(Humanidad, Ética, Estrategia y Valor)*

* **Challapally, A., et al. (Julio 2025). "The GenAI Divide: State of AI in Business 2025". MIT / Project NANDA.** [[PDF]](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf)
    * **Por qué leerlo:** Es el informe de mercado clave de 2025. Proporciona los datos estadísticos que validan la tesis de esta obra: la **"Brecha GenAI"** (el 95% de las empresas con ROI cero). Define los conceptos de **"Shadow AI"** (IA en la sombra), **"Prosumers"** (usuarios expertos) y la superioridad de la estrategia "Comprar" vs. "Construir", que son fundamentales para la Gobernanza (Guía 09), la Sinergia (Guía 15) y la Estrategia (Guía 13).
* **Singla, A., et al. (Noviembre 2025). "The state of AI in 2025". McKinsey.** [[Web]](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)
    * **Por qué leerlo:** Valida la "Brecha de Escalamiento" e identifica la "validación humana" como diferenciador clave de los *high performers*.
* **Kahneman, D. (2011). "Thinking, Fast and Slow".** [[Web]](https://us.macmillan.com/books/9780374533557/thinkingfastandslow)
    * **Por qué leerlo:** Fuente del marco **"Sistema 1 / Sistema 2"**, pilar conceptual de la **Sinergia Humano-IA** (Guía 15).
* **Dreyfus, H. L. (1992). "What Computers Still Can't Do: A Critique of Artificial Reason".** [[Web]](https://mitpress.mit.edu/9780262540674/what-computers-still-cant-do/)
    * **Por qué leerlo:** Base filosófica del Prólogo. Argumenta por qué la inteligencia sin "cuerpo" es distinta a la humana.
* **Taleb, N. N. (2012). "Antifragile: Things That Gain from Disorder".** [[Web]](https://www.penguinrandomhouse.com/books/176227/antifragile-by-nassim-nicholas-taleb/)
    * **Por qué leerlo:** Define **Fragilidad** y **Skin in the Game** (Prólogo). Esencial para entender el riesgo de sistemas sin consecuencias.
* **Heath, C., & Heath, D. (2010). "Switch: How to Change Things When Change Is Hard".** [[Web]](https://heathbrothers.com/books/switch/)
    * **Por qué leerlo:** Manual práctico para la **gestión del cambio**, esencial para ejecutar la Guía 15 y gestionar la resistencia cultural.
* **Gobierno de Chile (BID Lab, UAI). (2022). "Guía Formulación ética de proyectos de ciencia de datos".** [[Web]](https://goblab.uai.cl/guia-formulacion-etica-de-proyectos-de-ciencia-de-datos/)
    * **Por qué leerlo:** Marco legal para la ética de datos, definiendo **"Opacidad"** y **"Licencia Social"**.
* **Angwin, J., et al. (2016). "Machine Bias". ProPublica.** [[Web]](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing)
    * **Por qué leerlo:** Investigación que expone los **sesgos** en algoritmos, justificando la **Brújula Ética**.
* **Buolamwini, J., & Gebru, T. (2018). "Gender Shades".** [[PDF]](http://gendershades.org/overview.html)
    * **Por qué leerlo:** Investigación seminal sobre **sesgos en reconocimiento facial**.
* **Data Futures Partnership (2017). "A Path to Social Licence: Guidelines for Trusted Data Use".** [[PDF]](https://aisp.upenn.edu/wp-content/uploads/2019/08/Trusted-Data-Use_2017.pdf)
    * **Por qué leerlo:** Define el concepto de **"Licencia Social"**, requisito ético central de la Guía 15. Establece que la confianza no es un estado permanente, sino un permiso que se renueva continuamente mediante la transparencia y el valor compartido.
* **Gobierno de Chile. (2012). "Ley N° 20.609 que establece medidas contra la discriminación".** [[Web]](https://www.bcn.cl/leychile/navegar?idNorma=1042092)
    * **Por qué leerlo:** Proporciona la definición legal de **"discriminación arbitraria"**.
* **Unión Europea. (2024). "Reglamento de Inteligencia Artificial (AI Act)".** [[Web]](https://artificialintelligenceact.eu/)
    * **Por qué leerlo:** Primer marco regulatorio integral que convierte la Gobernanza y Evaluación en obligaciones legales.
* **Strubell, E., Ganesh, A., & McCallum, A. (2019). "Energy and Policy Considerations for Deep Learning in NLP".** [[PDF]](https://arxiv.org/abs/1906.02243)
    * **Por qué leerlo:** El estudio fundacional que puso número a la huella de carbono de la IA. Reveló que entrenar un modelo grande puede emitir tanto CO2 como 5 coches en toda su vida útil. Lectura obligatoria para justificar el riesgo de **"Green AI"** en la **Guía 15**.
* **Gilley, A., Godek, M., & Gilley, J. W. (2009). "Change, Resistance, and the Organizational Immune System".** [[Web]](https://www.researchgate.net/publication/211386571_Change_Resistance_and_the_Organizational_Immune_System)
    * **Por qué leerlo:** Provee la base teórica para entender por qué las organizaciones atacan la innovación interna, validando tu sección sobre la **"Gestión del Sabotaje"** en la **Guía 15**.
* **Google Cloud. (Octubre 2025). "101 Real-World Gen AI Use Cases from Industry Leaders".** [[Web]](https://cloud.google.com/transform/101-real-world-generative-ai-use-cases-from-industry-leaders)
    * **Por qué leerlo:** Es la validación empírica definitiva del manuscrito. Confirma la transición de Chatbots a Agentes, valida los Blueprints de Soporte, Legal y Datos con casos de éxito reales (Toyota, Mercari, Freshfields) y respalda el modelo de ROI de la Guía 12 con cifras auditadas.
* **Dirección de Compras y Contratación Pública (ChileCompra). (Dic 2023). "Directiva N°44: Recomendaciones para la adquisición de proyectos de Ciencia de Datos e IA".** [[PDF]](https://www.chilecompra.cl/wp-content/uploads/2023/12/Directiva-Recomendaciones-proyectos-Ciencia-Datos-IA.pdf)
    * **Por qué leerlo:** Un modelo robusto para la contratación de tecnología (Guía 14). Ofrece cláusulas tipo para proteger la propiedad intelectual, exigir explicabilidad ("caja blanca") y definir niveles de servicio (SLA) en proyectos de IA.
* **División de Gobierno Digital & UAI. (2022). "Guía de Formulación Ética de Proyectos de Ciencia de Datos".** [[Web]](h[ttps://digital.gob.cl](https://goblab.uai.cl/guia-formulacion-etica-de-proyectos-de-ciencia-de-datos/))
    * **Por qué leerlo:** Marco de referencia esencial para la Guía 15. Define operacionalmente la "Licencia Social", la proporcionalidad en el uso de IA y los protocolos para mitigar sesgos en datos administrativos.
* **Innerarity, D. (2023). "Una teoría crítica de la inteligencia artificial". Galaxia Gutenberg.** [[Web]](https://www.galaxiagutenberg.com/libros/una-teoria-critica-de-la-inteligencia-artificial/)
    * **Por qué leerlo:** Es la base filosófica de la **"Construcción de la Agencia"** (Conclusión). Innerarity argumenta que la IA no es una inteligencia que compite con la humana, sino una herramienta de gestión de la complejidad, y que el verdadero peligro es la "abdicación" del juicio humano frente al cálculo algorítmico.
  
---

### Sobre el Bloque 5: La Expansión

*(Perspectivas, Futuro y el Rol del "Vigilante Estratégico")*

* **Tendencia 1: La Explosión de la Multimodalidad (Model Cards y System Cards)**
    * **Google DeepMind (2025). "Gemini 3 Pro Model Card".** [[Web]](https://ai.google.dev/gemini-api/docs/models)
        * **Por qué leerlo:** El documento técnico oficial de la arquitectura multimodal nativa y el razonamiento ("Deep Think") de Gemini 3.
    * **OpenAI (2025). "GPT-5 System Card".** [[PDF]](https://openai.com/index/gpt-5-system-card/)
        * **Por qué leerlo:** Detalla los riesgos de gobernanza en modelos omnicanal y la mitigación de audio/visión no deseada.
    * **Anthropic (2025). "Claude 3.5 Sonnet System Card".** [[PDF]](https://assets.anthropic.com/m/12f214efcc2f457a/original/Claude-Sonnet-4-5-System-Card.pdf)
        * **Por qué leerlo:** El estándar de la industria en "Seguridad Constitucional" y evaluación de riesgos catastróficos (CBRN).
    * **Meta (2025). "Llama 4 Model Card".** [[Web]](https://github.com/meta-llama/llama-models/blob/main/models/llama4/MODEL_CARD.md)
        * **Por qué leerlo:** La referencia obligatoria para el uso de modelos de frontera Open Source (Pesos Abiertos).
    * **Mistral AI (2025). "Mistral Large Model Card".** [[Web]](https://docs.mistral.ai/getting-started/models/)
        * **Por qué leerlo:** Ejemplo de eficiencia europea y modelos optimizados para razonamiento lógico y código.

* **Tendencia 2: IA en el Dispositivo (SLMs)**
    * **Microsoft (2025). "Phi-4 Technical Report".** [[PDF]](https://arxiv.org/abs/2412.08905)
        * **Por qué leerlo:** Define el estado del arte en **razonamiento complejo en modelos pequeños**. Demuestra cómo un modelo que cabe en un laptop puede superar a modelos 10 veces más grandes en matemáticas y lógica, validando la tesis de que "el tamaño no es inteligencia".
    * **Meta (2025). "Llama 3.2: Revolutionizing Edge AI".** [[Web]](https://ai.meta.com/blog/llama-3-2-connect-2024-vision-edge-mobile-devices/)
        * **Por qué leerlo:** El informe técnico de los modelos de **1B y 3B parámetros**. Es la referencia obligatoria para entender cómo desplegar agentes multimodales (texto e imagen) directamente en dispositivos móviles sin conexión a internet.
    * **Apple (2025). "OpenELM: An Efficient Language Model Family".** [[PDF]](https://arxiv.org/abs/2404.14619)
        * **Por qué leerlo:** Fundamental para el "Control". Apple publica no solo los pesos, sino el framework de entrenamiento completo, ofreciendo la máxima transparencia para entornos donde la **auditoría del código** es un requisito legal.

* **Tendencia 3: De Agentes-Herramienta a Agentes Autónomos**
    * **Cognition Labs (2025). "A Theory of Building Long-running Agents".** [[Web]](https://cognition.ai/blog/dont-build-multi-agents)
        * **Por qué leerlo:** Describe la arquitectura de ingeniería necesaria para evitar la fragilidad en agentes autónomos, proponiendo un enfoque de "agente único con contexto compartido" en lugar de sistemas multi-agente desconectados.
    * **Anthropic (Noviembre 2025). "Disrupting the first reported AI-orchestrated cyber espionage campaign".** [[Web]](https://www.anthropic.com/news/disrupting-AI-espionage)
        * **Por qué leerlo:** El reporte oficial de seguridad que detalla el incidente GTG-1002. Proporciona la evidencia empírica de cómo la "lealtad del agente" al prompt (jailbreak) superó a sus protocolos de seguridad.
    * **Riedl, M. O., & Desai, D. R. (Agosto 2025). "AI Agents and the Law". arXiv.** [[PDF]](https://arxiv.org/abs/2508.08544)
        * **Por qué leerlo:** Análisis crítico sobre la "Ley de Agencia" y los deberes fiduciarios, fundamental para entender la responsabilidad legal de los agentes autónomos.

* **Tendencia 4: La Web Agéntica (El Ecosistema)**
    * **Google (Noviembre 2025). "Google Antigravity: Platform for Autonomous Agents".** [[Web]](https://antigravity.google)
        * **Por qué leerlo:** El sitio de documentación oficial de la plataforma que habilita la orquestación global de agentes, definiendo los estándares de la "intranet de agentes".
    * **Anthropic (2025). "The Model Context Protocol (MCP)".** [[Web]](https://modelcontextprotocol.io)
        * **Por qué leerlo:** La especificación técnica del estándar abierto que permite a los agentes conectarse universalmente con sistemas de datos, la "tubería" esencial de la Web Agéntica.

* **Tendencia 5: IA Corpórea (Embodied AI)**
    * **LeCun, Y. (2022/2025). "A Path Towards Autonomous Machine Intelligence (AMI)".** [[PDF]](https://openreview.net/pdf?id=BZ5a1r-kVsf)
        * **Por qué leerlo:** Es el "Manifiesto Técnico" original de Yann LeCun. Define la arquitectura **JEPA** (Joint Embedding Predictive Architecture) y los "Modelos de Mundo", la base teórica de la startup AMI para crear IAs que entiendan la causa y efecto físico, no solo el lenguaje.
    * **Figure AI (2025). "Figure 03: Fleet Learning & Architecture".** [[Web]](https://www.figure.ai/news/introducing-figure-03)
        * **Por qué leerlo:** El reporte técnico del despliegue del robot Figure 03. Detalla cómo la **"tubería de datos de flota"** (Fleet Data Pipeline) permite que un robot aprenda una tarea (ej. manipular una pieza) y suba el conocimiento a la nube para que los otros 10.000 robots de la flota lo aprendan instantáneamente ("Aprendizaje de Flota").
    * **Boston Dynamics (2025). "The Electric Atlas: Reinforcement Learning for Dynamic Humanoids".** [[Web]](https://bostondynamics.com/blog/electric-new-era-for-atlas/)
        * **Por qué leerlo:** Detalla el cambio histórico de la robótica: el paso de la hidráulica (fuerza bruta) a la eléctrica controlada por **Aprendizaje por Refuerzo (RL)**. Explica cómo el modelo "aprende" a moverse y manipular objetos en lugar de ser programado paso a paso.

* **Tendencia 6: Más Allá del Transformer (Aprendizaje Continuo)**
    * **Dao, T., & Gu, A. (2025). "Transformers are SSMs: Generalized Models and Efficient Algorithms Through Structured State Space Duality (Mamba-2)".** [[PDF]](https://arxiv.org/abs/2405.21060)
        * **Por qué leerlo:** Es el paper de referencia para las arquitecturas **no-Transformers** (SSMs) que resuelven el **Costo Cuadrático** (Guía 03), permitiendo eficiencia a escala y costo lineal.
    * **Behrouz, A., et al. (2025). "Nested Learning: The Illusion of Deep Learning Architectures".** [[Web]](https://research.google/blog/introducing-nested-learning-a-new-ml-paradigm-for-continual-learning/)
        * **Por qué leerlo:** Aborda el segundo límite del Transformer (Guía 03): la **Amnesia Estática**. Introduce el paradigma del "Aprendizaje Anidado" y prototipos capaces de auto-modificación, clave para el "Vigilante Estratégico".
