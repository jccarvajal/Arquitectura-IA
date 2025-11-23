## Anexo D: Plantillas y Recursos

Subtítulo: El "Cinturón de Herramientas" del Arquitecto

### Introducción: El "Cinturón de Herramientas"

Este anexo no es una guía narrativa; es el "cinturón de herramientas" práctico de toda la obra. Es un repositorio centralizado de checklists, plantillas y matrices mencionadas a lo largo de las guías.

No está diseñado para "leerse" de principio a fin, sino para "usarse" como referencia rápida en el trabajo diario de diseño, gobernanza y estrategia de IA.

---

### Sección 1: Diseño de Prompts y Agentes

**Plantilla 1.1: El "Prompt Maestro" (CRF-R: Contexto, Rol, Formato, Restricciones)**
Esta plantilla es un bloque de texto estructurado, diseñado para ser copiado y pegado directamente en tu editor de código o herramienta de prompting. Es la implementación de la Guía 01.

```text
# PLANTILLA DE PROMPT MAESTRO (CRF-R)
#
### 1\. CONTEXTO (El "Por qué" y "Para qué")
\[Proporciona la información de fondo esencial. ¿Cuál es el problema? ¿Qué información necesita la IA para tener éxito? Incluye aquí cualquier dato, texto o historial de conversación relevante.\]

### 2\. ROL (El "Quién")
Actúa como un \[Rol Específico. Ej: "Analista financiero experto", "Redactor de marketing especializado en SEO", "Asistente ejecutivo con 10 años de experiencia"\].
Tu audiencia es \[Público objetivo. Ej: "un comité de gerencia", "clientes nuevos", "un desarrollador junior"\].

### 3\. FORMATO (El "Cómo")
Tu respuesta DEBE estar estructurada exactamente en el siguiente formato:
\[Define la estructura de salida. Sé explícito. Ej: "un objeto JSON con las claves 'resumen' y 'puntos\_clave'", "un email con 'Asunto:' y 'Cuerpo: '", "una tabla en markdown"\].

### 4\. RESTRICCIONES (El "Qué NO hacer")
NO \[Restricción 1\. Ej: "uses jerga técnica"\].
NO \[Restricción 2\. Ej: "excedas las 200 palabras"\].
NO \[Restricción 3\. Ej: "alucines o inventes fuentes. Si no sabes la
respuesta, di 'No tengo información suficiente'"\].
Basa tu respuesta ÚNICAMENTE en el \[Contexto\] proporcionado.
#
# INSTRUCCIÓN DE TAREA (El "Qué")
#
\[Aquí va la tarea o pregunta específica. Ej: "Analiza el texto en el CONTEXTO, extrae los 5 riesgos principales en el FORMATO solicitado, obedeciendo todas las RESTRICCIONES."\]
```

**Plantilla 1.2: Ficha de Diseño de Agente (ReAct)**
Esta ficha sirve como el "plano" de diseño de un agente (Guía 05) antes de construirlo.

| Concepto | Detalle |
| :--- | :--- |
| **Nombre del Agente:** | \[Ej: Agente de Soporte Técnico Nivel 1\] |
| **Propósito Principal:** | \[Definición clara de su objetivo. Ej: "Diagnosticar y resolver problemas comunes de software basándose en la base de conocimiento interna."\] |
| **Input de Usuario (Ejemplo):** | Usuario: "Mi aplicación se cierra sola al abrir un archivo." |
| **Output Deseado (Ejemplo):** | "Entendido. Basado en nuestros registros (Doc-451), ese error se soluciona borrando la caché. ¿Te gustaría que te guíe para hacerlo?" |
| **Herramientas Disponibles:** | 1\. search\_RAG(query): Busca en la base de conocimiento.<br>2\. get\_user\_history(user\_id): Obtiene el historial de tickets del usuario.<br>3\. create\_ticket(summary, priority): Crea un nuevo ticket de soporte. |
| **Plano Cognitivo (Lógica):** | Define el "bucle de pensamiento" del agente.<br>**Iteración 1:**<br>*Pensamiento:* "El usuario tiene un problema. Primero, necesito diagnosticarlo. Usaré search\_RAG para buscar síntomas similares."<br>*Acción:* search\_RAG("aplicación se cierra al abrir archivo")<br>**Iteración 2:**<br>*Observación:* "Se encontró el documento Doc-451 que describe la solución: 'borrar caché'."<br>*Pensamiento:* "Tengo una solución. No necesito más herramientas. Formularé la respuesta al usuario citando la fuente."<br>*Acción:* (Generar respuesta final). |
| **Criterio de Éxito:** | El agente se considera exitoso si resuelve la consulta usando RAG o escala correctamente con create\_ticket si no encuentra solución. |

---

### Sección 2: Gobernanza y Calidad

**Checklist 2.1: Control de Riesgos de Seguridad (Pre-Lanzamiento)**
Esta tabla debe ser completada por el equipo de desarrollo y gobernanza (Guía 07) antes de pasar a producción.

| Riesgo Mitigado | Control Implementado |
| :--- | :--- |
| 1\. Inyección de Prompts | "Firewall de Prompt" (Sanitización de inputs y prompts del sistema robustos). |
| 2\. Fuga de Datos (PII) | Detección y Enmascaramiento de PII (Datos Personales Sensibles) en logs e inputs. |
| 3\. Alucinaciones Operacionales | Monitoreo de Facticidad (Guía 08) y mecanismo de "Humano-en-el-Bucle" (Guía 10) para tareas críticas. |
| 4\. Bucle de Costos | "Interruptor Automático" (Rate Limiter / Presupuesto Máximo) configurado en la API del LLM. |
| 5\. Sesgo y Toxicidad | Filtros de contenido y tono implementados en la salida del modelo. |
| **Aprobación Final de Gobernanza:** | \[Nombre del Responsable\] |

**Plantilla 2.2: Rúbrica de Evaluación de Calidad**
Esta rúbrica (de Guía 08) se usa para calificar las respuestas del "Golden Set" durante las pruebas de QA.

**Prompt ID:** \[Golden-Set-001\] | **Modelo:** \[Ej: GPT-4o\] | **Evaluador:** \[Nombre\] | **Fecha:** \[Fecha\]

| Métrica | Puntaje | Descripción del Puntaje |
| :--- | :--- | :--- |
| **1\. Facticidad (Precisión)** | \[ 1-5 \] | 1: Alucinación grave. Totalmente incorrecto.<br>3: Mayormente correcto, pero con errores menores u omisiones.<br>5: 100% factual, preciso y verificable con las fuentes. |
| **2\. Relevancia (Intención)** | \[ 1-5 \] | 1: Irrelevante. No responde la pregunta del usuario.<br>3: Responde la pregunta literal, pero falla en captar la intención.<br>5: Responde perfectamente a la intención central del usuario. |
| **3\. Tono y Estilo** | \[ 1-3 \] | 1: Tono completamente incorrecto (ej: demasiado informal, robótico).<br>2: Tono aceptable, pero no alineado con el ROL.<br>3: Tono y estilo perfectos, se ajusta al ROL solicitado. |
| **4. Seguridad y Contención** | \[ Pasa / Falla \] | Falla: La respuesta contiene PII, es tóxica, viola una restricción.<br>Pasa: La respuesta es segura y contenida. |
| **Puntaje Total:** | \[ /13 \] | |
| **Notas del Evaluador:** | \[Observaciones cualitativas sobre la respuesta\] | |

---

### Sección 3: Estrategia y Operaciones

**Matriz 3.1: Decisión de Mercado de LLM**
Esta matriz (de Anexo 03) se usa para comparar y seleccionar el modelo de IA (motor) adecuado para un caso de uso específico.

**Caso de Uso:** \[Ej: Chatbot de RAG para consulta de pólizas\]

| Modelo (Motor) | Rendimiento (QA) (Puntaje Guía 08) | Costo (Estimado) (Por Millón de Tokens) | Capacidad (Ventana de Contexto) | Gobernanza (Soberanía) |
| :--- | :--- | :--- | :--- | :--- |
| \[Ej: GPT-4o\] | \[Puntaje: 12/13\] | \[$5.00 (In) / $15.00 (Out)\] | \[128k\] | \[Pública (EEUU)\] |
| \[Ej: Claude 3 Opus\] | \[Puntaje: 11.5/13\] | \[$15.00 (In) / $75.00 (Out)\] | \[200k\] | \[Pública (EEUU)\] |
| \[Ej: Llama 3 70B (Hosteado)\] | \[Puntaje: 10/13\] | \[Variable (Costo de Cómputo)\] | \[8k\] | \[Soberana (Propia Nube)\] |

**Decisión Final:** \[Modelo Seleccionado\]
**Justificación:** \[Razón principal de la elección (ej: "Mejor balance costo-rendimiento para este RAG").\]

**Matriz 3.2: Decisión Estratégica (Guía 12)**
Un framework de 2x2 para decidir para qué usar la IA en un nuevo proyecto.

| (Eje Y \ Eje X) | **INNOVACIÓN BAJA (Hacer lo mismo)** | **INNOVACIÓN ALTA (Hacer cosas nuevas)** |
| :--- | :--- | :--- |
| **EFICIENCIA ALTA (Hacerlo más barato/rápido)** | **Cuadrante 1: Optimización de Procesos.**<br>Descripción: Usar IA para automatizar tareas repetitivas y reducir costos.<br>Ejemplos: Clasificación de emails, resúmenes automáticos, transcripción de reuniones. | **Cuadrante 2: Transformación de Negocio.**<br>Descripción: Usar la eficiencia de la IA (costo marginal cero) para crear nuevos modelos de negocio o servicios que antes eran inviables.<br>Ejemplos: Hiper-personalización a escala (Guía 12), Producto-como-Agente (Blueprint 7). |
| **EFICIENCIA BAJA (Hacerlo al mismo costo/velocidad)** | **Cuadrante 3: Experimentación (PoC).**<br>Descripción: Proyectos de bajo impacto para desarrollar habilidades internas sin un ROI claro.<br>EjemplOS: Un bot de Slack interno para diversión, pruebas de concepto desechables. | **Cuadrante 4: Investigación y Desarrollo (I+D).**<br>Descripción: Proyectos de alto costo/esfuerzo para crear capacidades completamente nuevas. El ROI no es inmediato.<br>Ejemplos: Desarrollar un "Agente Director" (Blueprint 3) o un modelo con Ajuste Fino (Anexo 05) por primera vez. |

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="./C-Blueprints.html">« Anexo C</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
  <div>
    <a href="./E-Glosario.html">Anexo E »</a>
  </div>
</div>