# Anexo F: Marco Regulatorio Global (EU AI Act)

### 1. Introducción: El "Efecto Bruselas" en la IA

Aunque esta obra se centra en el criterio de ingeniería y gestión, es imposible gobernar la IA sin entender el marco legal que está definiendo los estándares globales: la **Ley de Inteligencia Artificial de la Unión Europea (EU AI Act)**. 

Al igual que ocurrió con el GDPR en privacidad, esta ley establece un "Efecto Bruselas", donde las organizaciones fuera de Europa adoptan estos estándares para garantizar su resiliencia legal y competitividad. Este anexo proporciona la clasificación de riesgos necesaria para priorizar los controles de GRC.

---

### 2. Clasificación de Riesgos y Obligaciones

La normativa europea clasifica los sistemas de IA en cuatro niveles, permitiendo al Arquitecto definir la intensidad de la supervisión del **Sistema 2** humano.

| Nivel de Riesgo | Descripción / Ejemplos | Obligación Principal | Vínculo con esta Obra |
| :--- | :--- | :--- | :--- |
| **Inaceptable** | Sistemas que manipulan el comportamiento o realizan *Social Scoring*. | **Prohibición Total** | Líneas Rojas y Ética |
| **Alto Riesgo** | IA en infraestructura crítica, educación, empleo o salud. | **Auditoría y Supervisión Humana Obligatoria** | Guías de Industrialización y QA |
| **Limitado** | Chatbots y sistemas de generación de contenidos. | **Transparencia (Revelar que es IA)** | Ingeniería de Prompts |
| **Mínimo** | Filtros de spam o aplicaciones de entretenimiento. | **Sin obligaciones adicionales** | Zona Azul de ROI |

---

### 3. Alineación con la Tesis de la Obra

La **EU AI Act** codifica legalmente la necesidad de evitar la **abdicación del juicio humano** que defendemos en esta arquitectura.

* **Supervisión Humana (Art. 14):** Exige que los sistemas de alto riesgo permitan una supervisión efectiva por personas naturales. Esto equivale a la implementación mandatoria del **Sistema 2**.
* **Gobernanza de Datos (Art. 10):** Valida la **Guía 04**, exigiendo que los datos de entrenamiento sean pertinentes, representativos y libres de errores sistémicos.
* **Transparencia:** Refuerza la necesidad de una **IA Explicable (XAI)** para que el operador pueda validar el resultado antes de actuar.

---

### 4. Resumen para el Arquitecto: El "Compliance" como Ventaja

1.  **Evidencia de Triage:** El uso del **Anexo A** para clasificar el riesgo del proyecto antes de iniciar.
2.  **Responsabilidad Indelegable:** Cumplimiento del principio de que el humano es el único responsable legal por las acciones del sistema.
3.  **Seguridad Operativa:** La obligatoriedad de controles técnicos para mitigar alucinaciones y sesgos.

!!! tip "Recomendación Estratégica"
    Si su proyecto califica como de **Alto Riesgo**, la aplicación del **Checklist de Juicio Humano** (Sección 6 del Anexo A) es la evidencia técnica que protege a la organización ante auditorías regulatorias.
