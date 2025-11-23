## Bloque 1: Fundamentos Técnicos (Cómo funciona)

### Guía 01: Anatomía y Entrenamiento de Modelos Generativos
### La capa invisible que determina el Riesgo y la Utilidad

Para decidir, diseñar y gobernar adecuadamente sobre Inteligencia Artificial, es imperativo desmontar la noción de "caja negra". Los modelos generativos modernos (como GPT-4, Claude 3.5 o Llama 3) no son bases de conocimiento ni sistemas de razonamiento lógico en sentido humano: son **motores probabilísticos de predicción**, moldeados a través de múltiples fases de entrenamiento.

Este anexo describe el ciclo de vida técnico que transforma terabytes de texto crudo en un asistente capaz de seguir instrucciones. El objetivo es que el arquitecto decida en función de **criterio de ingeniería**, no de intuición ni del *hype* del mercado.

---

## 1. El Motor Base: Arquitectura Transformer

La generación actual se sustenta en la arquitectura **Transformer** (Vaswani et al., 2017). Su innovación central es el procesamiento paralelo y el **Mecanismo de Atención**, que asigna "pesos" de relevancia entre partes distantes de una secuencia.

### A. Tokenización
Los modelos no procesan palabras, sino **tokens** (fragmentos numéricos).
* **Implicancia Económica:** Un tokenizador ineficiente —especialmente en modelos anglocéntricos aplicados al español— aumenta el costo real de inferencia.
* **Implicancia Técnica:** Más tokens para expresar la misma idea implica mayor latencia y mayor superficie para alucinaciones.

### B. Ventana de Contexto y Atención
La atención permite al modelo relacionar conceptos distantes para mantener coherencia narrativa y lógica.
* **Implicancia de Diseño:** La calidad del razonamiento (lo que algunos llaman "Sistema 2") está limitada por la fidelidad del mecanismo de atención y por el tamaño de la ventana de contexto. Contextos saturados degradan la capacidad instruccional (*Lost in the Middle phenomenon*).

---

## 2. Fase 1: Pre-Entrenamiento (Pre-training)
**El nacimiento del "Modelo Base"**

> **Nota terminológica:** En la industria, el "entrenamiento principal" del modelo se denomina **Pre-Entrenamiento**. Aunque el nombre parezca preliminar, esta es la fase donde realmente se construyen los pesos fundamentales. Las etapas posteriores (SFT, RLHF, RLAIF) no reemplazan esta base; la especializan.

Es la fase de mayor inversión (meses de cómputo en miles de GPUs). El modelo aprende por autosupervisión: predecir el siguiente token o completar textos masivos.

* **Resultado:** Un **Modelo Base** (Foundation Model).
* **Propiedad Clave:** Posee un amplio conocimiento latente, pero carece de capacidad estructurada de seguir instrucciones.

> **⚠️ Riesgo de Gobernanza:** Implementar un Modelo Base creyendo que es un asistente produce incoherencias, sesgos sin filtrar y vulnerabilidad total a inyección de prompts.

---

## 3. Fase 2: Post-Entrenamiento (Post-training)
**La creación del Asistente**

Esta fase convierte al motor estadístico en un sistema útil y seguro. Se divide en capas conductuales y normativas.

### A. SFT (Supervised Fine-Tuning)
Entrenamiento con pares curados **Instrucción -> Respuesta** escritos por humanos.
* **Función:** Enseñar al modelo a estructurar diálogos, seguir pasos y adoptar un tono útil.
* **Riesgo:** **Alucinación Confiada**. El modelo puede dar respuestas erróneas con un tono autoritativo.

### B. RLHF (Reinforcement Learning from Human Feedback)
Capa clásica de alineación.
1.  Humanos ordenan respuestas.
2.  Se entrena un "Modelo de Recompensa".
3.  El LLM se ajusta para maximizar esa recompensa.
* **Limitación:** Puede inducir **Negative Refusal** (rechazo excesivo por sobreprotección ideológica o de seguridad).

### C. RLAIF (Constitutional AI / AI Feedback)
Alineación escalable utilizando **IA supervisando IA**.
* **Mecanismo:** Una "Constitución" de reglas explícitas guía el juicio del modelo supervisor.
* **Ventaja:** Mayor consistencia y menor variabilidad humana.

---

## 4. Resumen Estratégico: Las Capas del Modelo

| Capa | Naturaleza | Función Real | Riesgo Principal |
| :--- | :--- | :--- | :--- |
| **Modelo Base** | Estadística | Predecir tokens | Incoherencia y falta de control. |
| **SFT** | Conductual | Seguir instrucciones | Alucinación confiada. |
| **RLHF/RLAIF** | Normativa | Alinear con valores | Rechazos falsos positivos. |

---

## 5. De la Teoría a la Auditoría: Documentación

Para aplicar GRC, exige la documentación correcta para cada fase:

### 🔍 Model Card (Ficha del Motor)
Documenta la **Fase 1 (Pre-entrenamiento)**.
* **Qué buscar:** Fecha de corte (*cut-off date*), arquitectura técnica, benchmarks de razonamiento y tamaño de contexto.
* **Uso:** Viabilidad técnica y costo de infraestructura.

### 🛡️ System Card (Ficha de Seguridad)
Documenta la **Fase 2 (Post-entrenamiento)**.
* **Qué buscar:** Metodología de alineación, resultados de *Red Teaming*, tasas de rechazo y mitigación de sesgos.
* **Uso:** Cumplimiento normativo, ética y seguridad operativa.

---

## 6. Herramienta Práctica: Checklist de Auditoría

Utilice este cuestionario para evaluar modelos en contextos corporativos o de contratación pública, contrastando la información de la *Model Card* y la *System Card*.

### I. Auditoría del Modelo Base (Model Card)
*Evaluación de capacidades fundamentales y viabilidad técnica.*

| Pregunta de Control | Evidencia Esperada | Riesgo Asociado | Acción Mitigadora |
| :--- | :--- | :--- | :--- |
| **¿Cuál es la fecha de corte del conocimiento?** | Fecha explícita. | Respuestas obsoletas; decisiones incorrectas. | Restringir dominios críticos o usar RAG (Retrieval). |
| **¿Qué arquitectura utiliza y cuántos parámetros tiene?** | Descripción técnica (ej. Dense vs MoE). | Dificultad para estimar costos y latencia. | Solicitar transparencia mínima o benchmarks de inferencia. |
| **¿Cuál es el tamaño de la ventana de contexto?** | Valor en tokens (ej. 128k). | Pérdida de información en tareas largas ("Olvido"). | Fragmentar tareas o usar herramientas de resumen. |
| **¿Cuáles son los resultados en benchmarks estándar?** | MMLU, HumanEval. | Modelo insuficiente para tareas de razonamiento. | Escalar a un modelo más avanzado (Frontier Model). |

### II. Auditoría del Post-Entrenamiento (System Card)
*Evaluación de alineación, seguridad y comportamiento.*

| Pregunta de Control | Evidencia Esperada | Riesgo Asociado | Acción Mitigadora |
| :--- | :--- | :--- | :--- |
| **¿Qué metodología SFT se usó?** | Descripción del dataset. | El modelo no sigue instrucciones de formato. | Afinar *System Prompts* o realizar SFT adicional. |
| **¿Existen resultados de RLHF o RLAIF?** | Detalles del *Reward Model*. | Respuestas peligrosas, tóxicas o ideológicas. | Aplicar filtros externos (Guardrails/LOSA). |
| **¿Se documentaron pruebas de Red Teaming?** | Casuística de ataques. | Fugas de información, *jailbreaks* exitosos. | Implementar capa adicional de seguridad de entrada/salida. |
| **¿Cuáles son las tasas de rechazo (*Refusal Rates*)?** | Métricas de rechazo. | *Negative Refusal*; bloqueo injustificado de tareas. | Ajustar el modelo o cambiar proveedor si es muy restrictivo. |

### III. Dictamen de Auditoría (Plantilla)

**Fecha de Evaluación:** `DD/MM/AAAA`
**Modelo Evaluado:** `[Nombre del Modelo y Versión]`

* **Conclusión Técnica:** `[Viable / No Viable]`
* **Conclusión Normativa:** `[Cumple / No Cumple]`

**Recomendación Final:**
[ ] APROBAR | [ ] APROBAR CON CONDICIONES | [ ] NO APROBAR

---
<div style="display: flex; justify-content: space-between; font-size: 0.9em; padding-top: 10px;">
  <div>
    <a href="../ideas-centrales.md">« Ideas Centrales</a>
  </div>
  <div>
    <a href="../">Volver al Índice</a>
  </div>
  <div>
    <a href="./02-Ingenieria-Prompts.md">Guía 02 »</a>
  </div>
</div>