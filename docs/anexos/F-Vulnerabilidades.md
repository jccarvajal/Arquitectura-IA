# Anexo F: Atlas de Vulnerabilidades Lógicas y Resiliencia del Sistema

## 1. Introducción: La Inferencia como Superficie de Ataque

La seguridad de una arquitectura de IA no se limita a la protección de datos ni al cifrado de red. En este anexo se establece que el lenguaje natural y la lógica formal constituyen **vectores de ataque críticos**. Un sistema resiliente debe ser capaz de procesar *inputs* maliciosos, persuasivos o erróneos sin degradar su **Fidelidad Semántica** ni comprometer su **Soberanía Operativa**.

Este Atlas consolida las **vulnerabilidades estructurales** de los Modelos de Lenguaje (Sistema 1), clasificándolas en cuatro dimensiones de riesgo operativo, cuya mitigación exige controles externos explícitos (Sistema 2).

---

## 2. Definiciones de las Dimensiones de Vulnerabilidad

A continuación, se describen las principales familias de fallos que todo arquitecto, auditor o responsable de GRC debe considerar y mitigar. La terminología utilizada corresponde a conceptos consolidados en la práctica operativa reciente (2024–2025).

Las cuatro dimensiones clasifican los fallos según el plano en el que se degrada el control:

* **I. Retórica:** Fallos inducidos por la forma persuasiva del lenguaje de entrada que provocan la violación de controles sin alterar la arquitectura del sistema.
* **II. Emergente:** Fallos emergentes del comportamiento estadístico interno que surgen del comportamiento interno y probabilístico del modelo, incluso ante *inputs* benignos, por efectos de auto-referencia, optimización o razonamiento extendido.
* **III. Ética-Normativa:** Fallos derivados de una jerarquización incorrecta de principios éticos u obligaciones regulatorias que conduce a incumplimiento o parálisis operativa.
* **IV. Operativa:** Fallos originados en el diseño, despliegue o coordinación del sistema en producción que amplifican el impacto del error más allá del razonamiento individual del modelo.

---

## 3. Matriz de Riesgo Semántico

| Dimensión | Tipo de Fallo | Concepto Operativo | Riesgo GRC Principal |
| :--- | :--- | :--- | :--- |
| **I. Retórica** | **Ad Verecundiam / Ad Misericordiam** | *Adversarial Persuasion* | **Suplantación de Autoridad:** Salto de protocolos por simulación de urgencia, jerarquía o victimización falsa. |
| **I. Retórica** | **Red Herring / Cortina de Humo** | *Context Distraction* | **Inyección Indirecta:** Ocultamiento de instrucciones maliciosas dentro de grandes volúmenes de información legítima. |
| **II. Emergente** | **Bucle Tautológico** | *Feedback Loop Hallucination* | **Corrupción de Auditoría:** El sistema valida sus propios errores previos como hechos dentro de la ventana de contexto. |
| **II. Emergente** | **Sycophancy (Adulación)** | *Reward Hacking* / Complacencia | **Falsedad Sistémica:** Generación de inexactitudes fácticas para maximizar la alineación percibida con el usuario. |
| **III. Ética-Norm.** | **Falso Balance / Equidistancia** | *False Neutrality Bias* | **Incumplimiento Normativo:** Tratamiento neutral ante hechos objetivamente ilegales o contrarios a políticas internas. |
| **III. Ética-Norm.** | **Secuestro de Políticas** | *Moral Hijacking* | **Parálisis Operativa:** Uso instrumental de principios éticos para bloquear funciones legítimas del sistema. |
| **IV. Operativa** | **Deriva de Inferencia** | *Reasoning Drift* | **Degradación Lógica:** La calidad de la decisión se degrada de forma acumulativa y no lineal en procesos multi-paso. |
| **IV. Operativa** | **Alucinación Operacional** | *Factuality Failure* | **Decisión Errónea:** Ejecución de acciones irreversibles basadas en información no verificada o inexistente. |

---

## 4. Matriz de Intersección: Vulnerabilidades vs. Pilares de Control

Cada vulnerabilidad identificada debe mapearse explícitamente a uno o más de los **20 Pilares de Control** definidos en esta arquitectura.

| Vulnerabilidad Detectada | Pilar de Mitigación Primario | Mecanismo de Control |
| :--- | :--- | :--- |
| **Sycophancy (Adulación)** | **Pilar 9:** Fidelidad Semántica | Contraste obligatorio con fuentes externas inmutables (RAG / Grounding) previo a la generación. |
| **Bucle Tautológico** | **Pilar 19:** Expediente Técnico | Trazabilidad inmutable de inferencias y saneamiento periódico de la ventana de contexto. |
| **Alucinación Operacional** | **Pilar 10:** Verificabilidad | Política de **Abstención Obligatoria** (System 2 Override) ante ausencia de evidencia suficiente, independientemente de la confianza lingüística. |
| **Falsa Dicotomía** | **Pilar 17:** Explicabilidad | Obligación de explorar y documentar “terceras vías” antes de forzar decisiones binarias. |
| **Reasoning Mode Collapse** | **Pilar 12:** RAG (Knowledge) | Inyección sistemática de casos de borde y eventos de baja frecuencia (Cisnes Negros). |
| **Secuestro de Políticas** | **Pilar 3:** Inmutabilidad (PaC) | Anclaje de reglas críticas en código duro (*middleware*), no en *prompts* de sistema. |

---

## 5. Definiciones Técnicas de Frontera

### A. Sycophancy (Adulación Sistémica)
Tendencia estadística del modelo a priorizar la probabilidad de aceptación del usuario por sobre la veracidad fáctica, validando premisas incorrectas para maximizar utilidad percibida.

### B. Alucinación Operacional
Producción de respuestas accionables en ausencia de evidencia suficiente, cuando el comportamiento correcto era la abstención. Su impacto es directo sobre la cadena de valor.

### C. Reasoning Drift (Deriva de Inferencia)
Acumulación progresiva de errores probabilísticos menores en cadenas de razonamiento extensas, conduciendo a conclusiones inconsistentes con las premisas iniciales sin error sintáctico detectable.

### D. False Neutrality Bias (Falso Balance)
Aplicación indebida de neutralidad a escenarios binarios de cumplimiento normativo, generando ambigüedad donde existe obligación clara.

### E. Reasoning Mode Collapse (Colapso de Modo)
Reducción de la diversidad inferencial ante complejidad elevada, produciendo respuestas genéricas y conservadoras que degradan la efectividad del sistema.

---

## 6. Protocolo de Certificación: El Test del Sofista
*(Ensayo de Resiliencia Lógica y Retórica)*

Ninguna instancia de IA o agente autónomo debe entrar en producción sin un certificado formal de **Resiliencia Lógica**. El protocolo incluye pruebas adversariales controladas con métricas objetivas:

1. **Prueba de Inmunidad a la Adulación**
    * **Objetivo:** Inyección de premisas falsas para inducir validación.
    * **Benchmark:** Ratio de rechazo ≥ 98 %.
2. **Prueba de Resistencia Retórica**
    * **Objetivo:** Ataques de apelación emocional o urgencia (*Ad Misericordiam*).
    * **Benchmark:** Tasa de *bypass* = 0 % (tolerancia cero).
3. **Validación de Compresión Semántica**
    * **Objetivo:** Verificar preservación de cláusulas obligatorias en resúmenes normativos.
    * **Benchmark:** Pérdida de fidelidad semántica ≤ 2 %.

---

## 7. Evidencias, Logs y Métricas de Resiliencia

### Propósito Normativo
Esta sección define los artefactos verificables que demuestran que las vulnerabilidades lógicas no solo están descritas, sino activamente controladas. Su función es cerrar la brecha entre análisis conceptual y evidencia auditora. **Ningún control descrito en este Anexo se considera efectivo sin evidencia técnica asociada.**

### 7.1 Tipología de Evidencias Exigidas
Toda mitigación debe generar al menos uno de los siguientes tipos de evidencia:

* **Evidencia Preventiva:** Demuestra que el fallo no puede ejecutarse (bloqueo *a priori*).
* **Evidencia Detectiva:** Demuestra que el fallo es identificado oportunamente (alerta *in-flight*).
* **Evidencia Correctiva:** Demuestra capacidad de contención y reversión (recuperación *post-hoc*).

Estas evidencias forman parte obligatoria del Expediente Técnico del Agente.

### 7.2 Matriz de Evidencias por Vulnerabilidad

| Vulnerabilidad | Evidencia Requerida | Tipo de Evidencia | Métrica Clave |
| :--- | :--- | :--- | :--- |
| **Sycophancy (Adulación)** | Registro de contraste RAG + rechazo explícito de premisas falsas | Preventiva | % de respuestas con refutación explícita |
| **Bucle Tautológico** | Logs de limpieza de contexto y hashes de sesión | Detectiva | Nº de autoreferencias por sesión |
| **Alucinación Operacional** | Evento de abstención forzada (System 2 Override) | Correctiva | Ratio de abstención justificada |
| **Deriva de Inferencia** | Traza técnica de inferencia multi-paso con *checkpoints* | Detectiva | Variación semántica acumulada |
| **Secuestro de Políticas** | Log de colisión entre ética y operación | Preventiva | Tiempo medio de resolución |
| **Falso Balance** | Registro de decisión normativa explícita | Correctiva | % de decisiones no neutrales |

### 7.3 Logs Forenses Obligatorios
La arquitectura debe generar logs inmutables, con retención mínima definida por política institucional, que incluyan:

* Identificador único de sesión y transacción.
* *Hash* del *input* original (integridad).
* Vulnerabilidad detectada (si aplica).
* Pilar de control activado.
* Acción ejecutada (rechazo, abstención, escalamiento).
* *Timestamp* sincronizado.
* Identidad del agente o sistema invocador.

**Nota:** Estos logs son no opcionales y deben ser accesibles para auditoría interna y externa.

### 7.4 Métricas de Resiliencia Operativa
Las siguientes métricas deben ser monitoreadas y reportadas periódicamente:

* Índice de Fidelidad Semántica.
* Tasa de Abstención Correcta.
* Ratio de *Bypass* Ético.
* Latencia Introducida por Controles LOSA.
* Tasa de Incidentes por Dimensión (I–IV).

La degradación sostenida de cualquiera de estas métricas activa un evento de revisión obligatoria del agente.

### 7.5 Criterio de Aprobación para Producción
Un agente solo puede ser autorizado para producción si:

1. Todas las vulnerabilidades del Anexo F tienen evidencia asociada.
2. Las métricas clave cumplen los umbrales definidos.
3. El Expediente Técnico se encuentra completo y firmado.
4. El "Test del Sofista" ha sido aprobado.

**La ausencia de evidencia se considera fallo de control, incluso si no existe incidente registrado.**

---

!!! success "Declaración de Integridad y Auditoría"
    Este anexo, en sus **partes 1 a 6**, identifica y sistematiza las **familias de fallos** inherentes a arquitecturas de IA en producción.  

    La **parte 7** establece los **mecanismos de control y evidencia operativa** que permiten demostrar su mitigación efectiva.

    Sin **evidencia técnica verificable**, la resiliencia es solo una declaración teórica.  

    Con evidencia, la arquitectura se vuelve **gobernable**, **auditable** y **defendible** frente a exigencias regulatorias, operativas y forenses.
