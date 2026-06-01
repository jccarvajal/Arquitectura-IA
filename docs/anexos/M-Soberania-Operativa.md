# Anexo M: IA Local y Soberanía Operativa

**Modelos Locales, Entornos Privados, Wrappers CLI y Control del Dato**

### 1. El Problema que Este Anexo Resuelve

La adopción organizacional de IA ha creado una tensión estructural entre dos objetivos legítimos: maximizar la capacidad de razonamiento disponible para los usuarios y mantener el control sobre los datos, procesos y secretos institucionales.

La respuesta habitual ha oscilado entre dos extremos deficientes. El primero consiste en permitir el uso irrestricto de herramientas externas, trasladando datos institucionales a proveedores sin una evaluación formal del riesgo; esto sacrifica la gobernanza. El segundo consiste en prohibir el uso de IA, bajo el supuesto de que la restricción elimina el riesgo; esto fracasa porque no modifica el incentivo y genera **Shadow AI** (uso informal de herramientas no autorizadas fuera de los mecanismos de supervisión).

Este anexo describe la arquitectura que elimina el dilema de origen: operar con capacidad de razonamiento avanzada sin perder soberanía sobre el dato.

---

### 2. Qué Entendemos por Soberanía Operativa

La soberanía operativa es la capacidad de una organización para decidir de forma verificable:

* Dónde se procesa un dato.
* Quién puede acceder a él.
* Qué modelo puede utilizarlo.
* Bajo qué condiciones puede ser transferido.
* Cómo se audita el proceso.

La soberanía no implica aislamiento absoluto; implica control verificable. La ubicación física del procesamiento no es el criterio principal; el criterio estructural es la capacidad de gobernanza. 

La soberanía operativa constituye la extensión práctica de la Soberanía del Criterio descrita en el Anexo E. No basta con conservar el control sobre la decisión; también debe conservarse el control sobre los mecanismos que procesan la información utilizada para tomarla.

---

### 3. Los Cuatro Vectores de Soberanía Operativa

La operación soberana se despliega a través de cuatro vectores complementarios. No compiten entre sí; resuelven perfiles de riesgo distintos en función de la sensibilidad del entorno:

* **Vector 1 — Modelos Locales:** Inferencia ejecutada íntegramente en hardware propio o gestionado, sin tráfico hacia APIs externas.
* **Vector 2 — Wrappers CLI y Agentes de Desarrollo:** Herramientas de razonamiento asistido con acceso controlado al sistema de archivos local y repositorios.
* **Vector 3 — Filtros de Privacidad:** Capa de anonimización y tokenización que permite usar modelos de frontera en nube sin exponer el dato sensible.
* **Vector 4 — Entornos Privados Gestionados:** Infraestructura empresarial segregada (VPC, instancias dedicadas) operada por terceros bajo contratos de retención y auditoría estricta.

---

### 4. Vector 1: Modelos Locales e Inferencia sin Externalización

#### 4.1 La Madurez del Ecosistema y Hardware
En 2026, la inferencia local es técnicamente viable para mantener cargas de trabajo críticas dentro del perímetro. Runtimes como Ollama y entornos como LM Studio permiten desplegar modelos sobre hardware estándar. 

La **cuantización** es el mecanismo habilitador: reduce la precisión numérica de los pesos del modelo (a Q4, Q5 o Q8) para disminuir el consumo de RAM sin destruir la capacidad analítica. Un modelo de 7 o 8 mil millones de parámetros en Q4 opera con fluidez en 8 GB de RAM unificada; un modelo de 27 mil millones requiere entre 16 y 20 GB.

#### 4.2 Criterio de Selección
Cuando el horizonte de confidencialidad dicta que el dato no puede abandonar el perímetro (información regulada, datos personales críticos, secretos industriales), la inferencia local deja de ser una opción y se transforma en la única arquitectura admisible.

#### 4.3 Auditoría del Modelo Local
La soberanía del procesamiento no sustituye la gobernanza técnica. Un modelo local requiere:

1.  **Verificación de origen:** Hash del archivo contra el repositorio oficial.
2.  **Evaluación de comportamiento:** Pruebas controladas antes del despliegue.
3.  **Control de versiones:** Política de actualización documentada.

Un modelo local sin gobernanza técnica no es soberanía operativa; es Shadow AI ejecutado en hardware propio.

---

### 5. Vector 2: Wrappers CLI y Agentes de Desarrollo

#### 5.1 El Riesgo Agéntico
Herramientas como Claude Code o Gemini CLI no son editores de texto; son agentes con acceso al sistema de archivos, terminal y credenciales. La **Regla del 2** descrita en el Anexo K aplica al entorno de desarrollo: el agente tiene acceso a datos sensibles, capacidad de acción real y procesa inputs externos.

#### 5.2 Principio de Mínimo Privilegio
La arquitectura establece:

* **Perímetro explícito de lectura:** Acceso restringido a los directorios necesarios, nunca al repositorio completo por defecto.
* **Confirmación para acciones irreversibles:** Toda modificación de archivos o ejecución de comandos requiere autorización humana explícita.
* **Aislamiento de credenciales:** Tokens y claves API excluidos del contexto del agente.

#### 5.3 El Problema del Contexto
El contexto enviado a modelos en nube contiene lógica propietaria. La organización debe definir qué repositorios pueden procesarse con herramientas conectadas y cuáles exigen el Vector 1.

---

### 6. Vector 3: Filtros de Privacidad

#### 6.1 El Punto Medio
El filtro de privacidad resuelve la tensión entre la limitación de los modelos locales y el riesgo de los modelos de frontera, procesando la información sin exponer la identidad del dato.

#### 6.2 Arquitectura del Filtro y El Secreto Contextual
El flujo requiere tokenización reversible localmente e imposibilidad práctica de reidentificación externa. Además, el filtro debe considerar el **secreto contextual**: la agregación de elementos inocuos (organigramas, modelos operativos) puede revelar información estratégica incluso si se eliminan nombres o RUTs.

---

### 7. Vector 4: Entornos Privados Gestionados

#### 7.1 La Categoría Intermedia
Este modelo de adopción empresarial incluye aislamiento lógico y retención cero de datos para entrenamiento (ej. Azure OpenAI, AWS Bedrock, Google Cloud Vertex AI). 

#### 7.2 Lo que Resuelve y lo que No Resuelve
Permite acceder a capacidades de frontera sin los riesgos de la nube pública generalista. No obstante, no elimina la necesidad de clasificar datos, auditar accesos y supervisar al proveedor. La responsabilidad final del dato pertenece a la organización.

---

### 8. Matriz de Decisión Arquitectónica

La selección responde a la intersección entre clasificación y capacidad:

| Clasificación del Dato | Capacidad Requerida | Vector Recomendado |
| :--- | :--- | :--- |
| **Crítico / No externalizable** | Básica-Media | Vector 1 (Local) |
| **Crítico / No externalizable** | Alta | Vector 1 + rediseño de proceso |
| **Sensible / Regulado** | Básica-Alta | Vector 3 (Filtro) |
| **Sensible / Regulado** | Muy Alta | Vector 3 o Vector 4 (Privado) |
| **Interno / No clasificado** | Básica-Alta | Vector 2 (CLI) o Vector 4 (Privado) |
| **Público** | Cualquiera | Sin restricción |

---

### 9. Implicaciones para la Gobernanza Institucional

La soberanía operativa exige:

* Inventario formal de modelos, wrappers y filtros.
* Clasificación del dato como prerrequisito ineludible.
* Auditoría periódica de anonimización (Vector 3) y accesos agénticos (Vector 2).

---

### 10. Conclusión

La soberanía operativa no consiste en impedir que los datos se muevan, sino en decidir conscientemente cuándo, cómo y bajo qué controles lo hacen. Ningún vector es universalmente superior. La arquitectura correcta es aquella cuya complejidad es proporcional al riesgo que busca controlar.

La organización que prohíbe toda IA renuncia a capacidades estructurales; la que adopta IA sin arquitectura renuncia al control. La organización que no ofrece mecanismos soberanos de adopción no elimina el Shadow AI; simplemente lo desplaza fuera del campo de observación institucional.

La soberanía operativa no se mide por dónde corre el modelo. Se mide por quién conserva el control sobre el dato, la decisión y la trazabilidad del proceso.

> Este anexo complementa la **Guía 09 (Gobernanza)**, el **Anexo E (Soberanía del Criterio)**, el **Anexo H (Seguridad Operativa — LOSA)** y el **Anexo K (Doctrina de IA Agéntica)**.

---

### Notas de Implementación (Actualización 2026)

**Herramientas de referencia:**

* **Ollama / llama.cpp:** Runtimes locales para inferencia.
* **LM Studio:** Entorno de evaluación para despliegues headless.
* **Claude Code / Gemini CLI:** Wrappers agénticos sujetos a políticas de perímetro.

**Modelos locales evaluados (Requerimientos con cuantización Q4):**

| Modelo | Parámetros | RAM mínima (Q4) | Perfil de Operación |
| :--- | :--- | :--- | :--- |
| **Gemma 3** | 4B | 4 GB | Tareas básicas, edge devices |
| **Gemma 3** | 12B | 8 GB | Balance capacidad/recursos |
| **Phi-4** | 14B | 10 GB | Razonamiento técnico |
| **Mistral Small 3.1** | 24B | 16 GB | Multilingüe, razonamiento intermedio |
| **Llama 3.3** | 70B | 40 GB | Alta capacidad, requiere hardware dedicado |