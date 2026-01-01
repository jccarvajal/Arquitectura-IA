# Anexo H: Puntos de Control de Seguridad Operativa (Capa LOSA)

## 1. El Concepto: La "Aduana Cognitiva" en la Práctica

La arquitectura **LOSA (Layer of Safety & Alignment)** no es una sugerencia para el modelo, sino una infraestructura de seguridad perimetral que envuelve la capa de razonamiento. Opera bajo el principio de **Confianza Cero (Zero Trust)**: se asume que todo input es potencialmente malicioso y que el modelo, por su naturaleza probabilística, es ingenuo ante la manipulación.

Como "Aduana Cognitiva", la LOSA inspecciona, sanitiza y valida cada interacción desde una perspectiva de riesgo operacional, antes de permitir su ejecución o visualización.

---

## 2. Los Tres "Peajes" de Control Operativo

Para cumplir con el estándar **OWASP Top 10 LLM (2025)**, la arquitectura debe implementar peajes obligatorios en tres momentos del ciclo de vida de la inferencia:

### I. Entrada (Input Hardening): El Escáner de Seguridad
* **Sanitización de Prompts (LLM01):** Detección activa de patrones de *Jailbreak* y el uso de delimitadores estructurales para separar las instrucciones del sistema de los datos no confiables del usuario.
* **Cuarentena de Datos (Sandboxing):** Protocolo de aislamiento para datos de terceros (RAG, PDFs, sitios web). Los datos se tratan como "material de lectura" y nunca como "comandos de mando", evitando la **Inyección Indirecta de Prompts**.

### II. Proceso (In-Flight Monitoring): Vigilancia de Ejecución
* **Circuit Breakers (LLM10):** Interruptores automáticos que detienen el flujo si se detecta un **Bucle de Costos** o una actividad transaccional que exceda los límites presupuestarios definidos.
* **Monitoreo de Razonamiento (Evidencia de Ejecución):** Auditoría en tiempo real de señales de coherencia lógica y cumplimiento de políticas, sin exposición del Chain-of-Thought al usuario final, antes de que el agente realice una acción irreversible.

### III. Salida (Output Sanitization): El Filtro de Integridad
* **Enmascaramiento de PII (LLM02):** Identificación y redacción automática de datos personales sensibles antes de la entrega final.
* **Validación de Grounding:** Verificación técnica de que la respuesta está "anclada" a las fuentes verificables, mitigando las **Alucinaciones Operacionales**.

---

## 3. Matriz de Intersección GRC (LOSA)

Esta matriz vincula los peajes técnicos con los pilares de resiliencia del libro y los riesgos globales de industria.

| Punto de Control | Riesgo Mitigado (OWASP 2025) | Tipo de Control | Pilar de Resiliencia |
| :--- | :--- | :--- | :--- |
| **Filtro de Inyección** | **LLM01:** Inyección de Prompt | Preventivo | **Pilar 7:** Robustez Inyección |
| **Limitador Financiero** | **LLM10:** Consumo Ilimitado | Preventivo + Detectivo | **Pilar 6:** Hard Caps |
| **Redacción de Datos** | **LLM02:** Fuga de Información | Correctivo | **Pilar 13:** Minimización |
| **Validación de Fuente** | **LLM09:** Desinformación | Preventivo + Detectivo | **Pilar 12:** Procedencia Datos |

---

## 4. Checklist de Auditoría para el Arquitecto LOSA

*Este checklist debe ser completado y adjuntado al **Expediente Técnico** de cada agente antes de su paso a producción.*

* [ ] **Independencia de Capa:** ¿La seguridad reside en un *middleware* externo y no depende exclusivamente de las instrucciones del prompt del sistema?.
* [ ] **Mecanismo de Rollback:** ¿Existe una función técnica de "Deshacer" para todas las acciones de escritura ejecutadas por el agente?.
* [ ] **Muestreo Inteligente:** ¿Se ha configurado una auditoría sorpresa del 5% de las transacciones para combatir la **Complacencia de la Automatización**?.
* [ ] **Trazabilidad Forense:** ¿Cada intervención de la capa LOSA (bloqueos, ediciones, alertas) genera un log inmutable para análisis de causa raíz?.

---

!!! success "Sinergia con la Guía 09"
    Mientras la **Guía 09** define el "Apetito de Riesgo" y la política institucional, el **Anexo H** provee la infraestructura de control para ejecutar dicha política. La robustez de la arquitectura LOSA garantiza que, ante un fallo del modelo, la organización conserve la soberanía operativa.
