# Anexo E: Mapeo de Gobernanza Global (ISO/IEC 42001 y NIST AI RMF)

### 1. Introducción: El Andamiaje de la Certificación

Este anexo actúa como el puente técnico entre la arquitectura de "Sistema 1 y Sistema 2" propuesta en esta obra y los marcos de gobernanza internacionalmente reconocidos. Para el Arquitecto de IA, estos estándares no son burocracia, sino el "manual de vuelo" para operar sistemas complejos de forma segura y auditable.

La implementación de las guías de este libro permite a las organizaciones alinearse con:
* **ISO/IEC 42001:** El primer estándar internacional de sistemas de gestión de IA (AIMS).
* **NIST AI Risk Management Framework (RMF 1.0):** El marco de referencia global para la gestión de riesgos de IA.

---

### 2. Tabla de Correspondencia Operativa

Este mapeo permite identificar cómo los conceptos técnicos del libro cumplen con los requisitos de cumplimiento global.

| Función NIST AI RMF | Control / Cláusula ISO 42001 | Implementación en la Obra | Referencia |
| :--- | :--- | :--- | :--- |
| **GOVERN (Gobernar)** | Cláusulas 5 (Liderazgo) y 6 (Planificación) | **Política Institucional:** Definición de roles, responsabilidades y rendición de cuentas. | Guía 09, Anexo B |
| **MAP (Mapear)** | Control A.5: Evaluación de Impacto | **Triage de Viabilidad:** Identificación de contextos, riesgos y stakeholders pre-diseño. | Guía 01, Anexo A |
| **MEASURE (Medir)** | Cláusula 9: Evaluación de Desempeño | **Laboratorio de QA:** Uso de *Golden Sets* y métricas de ingeniería (precisión, sesgo, costo). | Guía 10 |
| **MANAGE (Gestionar)** | Control A.8: Ciclo de Vida del Sistema | **Industrialización:** Gestión de cambios, *Prompt-as-Code* y observabilidad operativa. | Guía 11 |

---

### 3. La Operacionalización del "Sistema 2" en la Norma

Para certificar un sistema bajo la **ISO/IEC 42001**, la organización debe demostrar que el **Sistema 2 humano** mantiene el control efectivo sobre el **Sistema 1 algorítmico**. Este libro facilita dicho cumplimiento mediante tres pilares:

1.  **Prevención de la Abdicación:** La norma exige la "Rendición de Cuentas". Esto se cumple aplicando el **Axioma de la Responsabilidad Indelegable**.
2.  **Mitigación de la Estupidez Artificial:** El control de riesgos se operativiza mediante el **Checklist de Juicio Humano** del Anexo A, asegurando que la IA sea un aumento y no un sustituto del criterio profesional.
3.  **Resiliencia Financiera:** La gestión de recursos exigida por ISO se garantiza mediante la **Regla de Oro de la Economía Unitaria**.

---

### 4. Guía de Auditoría para el Arquitecto

Al enfrentar un proceso de auditoría o debida diligencia (*Due Diligence*), el Arquitecto debe presentar las siguientes evidencias derivadas de este marco de trabajo:

* **Evidencia de Selección:** *System Cards* y fichas técnicas del modelo evaluadas bajo el Triage de la Guía 01.
* **Evidencia de Diseño:** El uso del **Prompt Maestro (CRF-R)** como mecanismo de alineación y control de riesgos.
* **Evidencia de Control:** Registros de **Simetría de Acción** (logs de *Undo* y *Kill-Switch*) que demuestran la capacidad de interferir eficazmente en la operación de la máquina.

!!! success "Hacia un Estándar de Confianza"
    Alinear su fábrica de IA con la ISO 42001 y el NIST RMF no es un acto burocrático; es la garantía de que su arquitectura es **robusta, ética y comercialmente viable** a largo plazo.
