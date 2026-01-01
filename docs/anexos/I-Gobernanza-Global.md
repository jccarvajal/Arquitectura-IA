# Anexo I: Mapeo de Gobernanza Global (ISO/IEC 42001 y NIST AI RMF)

### 1. Introducción: El Andamiaje de la Certificación

Este anexo actúa como el puente técnico entre la arquitectura de "Sistema 1 y Sistema 2" propuesta en esta obra y los marcos de gobernanza internacionalmente reconocidos. Para el Arquitecto de IA, estos estándares no son burocracia, sino el "manual de vuelo" necesario para operar sistemas complejos de forma segura, ética y auditable.

La implementación de las guías de este libro permite a las organizaciones alinearse con los dos pilares de la gobernanza global moderna:

* **ISO/IEC 42001:** El primer estándar internacional de sistemas de gestión de IA (AIMS).
* **NIST AI Risk Management Framework (RMF 1.0):** El marco de referencia global para la gestión de riesgos de IA.

---

### 2. Matriz de Correspondencia Operativa

Esta matriz detalla cómo los componentes cumplen con los requisitos operativos de cumplimiento global.

| Función NIST | Control ISO 42001 | Implementación en la Obra | Evidencia para Auditoría |
| :--- | :--- | :--- | :--- |
| **GOVERN** | Cláusula 5 y 6 | **Gobernanza de Ciclo de Vida:** Definición de roles, responsabilidades y política de "Delegar, No Abdicar". | Acta de Constitución del Comité de IA y Política Institucional. |
| **MAP** | Control A.5 (Impacto) | **Triage de Viabilidad:** Identificación de riesgos sistémicos, contextos de uso y stakeholders pre-diseño. | Informe de Evaluación de Impacto Algorítmico (DPIA). |
| **MEASURE** | Control A.10 (Monitoreo) | **Laboratorio de QA:** Uso de *Golden Sets* y métricas de la Tríada RAG (*Faithfulness, Relevance*). | Reporte de *Benchmark* del Golden Set y Rúbricas de Evaluación. |
| **MANAGE** | Control A.8 (Seguridad) | **Arquitectura LOSA y Línea Base de Control (20 Pilares):** Implementación de *Circuit Breakers*, filtros anti-inyección y capas de seguridad LOSA. | Logs de la Capa LOSA y Checklist de los 20 Pilares (Anexo D). |
| **MANAGE** | Control A.6 (Datos) | **Estrategia de Datos:** Protocolos de procedencia, minimización e integridad de la fuente para RAG. | Inventario de Datos y Hashing de Documentos RAG. |

---

### 3. Profundización en Marcos Internacionales

!!! tip "De la Teoría al Mapa de Riesgos"
Mientras que la ISO/IEC 42001 proporciona la **estructura de gestión** (el "qué"), el NIST RMF proporciona el **método de evaluación** (el "cómo"). El uso conjunto de ambos, operativizado mediante la **Línea Base de Control Industrial (20 Pilares)**, permite que su fábrica de IA sea auditable por terceros y resiliente ante regulaciones futuras como el EU AI Act.

#### 3.1. ISO/IEC 42001: El Sistema de Gestión de IA (AIMS)

1. **Cláusulas 4 y 6: Contexto de la Organización y Planificación (Evaluación de Impacto)**
    * **Requisito:** La norma exige entender el contexto, las partes interesadas y realizar un proceso formal para identificar riesgos y evaluar el impacto del sistema en individuos y la sociedad.
    * **Implementación:** Se cumple mediante el **Triage de Viabilidad** (Guía 01), que actúa como la primera puerta de control para identificar partes interesadas, requisitos legales y determinar si un caso de uso es técnicamente viable y éticamente aceptable antes de iniciar el diseño.
2. **Cláusula 8.1 y Control A.6: Control Operacional y Ciclo de Vida**
    * **Requisito:** ISO exige criterios claros y controles operativos para cada etapa del ciclo de vida de la IA, incluyendo el diseño y desarrollo.
    * **Implementación:** La metodología de **Industrialización** (Guía 11) cumple con esto al transformar el prototipo en un activo bajo control de cambios, utilizando **Prompt-as-Code** para asegurar la trazabilidad y la inmutabilidad de la lógica de negocio.
3. **Controles A.4 y A.7: Gestión de Recursos y Datos**
    * **Requisito:** La norma pone especial énfasis en la documentación de recursos, la procedencia (*provenance*) y la calidad de los datos utilizados.
    * **Implementación:** La **Estrategia de Datos** (Guía 04) y el uso de **RAG** (Generación Aumentada por Recuperación) permiten cumplir con estos requisitos al proporcionar un rastro auditable de las fuentes de información utilizadas por el agente para generar sus respuestas.
4. **Control A.8.2: Seguridad de Aplicaciones y Mitigación de Riesgos**
    * **Requisito:** La norma exige controles para prevenir la manipulación indebida y asegurar la integridad de los sistemas de IA.
    * **Implementación:** Se cumple mediante la **Arquitectura LOSA** (Guía 09), que actúa como el control de seguridad perimetral para mitigar ataques de **Inyección de Prompts (LLM01)** y **Divulgación de Información Sensible (LLM02)**.
5. **Control A.8.4: Resiliencia Operativa y Continuidad**
    * **Requisito:** Asegurar que el sistema sea estable ante fallos de infraestructura o cambios críticos de proveedores.
    * **Implementación:** Se operativiza a través del **Octágono de Control** (Guía 11), específicamente mediante los puntos de **Inmutabilidad y Reversibilidad** (versionado de prompts) y la **Soberanía y Gestión de Terceros** para evitar el *vendor lock-in*.
6. **Control A.9.3: Vigilancia Humana y Objetivos de Uso Responsable**
    * **Requisito:** La organización debe identificar objetivos para guiar el uso responsable y demostrar que mantiene el control efectivo sobre el sistema.
    * **Implementación:** El **Axioma de la Responsabilidad Indelegable** (Guía 09) y la implementación de mecanismos de **Anulación Humana** (*Override*) garantizan que el Sistema 2 humano siempre sea el garante legal de las acciones del Sistema 1 algorítmico.
7. **Control A.10.2: Registro y Análisis de Incidentes**
    * **Requisito:** Mantener registros auditables para entender fallos, alucinaciones o comportamientos anómalos.
    * **Implementación:** Se garantiza mediante la **Observabilidad Cognitiva** (Guía 11), que registra no solo el resultado final, sino la **Cadena de Pensamiento (CoT)** del agente, proporcionando la "evidencia forense" necesaria para auditorías tras un incidente.

#### 3.2. NIST AI RMF: El Ciclo de Confianza y Fiabilidad

El marco del **NIST (AI Risk Management Framework 1.0)** se centra en cultivar una **IA Digna de Confianza** (*Trustworthy AI*) a lo largo de todo el ciclo de vida. Para el NIST, la confianza no es un sentimiento, sino una propiedad técnica que se mide a través de siete características clave que nuestra arquitectura garantiza:

1. **Válida y Fiable (Valid & Reliable):** 
    Se asegura mediante el rigor del **Laboratorio de QA**, el monitoreo de la deriva cognitiva (**Drift**) y el uso del **Golden Set**. Este control verifica que el sistema responda con precisión estadística y consistencia semántica antes y durante la producción, mitigando la **Falta de Fiabilidad**.
2. **Segura (Safe):** 
    Implementada a través de la **Capa LOSA** y los filtros de sanitización anti-inyección. Asegura que el sistema no opere fuera de sus límites de seguridad ni responda a entradas maliciosas que puedan comprometer la integridad operativa.
3. **Resiliente (Secure & Resilient):** 
    Garantizada por el **Interruptor Financiero (Hard Cap)** y los **Circuit Breakers** definidos en la Guía 11. Previene el colapso operativo ante errores lógicos, ataques de **Consumo Ilimitado (LLM10)** o fallos críticos de infraestructura.
4. **Transparente y con Rendición de Cuentas (Accountable & Transparent):** 
    Se basa en el **Axioma de la Responsabilidad Indelegable** de la Guía 09. Mitiga la **Abdicación del Juicio** al asegurar que el humano (Sistema 2) sea siempre el garante legal y ético de cada decisión automatizada.
5. **Explicable e Interpretable (Explainable & Interpretable):** 
    El monitoreo de la **Salud Cognitiva** y de la **Cadena de Pensamiento (CoT)** combate la **Opacidad** sistémica. Permite auditar el razonamiento interno y garantiza la trazabilidad de los pasos intermedios de los agentes ante auditorías.
6. **Privacidad Mejorada (Privacy-enhanced):** 
    El uso de **Ingeniería Soberana** y técnicas de **Minimización de Contexto** protege la información sensible. Asegura que el procesamiento de datos se mantenga bajo control institucional y dentro de su jurisdicción legal.
7. **Justa y con Sesgos Gestionados (Fair with Harmful Bias Managed):** 
    Se mide mediante métricas de **Relevancia y Fidelidad** en el laboratorio de QA. Detecta desviaciones semánticas o sesgos sistémicos que puedan perjudicar la integridad o equidad de las respuestas generadas

---

### 4. Guía de Auditoría para el Arquitecto (Artifacts)

Al enfrentar un proceso de auditoría o debida diligencia (*Due Diligence*), el Arquitecto debe presentar las siguientes evidencias (Artifacts) derivadas de este marco de trabajo:

* **System Cards (Fichas Técnicas):** 
    Evidencia documental de la selección del modelo y evaluación de capacidades bajo el Triage de la Guía 01.
* **Repositorio Git de Prompts:** 
    Evidencia de **Inmutabilidad y Reversibilidad**, demostrando qué instrucción exacta estaba activa en cada transacción para auditoría forense.
* **Rúbricas de Evaluación Semántica:** 
    Evidencia de los criterios objetivos usados por el **Juez LLM** para validar la calidad y seguridad de las respuestas.
* **Registros de Simetría de Acción:** 
    Logs que demuestran la capacidad efectiva de control humano, como la activación de **Circuit Breakers** o el uso del **"Retraso de Pánico"**.

!!! success "Hacia un Estándar de Confianza"
    Alinear tu fábrica de IA con la ISO 42001 y el NIST RMF no es un acto burocrático; es la garantía de que tu arquitectura es **robusta, ética y comercialmente viable** ante los reguladores y clientes globales más exigentes.
