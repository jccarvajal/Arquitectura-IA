# Anexo J: Clasificación de Riesgos según el EU AI Act

### 1. Introducción: El Enfoque basado en Riesgos

El **EU AI Act** (Reglamento de Inteligencia Artificial de la Unión Europea) representa el primer marco jurídico integral en el mundo. Su arquitectura no regula la tecnología de forma genérica, sino los **casos de uso**, clasificándolos en función del riesgo que suponen para los derechos fundamentales, la seguridad y la salud. 

Para el Arquitecto de IA, esta clasificación determina la viabilidad legal del proyecto y el nivel de rigor técnico exigido en la fase de industrialización.

!!! warning "Nota de Estrategia Global: El 'Efecto Bruselas' y el Horizonte 2026"
    Aunque este anexo toma como referencia la taxonomía de riesgo del *EU AI Act*, su utilidad no se limita a la jurisdicción europea. Para organizaciones en Latinoamérica y el resto del mundo, el **Q1 de 2026** marca un punto de inflexión estratégico por tres razones de mercado, más allá de la obligación legal directa:

    1. **El Estándar de la Cadena de Suministro:** Las corporaciones globales exigirán a sus proveedores (incluso locales) un cumplimiento homologable a la normativa europea para mitigar sus propios riesgos de terceros. No cumplir es quedar fuera del mercado *Enterprise*.
    2. **Efecto Espejo Legislativo:** Las regulaciones emergentes en la región (como las discusiones legislativas en Chile, Brasil o Colombia) tienden a armonizarse con el modelo europeo. Adoptar esta clasificación hoy es prepararse para la ley local de mañana.
    3. **Diferenciación Competitiva:** En un mercado saturado de IA experimental, la **gobernanza demostrable** se convierte en el principal activo de confianza. Llegar al 2026 con una arquitectura auditable es una ventaja comercial defensiva.

    **El mensaje es claro:** No espere a que la ley local se publique. Si su arquitectura es robusta bajo el estándar más alto (EU/ISO), será resiliente en cualquier jurisdicción.

---

### 2. Niveles de Riesgo y Obligaciones

#### 2.1. Riesgo Inaceptable (Prácticas Prohibidas)
Sistemas que suponen una amenaza clara y, por tanto, están estrictamente prohibidos en la Unión Europea.

* **Puntuación Social (Social Scoring):** Clasificación de personas basada en su comportamiento social o características personales.
* **Manipulación Subliminal:** Técnicas que eluden la conciencia para alterar el comportamiento de forma que cause daño.
* **Explotación de Vulnerabilidades:** Sistemas que se aprovechan de debilidades por edad, discapacidad o situación socioeconómica.
* **Identificación Biométrica Remota:** Uso en tiempo real en espacios públicos (salvo excepciones críticas de seguridad nacional).

#### 2.2. Alto Riesgo (Sistemas Regulados)
Esta es la categoría donde operan la mayoría de los sistemas empresariales complejos y la que requiere la implementación de las guías de esta obra.

* **Áreas Críticas:**
    * **Empleo y RRHH:** Sistemas de contratación, promoción o evaluación de trabajadores.
    * **Educación:** Evaluación de exámenes o admisión en instituciones educativas.
    * **Servicios Esenciales:** Evaluación de solvencia (Credit Scoring) y triaje en servicios de salud.
    * **Infraestructuras Críticas:** Gestión de tráfico, agua, gas o electricidad.
    * **Migración y Justicia:** Verificación de autenticidad de documentos de viaje o asistencia en la toma de decisiones judiciales.

#### 2.3. Riesgo Limitado (Obligaciones de Transparencia)
Sistemas con un riesgo menor pero que exigen informar claramente al usuario final.

* **Chatbots y Agentes:** El usuario debe saber que interactúa con una IA.
* **Deepfakes:** El contenido generado o manipulado debe estar etiquetado como artificial.

#### 2.4. Riesgo Mínimo o Nulo
La mayoría de las aplicaciones actuales (filtros de spam, recomendaciones de inventario, videojuegos) no tienen obligaciones legales específicas bajo el reglamento.

---

### 3. IA de Propósito General (GPAI) y Riesgo Sistémico

El reglamento introduce reglas específicas para modelos potentes (como GPT-4, Gemini o Claude) que sirven de base para múltiples aplicaciones:

* **Modelos con Riesgo Sistémico:** Modelos entrenados con una capacidad de cómputo superior a 10^25 FLOPS.
* **Obligaciones:** Evaluación de riesgos masiva, pruebas adversas (Red Teaming), informes de incidentes graves y cumplimiento de normas de eficiencia energética.

---

### 4. Correspondencia de Controles para Sistemas de "Alto Riesgo"

Para que un sistema de Alto Riesgo sea legalmente comercializable, el Arquitecto debe garantizar los siguientes controles técnicos mapeados en este libro:

| Requisito EU AI Act | Control Operativo en esta Obra |
| :--- | :--- |
| **Sistema de Gestión de Riesgos** | Implementación del Octágono de Control (Guía 11). |
| **Gobernanza de Datos** | Estrategia de Datos y protocolos RAG (Guía 04). |
| **Documentación Técnica** | Fichas de Proyecto y Prompt-as-Code (Guía 01 y 11). |
| **Registro de Eventos (Logging)** | Observabilidad Cognitiva y Trazabilidad de Pensamiento. |
| **Vigilancia Humana** | Aplicación del Axioma de Responsabilidad Indelegable. |
| **Precisión y Robustez** | Laboratorio de QA y Arquitectura LOSA (Guía 09 y 10). |

---

### 5. El Marcado CE de Inteligencia Artificial

Al igual que otros productos industriales, los sistemas de IA de Alto Riesgo deben obtener el **Marcado CE**. Este sello certifica que:

1. El sistema ha pasado por una evaluación de conformidad.
2. Existe un sistema de gestión de calidad documentado.
3. Se ha implementado un monitoreo post-comercialización continuo para detectar fallos o alucinaciones en tiempo real.

!!! danger "Advertencia sobre el Incumplimiento"
    Las sanciones por incumplimiento de las prácticas prohibidas pueden alcanzar los **35 millones de euros o el 7% de la facturación global anual**, lo que convierte a la gobernanza en un componente crítico de la viabilidad financiera.
