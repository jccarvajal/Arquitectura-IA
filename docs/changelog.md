# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Arquitectura de Inteligencia Artificial: Guías para Decidir, Diseñar y Gobernar"**.

---

# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Arquitectura de Inteligencia Artificial: Guías para Decidir, Diseñar y Gobernar"**.

---

# Versión 1.5 (Diciembre 2025)

**Motivo:** Cierre del ciclo operativo y consolidación de la biblioteca de herramientas. Esta versión finaliza la redacción de los anexos técnicos de soberanía y automatización, y reestructura la fase de cumplimiento para que actúe como un "Sello de Certificación" final. Uso de IA (LLM's) como auditor técnico preventivo externo.

### 🏗️ Reestructuración de la Biblioteca (Orden de Auditoría)
* **Desplazamiento Estructural:** Los antiguos Anexos E (ISO/NIST) y F (EU AI Act) se han movido a las posiciones **I** y **J** respectivamente.
* **Propósito:** Asegurar que los marcos regulatorios y estándares globales cierren el libro como la validación final (certificación) de todo el diseño previo.

### 📝 Redacción y Finalización de Anexos Técnicos
* **Anexo E (Soberanía del Criterio):** Restauración de la **Rúbrica de Madurez (RMJP)** con sus 4 dimensiones (Detección, Sistema 2, Soberanía y Manejo de Crisis) e introducción de la métrica **TDE (Tasa de Desafío Efectivo)**.
* **Anexo F (Vulnerabilidades Lógicas):** Desarrollo de protocolos de defensa contra la erosión del razonamiento crítico y sesgos cognitivos en la interacción con modelos.
* **Anexo G (Orquestación y Actuadores):** Definición de la matriz de decisión para la ejecución de acciones entre **SaaS** (Velocidad), **RPA** (Sistemas Legacy) e **Ingeniería Soberana** (Control/Privacidad).
* **Anexo H (Seguridad Operativa - LOSA):** Implementación técnica de la **Capa LOSA** como una **"Aduana Cognitiva"**, alineada con **OWASP LLM 2025** y el principio de *Zero Trust*.

### 🤖 Metodología de Revisión y Sparring
* **Auditoría Externa con IA:** Uso de **ChatGPT** como sparring técnico y revisor de arquitectura para desafiar la coherencia lógica de los contenidos.
* **Red Teaming de Contenidos:** Uso de modelos de lenguaje para verificar la alineación entre los *Blueprints* del Anexo C y las nuevas capacidades de automatización descritas en el Anexo G.

---

# Versión 1.4 (Diciembre 2025)

**Motivo:** Endurecimiento industrial del marco GRC. Esta versión transforma la arquitectura de "teóricamente correcta" a "financiera y operacionalmente viable", aplicando parches críticos de seguridad, rentabilidad y cultura. Se reestructura la jerarquía de contenidos separando las Herramientas (Anexos) de las Referencias Teóricas.

### 🛡️ Seguridad y Gobernanza
* **Guía 02 (Prompts):** Se redefinió el prompt como instrumento de *Alineación Probabilística*, eliminando la falacia de seguridad dura.
* **Guía 04 (Datos):** Nuevo protocolo de **"Esterilización de Documentos"** para mitigar ataques de *Inyección Indirecta* en RAG.
* **Guía 05 (Agentes):** Implementación del **"Principio de Simetría de Acción"**. Obligatoriedad de funciones de reversión (*Undo*) y *Kill-Switch* para herramientas de escritura.
* **Anexo C (Blueprints):** Alerta crítica sobre gestión de credenciales y prohibición de *hardcoded secrets*.

### 💰 Finanzas y Estrategia
* **Guía 13 (Estrategia):** **"Regla de Autofinanciamiento"**. La innovación (Transformación) solo puede financiarse con los ahorros de la eficiencia (Soporte).
* **Guía 11 (Industrialización):** **"Política de Purga de Logs"**. Retención máxima de 30 días para trazas de razonamiento (CoT) para control de costos.
* **Anexo A (Viabilidad):** **"Veto Automático del 50%"**. Rechazo inmediato de proyectos cuyo costo unitario IA supere la mitad del costo humano.
* **Glosario:** Redefinición financiera de **"Aumento"** (más output, mismo headcount) vs. **"Abdicación"**.

### 🏗️ Ingeniería y Operaciones
* **Guía 06 (Sistemas Cognitivos):** Restricción de latencia para *Tree of Thoughts* (ToT). Prohibido en tiempo real; exclusivo para procesos *Batch*.
* **Guía 14 (Modelos):** Optimización del **Agente Enrutador** mediante modelos ligeros (Flash/Haiku) para reducir latencia inicial.
* **Guía 10 (Calidad):** Estrategia de **"Cosecha Automática"** (Harvesting). El Golden Set se actualiza capturando *Edge Cases*, feedback negativo y baja confianza.

### 🧠 Cultura y Talento
* **Guía 15 (Ética):** Protocolos de **"Simulacro de Desconexión"** para combatir la atrofia cognitiva.
* **Guía 16 (Operación):** **"Teoría del Seguro"**. Redefinición del salario humano como una *Prima de Riesgo* por la responsabilidad legal, no por la producción.
* **Carrera Técnica:** Definición de roles de transición (Validador -> Entrenador -> Diseñador de Flujos).

### 🏗️ Refinamiento de Marco de Trabajo (GRC)
* **Guía 01 (Anatomía):** Inclusión del concepto de **"Soberanía de Pesos"** frente a modelos propietarios.
* **Guía 10 (Evaluación):** Formalización de la **Tríada RAG** (Faithfulness, Relevance) y la técnica del **Juez LLM** para evaluaciones semánticas no literales.
* **Guía 11 (Industrialización):** Introducción del **"Octágono de Control Industrial"** como checklist final para el paso a producción.

### 🌐 Cumplimiento y Estándares Globales (Anexos)
* **Anexo E (ISO/NIST):** Expansión total del mapeo operativo para **ISO/IEC 42001:2023** (cláusulas 4, 6, 8 y 9) y alineación con las **7 características de confianza** del **NIST AI RMF 1.0**.
* **Anexo F (EU AI Act):** Detalle de la clasificación de riesgos (Inaceptable, Alto, Limitado, Mínimo) y requisitos para la obtención del **Marcado CE** en sistemas de IA de alto riesgo.

### 📚 Cambios Estructurales
* **Jerarquía de Referencias:** El Glosario y la Bibliografía pierden la etiqueta de "Anexo" y se mueven a su propia categoría (`/referencias`) para distinguirlos de las herramientas operativas.

---

## Versión 1.3 (Diciembre 2025)

**Motivo:** Consolidación de la tesis de gobernanza como **"Ingeniería de Control"**. Esta versión integra la estrategia de **Soberanía y Geopolítica**, la visión de **Agencia Humana** (Innerarity) y profundiza en los riesgos de politización técnica.

### Actualizaciones Estratégicas y Filosóficas
* **Tesis Central (Guía 15 y Conclusión):** Se estableció el axioma de la "Agencia Humana" integrando la **"Advertencia de los Fundadores"** (Wiener/Lanier).
* **Prólogo:** Nueva estructura basada en las cuatro metáforas de futuros (Utopía, Distopía, Caos, Estructura).
* **Geopolítica:** Inclusión de la **Matriz de Decisión** (SaaS vs. Open Weights).

### Mejoras Técnicas
* **Infraestructura:** Migración completa a **MkDocs** e implementación de diagramas **Mermaid.js**.
* **Anexo A:** Adición del bloque de **Dictamen Final (Triage)**.
* **Anexo D:** Migración de prompts a bloques de código copiables.

---

## Versión 1.2 (Noviembre 2025)

**Motivo:** Estandarización de conceptos de "Agencia" y refinamiento de la "Ingeniería de Agentes".

### Cambios Técnicos
* **Guía 05 (Agentes):** Formalización del ciclo **ReAct** (Razonar + Actuar).
* **Guía 14 (Modelos):** Introducción de la **Estrategia de Portafolio** y métricas de *Token-Economics*.

---

## Versión 1.1 (Noviembre 2025)

**Motivo:** Transición a un marco de pensamiento estratégico completo (GRC).

### Cambios Estratégicos
* **Tesis Central:** Enfoque explícito en **GRC (Gobernanza, Riesgo y Cumplimiento)**.
* **Ingeniería de Contexto:** Elevación del Prompting a gestión de memoria.
* **Límites:** Definición del **Costo Cuadrático** y la **Amnesia Estática**.

---

## Versión 1.0 (Base Inicial)

**Motivo:** Publicación inicial del borrador de contenidos.

* **Lanzamiento:** Publicación del libro con la estructura base de 17 guías y 6 anexos.