# Anexo H: Puntos de Control de Seguridad Operativa (Capa LOSA)

## 1. El Concepto: La "Aduana de Inferencia Operativa" en la Práctica

La arquitectura **LOSA (Layer of Safety & Alignment)** no es una sugerencia para el modelo, sino una infraestructura de seguridad perimetral que envuelve la **capa de inferencia estadística**. Opera bajo el principio de **Confianza Cero (Zero Trust)**: se asume que todo *input* es potencialmente malicioso y que el modelo, por su naturaleza probabilística, es ingenuo ante la manipulación sintáctica y semántica.

Como "Aduana de Inferencia Operativa", la LOSA inspecciona, sanitiza y valida cada interacción desde una perspectiva de riesgo operacional **antes** de permitir su ejecución o visualización, actuando como un cortafuegos determinístico frente a la variabilidad del Sistema 1.

---

## 2. Los Tres "Peajes" de Control Operativo

Para cumplir con estándares de seguridad consolidados en la práctica reciente (como **OWASP Top 10 for LLM**), la arquitectura debe implementar controles obligatorios en tres estadios del ciclo de vida de la transacción:

### I. Entrada (Input Hardening): El Escáner de Seguridad
* **Sanitización de Prompts (Mitigación LLM01):** Detección activa de patrones de *Jailbreak*, inyección de delimitadores y neutralización de caracteres de control para separar las instrucciones del sistema ("System Prompt") de los datos no confiables del usuario.
* **Cuarentena de Contexto (Sandboxing):** Protocolo de aislamiento para datos de terceros (RAG, PDFs, webs). Estos datos se tratan estrictamente como "material de referencia pasivo" y nunca como instrucciones ejecutables, previniendo la **Inyección Indirecta de Prompts**.

### II. Proceso (In-Flight Monitoring): Vigilancia de Ejecución
* **Circuit Breakers de Recursos (Mitigación LLM04/LLM10):** Interruptores automáticos que detienen el flujo si se detecta un **Bucle de Costos**, consumo excesivo de tokens o una actividad transaccional que exceda los límites presupuestarios definidos.
* **Monitoreo de Ejecución y Cumplimiento:** Auditoría en tiempo real de señales de coherencia lógica, cumplimiento de políticas y desviaciones operativas, con el objetivo de identificar lógicas hostiles o intentos de "secuestro de políticas" antes de que el agente ejecute una acción irreversible. **Este mecanismo no expone ni registra la Chain-of-Thought del modelo, sino únicamente evidencia técnica suficiente para control y trazabilidad.**

### III. Salida (Output Sanitization): El Filtro de Integridad
* **Enmascaramiento de PII (Mitigación LLM06):** Identificación y redacción automática de datos personales sensibles (*Personally Identifiable Information*) mediante Regex o modelos NER locales antes de la entrega final.
* **Validación de Grounding (Mitigación LLM09):** Verificación técnica de que la respuesta contiene citas válidas y está "anclada" a las fuentes documentales proporcionadas, mitigando las **Alucinaciones Operacionales**.

---

## 3. Matriz de Intersección GRC (LOSA)

Esta matriz vincula los controles técnicos con los pilares de resiliencia del libro y los riesgos globales de industria.

| Punto de Control | Riesgo Mitigado (Ref. OWASP LLM) | Tipo de Control | Pilar de Resiliencia |
| :--- | :--- | :--- | :--- |
| **Filtro de Inyección** | **LLM01:** Prompt Injection | Preventivo | **Pilar 7:** Robustez Inyección |
| **Limitador Financiero** | **LLM04:** Denial of Service / Resource | Preventivo + Detectivo | **Pilar 6:** Hard Caps |
| **Redacción de Datos** | **LLM06:** Sensitive Info Disclosure | Correctivo | **Pilar 13:** Minimización |
| **Validación de Fuente** | **LLM02/LLM09:** Insecure Output / Overreliance | Preventivo + Detectivo | **Pilar 12:** Procedencia Datos |

---

## 4. Checklist de Auditoría para el Arquitecto LOSA

*Este checklist debe ser completado y adjuntado al **Expediente Técnico** de cada agente antes de su paso a producción.*

* [ ] **Independencia de Capa:** ¿La seguridad reside en un *middleware* externo (código duro) y no depende exclusivamente de las instrucciones verbales del *System Prompt*?
* [ ] **Mecanismo de Rollback:** ¿Existe una función técnica de "Deshacer" o "Compensar" para todas las acciones de escritura ejecutadas por el agente?
* [ ] **Muestreo Inteligente:** ¿Se ha configurado una auditoría sorpresa (ej. 5% de las transacciones) para combatir la **Complacencia de la Automatización** en los operadores humanos?
* [ ] **Trazabilidad Forense:** ¿Cada intervención de la capa LOSA (bloqueos, sanitizaciones, alertas) genera un log de **Evidencia de Ejecución** inmutable para el análisis de causa raíz, separado del log conversacional?
* [ ] **Fallo Seguro (Fail-Safe):** En caso de caída de la API del modelo o error de la capa LOSA, ¿el sistema entra en estado de bloqueo seguro (negar todo) en lugar de permitir el paso libre (*Fail-Open*)?

---

!!! success "Sinergia con la Guía 09"
    Mientras la **Guía 09** define el "Apetito de Riesgo" y la política institucional, el **Anexo H** provee la infraestructura de control para ejecutar dicha política. La robustez de la arquitectura LOSA garantiza que, ante un fallo del modelo o un ataque adversarial, la organización conserve la soberanía operativa sin depender de la introspección del modelo.
