### Guia 14: Modelos y Mercado LLM

Subtítulo: Del "Jefe de Adquisiciones" al "Arquitecto de Portafolio"

#### Introducción: Del Gobierno al Portafolio

En guías anteriores aprendimos a diseñar y **gobernar**, es decir, controlar de forma segura los sistemas de IA. Este anexo es el manual de adquisiciones. Su objetivo no es señalar al "mejor" modelo, sino entregar una metodología para construir un ecosistema de portafolio. El rol estratégico no es elegir un solo motor, sino diseñar un portafolio flexible que combine modelos de manera inteligente.

---

#### Parte 1: El Pilar Técnico: La Arquitectura Transformer

Antes de analizar el mercado de "motores" (modelos), es crucial entender la arquitectura técnica que define a la generación actual de IA: el **Transformer**.

Presentada en 2017 por Google, esta arquitectura es el motor detrás de casi todos los modelos que dominan el panorama 2025-2026, incluyendo las familias GPT (OpenAI), Gemini (Google), Claude (Anthropic) y los principales modelos open-source como Llama (Meta) y Mistral.

**¿Qué es y por qué domina?**

El Transformer resolvió el problema de cómo "entender" secuencias de texto a gran escala. Su innovación clave es el mecanismo de **"auto-atención" (self-attention)**, que permite al modelo sopesar la importancia de diferentes palabras en una oración, sin importar qué tan lejos estén unas de otras.

Es esta capacidad de "ver" y "conectar" el contexto completo de un texto lo que les da su poder para razonar, traducir y generar lenguaje con coherencia.

**La Limitación Estratégica**

Sin embargo, esta arquitectura tiene dos implicaciones estratégicas que impactan directamente en el "Triángulo de Adquisición" (Rendimiento, Control, Costo):
1. **Costo de Escalado (Costo):** El mecanismo de auto-atención es computacionalmente intensivo. Su costo y uso de memoria crecen cuadráticamente con la longitud del contexto. Duplicar la longitud de un documento no duplica el costo, sino que lo cuadruplica (o más), lo que encarece la operación a gran escala.
2. **Naturaleza Estática (Control):** Los Transformers se entrenan en una "foto" masiva del conocimiento (un corpus de datos) y luego se "congelan". No están diseñados para aprender de forma continua o para integrar nueva información después de su entrenamiento, un desafío que exploramos en la Guía 17: Perspectivas.

> **Nota del Arquitecto (Actualización de Industria 2025):**
> La industria ha validado oficialmente el cambio de paradigma de "Chatbots" a "Agentes". El reporte *101 Real-World Gen AI Use Cases* (Google Cloud, Oct 2025) clasifica el mercado ya no por modelos, sino por **6 Tipos de Agentes**:
> 1.  **Customer Agents:** (Nuestro Blueprint 1).
> 2.  **Employee Agents:** (Nuestros Agentes PM de productividad).
> 3.  **Creative Agents:** (Nuestros Co-Pilotos de Marketing).
> 4.  **Data Agents:** (Nuestros Agentes de Gobernanza y RAG).
> 5.  **Code Agents:** (Nuestros Co-Pilotos de Desarrollo).
> 6.  **Security Agents:** (Nuestros componentes de arquitectura LOSA).
>
> *Implicancia:* La estrategia de "Agente Enrutador" propuesta en esta guía es la única capaz de orquestar estos 6 tipos de especialistas en un solo portafolio coherente.

---

#### Parte 2: El Panorama 2025-2026: Los Tres Ecosistemas

Como “Jefes de Adquisiciones” de nuestra fábrica de IA, el mercado de “motores” (LLMs) se ha consolidado en tres ecosistemas claros. Como establecimos en la **Guía 03**, la arquitectura **Transformer** es el motor técnico fundamental que impulsa a la gran mayoría de los modelos en estos ecosistemas (GPT, Llama, Claude, etc.).

Este anexo se enfoca en cómo los proveedores "empaquetan" esa arquitectura, con sus límites de costo cuadrático y memoria estática, en distintas estrategias de suministro:

**A. Modelos Propietarios (APIs) \- "Arrendar el Cerebro"**

* **Qué es:** Arriendas el poder de cómputo y el modelo a un proveedor.  
* **Proveedores:** Google (Gemini), OpenAI (GPT), Anthropic (Claude).  
* **Fortaleza:** Acceso inmediato a la máxima potencia y a ventanas de contexto gigantescas (1M+ tokens). Ideal para tareas cognitivas complejas.  
* **Riesgo:** Dependencia tecnológica y exposición de datos al proveedor (los datos viajan a su nube). El costo operacional es alto por token.

**B. Modelos Open-Source / Open-Weigh (Ejecución Local) \- "Comprar la Máquina"**

* **Qué es:** Descargas los "pesos" del modelo y lo ejecutas en tu propia infraestructura (on-premise o nube privada). Tienes la máquina, no solo una conexión a ella.
* **Proyectos:** Llama (Meta), Mistral/Mixtral, Qwen.  
* **Fortaleza:** *Soberanía y transparencia* de los datos ya que nunca salen de tu control (ideal para entornos regulados). Ofrece máximo control para personalización profunda, incluyendo el *Ajuste Fino* para especializar el "cerebro" sin restricciones externas.
* **Riesgo:**
    1. **Costo de Infraestructura:** Requiere hardware GPU dedicado y un equipo de ingeniería capaz de gestionar la *Industrialización* (el proceso de escalar prototipos a producción).
    2. **Responsabilidad de Seguridad Total:** A diferencia de las APIs, donde el proveedor gestiona la seguridad, aquí el modelo es vulnerable. Las técnicas de seguridad nativas (como el "desaprendizaje" de conceptos dañinos) son inmaduras y pueden revertirse fácilmente con un ajuste fino mínimo. Si no construyes tu propia capa de seguridad (LOSA), el modelo está desprotegido.

> **Actualización de Mercado (Nov 2025):** La brecha de capacidad se ha cerrado. Actualmente, los modelos abiertos de vanguardia tienen un retraso de **menos de un año** respecto a los modelos de frontera cerrados.
> *Implicancia:* La decisión de usar Open-Source ya no implica sacrificar inteligencia. El *trade-off* ha cambiado: ganas potencia y soberanía, pero asumes el 100% de la carga de la ciberseguridad, ya que las salvaguardas del proveedor se pueden desactivar.

**C. Agentes-como-Servicio (AaaS) \- "Contratar al Especialista"**

* **Qué es:** Consumes un producto terminado que encapsula el modelo y la arquitectura (como la **Generación Aumentada por Recuperación (RAG)**, el sistema de recuperación de conocimiento).  
* **Ejemplos:** Perplexity, Microsoft Copilot, ChatGPT Enterprise.  
* **Fortaleza:** Implementación en tiempo récord y soluciones enfocadas (ej. ofimática, investigación). Costo inicial bajo (suscripción).  
* **Riesgo:** Flexibilidad técnica baja ("caja negra"). La **Gobernanza** (el control de seguridad y datos) depende 100% del contrato con el proveedor.

---

#### Parte 3: El "Triángulo de Adquisición"

Como "Jefe de Adquisiciones", no puedes tenerlo todo. Cada decisión equilibra tres fuerzas. Hemos reemplazado "Capacidad" por "Control", un término más robusto y estratégico.

1. **Rendimiento (Potencia):** La inteligencia "cruda". Su capacidad para razonar (usando un ciclo de **ReAct** o Razonar-Actuar), escribir código complejo y pasar benchmarks (pruebas de **Evaluación** de calidad).  
2. **Control (Soberanía):** ¿Qué tanto gobierno tienes sobre el proceso? Esto incluye:  
   * **Soberanía de Datos:** ¿Dónde residen los datos? ¿Salen de tu nube?  
   * **Auditoría:** ¿Puedes trazar las decisiones y los logs?  
   * **Personalización:** ¿Puedes hacer Ajuste Fino al modelo?  
   * **Seguridad:** ¿Cómo se manejan los riesgos de Gobernanza?  
3. **Costo (Economía):** El costo total, no solo el precio por token. Incluye el costo de infraestructura (GPUs), licencias y el costo de personal (Industrialización).

---

#### Parte 4: La Solución Estratégica: El "Agente Enrutador"

El panorama 2025-2026 demuestra que la estrategia ganadora no es elegir un motor, sino construir un portafolio y usar el motor adecuado para cada tarea.

¿Cómo se implementa esto? Con la arquitectura de **Diseño Cognitivo** más avanzada: el **Agente Enrutador**.

El "Agente Enrutador" (que puede ser un "Agente Director") es un "cerebro" metacognitivo que gestiona el portafolio.

1. **Llega una Tarea:** "Resume este email de 2 líneas."  
2. **Agente Enrutador (Razona):** "Esto es una tarea 'simple' y 'corta'. No necesito al caro GPT-4o. Usaré un modelo del Ecosistema B (Open-Source) o una API barata (Haiku)."  
3. **Agente Enrutador (Actúa):** Llama al motor más eficiente y económico.  
4. **Llega otra Tarea:** "Analiza las implicaciones de este contrato sensible de 500 páginas."  
5. **Agente Enrutador (Razona):** "Esto es 'complejo' y de 'contexto largo'. Además, los datos son 'sensibles'. Necesito 'Control' total."  
6. **Agente Enrutador (Actúa):** Llama al modelo Open-Source (Ecosistema B) hosteado localmente para garantizar la soberanía de los datos.  
* **Beneficio:** Obtienes el máximo Rendimiento cuando lo necesitas y el máximo Control y Costo-eficiencia cuando no. Has optimizado el "Triángulo de Adquisición".  
* **Validación de Mercado (2025):** Esta estrategia de portafolio ("Comprar" o "Arrendar" en lugar de "Construir" todo desde cero) no es solo teórica. Informes de la industria de 2025 (como el "State of AI in Business" del MIT) revelan que las iniciativas de "Comprar" (asociaciones estratégicas) tienen el **doble de tasa de éxito** (aprox. 66%) que las de "Construir" (desarrollo interno) (aprox. 33%).

---

#### Parte 5: Metodología Práctica de Selección (Checklist)

Para diseñar tu portafolio, usa este proceso:

1. **Definir el Caso de Uso:** ¿Qué problema resuelve? (Precisión, latencia).  
2. **Clasificar por Riesgo/Sensibilidad:** ¿Los datos son públicos, internos o confidenciales (salud, jurídicos, seguridad)?  
3. **Asignar el Tipo de Modelo:** Usa la matriz de decisión y el checklist de abajo.  
4. **Pilotar con Métricas:** Implementa un **prototipo** (la versión v1 de prueba) y mide con la guía de **Evaluación** (QA).  
5. **Monitorear y Revisar:** Implementa logs (parte de la **Industrialización**) y revisa el portafolio cada 3-6 meses.

**Matriz de Decisión Estratégica**

| Dimensión | Propietario (API) | Open-Source (Local) | AaaS (Producto) |
| :---- | :---- | :---- | :---- |
| **Gobernanza de Datos** | Limitada: los datos viajan a la nube del proveedor. | Total: Control local. Ideal para regulación. | Depende del proveedor y del contrato. |
| **Costo Inicial** | Bajo. | Alto (Hardware GPU, equipo). | Bajo (Suscripción). |
| **Costo Operacional** | Alto (Pago por token a escala). | Medio (Infraestructura, soporte). | Fijo/Variable (Licencia). |
| **Flexibilidad Técnica** | Media (Prompting, RAG). | Alta (Ajuste Fino, RAG, modificación). | Baja ("Caja negra"). |

**Checklist Rápido de Decisión**

| Pregunta Clave | Acción Requerida (Ejemplos) |
| :--- | :--- |
| ¿Los datos son sensibles (salud, seguridad, jurídico)? | (Si es SÍ: Priorizar Open-Source Local) |
| ¿Requiere auditoría y trazabilidad completa? | (Si es SÍ: Priorizar Open-Source o API con cláusulas de logs) |
| ¿Necesitamos customización profunda (Ajuste Fino)? | (Si es SÍ: Requerir Open-Source) |
| ¿Tenemos capacidad de Industrialización interna? | (Si es NO: Priorizar API o AaaS, o planificar contratación) |

##### Referencia de Adquisición Pública: El Modelo de la Directiva N°44

Para los "Arquitectos de Portafolio", es valioso analizar cómo los estados avanzados se protegen contractualmente. La **Directiva de Compra N°44 (Chile, 2023)** sobre proyectos de Ciencia de Datos e IA ofrece un catálogo de cláusulas de seguridad que cualquier empresa debería copiar en sus contratos:

* **Cláusula de "Caja Negra" (Explicabilidad):** Exigir al proveedor mecanismos que permitan comprender *por qué* el modelo llegó a una decisión. No aceptar modelos opacos en decisiones críticas.
* **Propiedad Intelectual:** Definir explícitamente si se adquiere el código fuente ("work for hire") o solo una licencia de uso.
* **Evaluación de Impacto:** Exigir una "Evaluación de Impacto en Protección de Datos" (DPIA) antes de la adjudicación.

**Herramienta:** Puede consultar las **Bases Tipo de Ciencia de Datos e IA** (disponibles como referencia pública en ChileCompra) para extraer estándares técnicos de SLA, perfiles de equipo e hitos de pago aplicables a cualquier industria.

---

#### Parte 6: Enfoque Especial: Sector Público y Entornos Regulados

Para instituciones públicas o reguladas (finanzas, salud), el factor **Control** (Soberanía de Datos, Auditoría) debe superar casi siempre al Rendimiento.

1. **Priorizar Soberanía de Datos:** Favorecer soluciones locales (Open-Source) para cualquier información crítica o sensible.  
2. **Exigir Transparencia y Auditoría:** Exigir documentación técnica clara y la capacidad de auditar los procesos y los logs.  
3. **Contratar con Cláusulas de Gobernanza:** Al usar APIs (Ecosistema A) o AaaS (Ecosistema C), incluir cláusulas contractuales específicas sobre residencia de datos, trazabilidad y retención de logs.

---

#### Conclusión: De Gobernador a Arquitecto de Portafolio

La maestría no reside en saber qué LLM es "mejor", sino en tener el juicio de ingeniería para diseñar un ecosistema flexible: rendimiento donde importa, Control donde hay riesgo, y Costo donde la escala lo exige. El rol final no es solo gobernar una fábrica; es ser el "Arquitecto del Portafolio de IA".

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="./13-Estrategia-Valor.html">« Guía 13</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
  <div>
    <a href="./15-Etica-Confianza.html">Guía 15 »</a>
  </div>
</div>