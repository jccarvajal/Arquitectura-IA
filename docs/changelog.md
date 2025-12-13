# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Arquitectura de Inteligencia Artificial: Guías para Decidir, Diseñar y Gobernar"**

---

## Versión 1.3 (Diciembre 2025)

**Motivo:** Consolidación del concepto de "Agencia Humana", integración del marco de **Soberanía y Geopolítica**, y actualización mayor de infraestructura (Migración a MkDocs). Se establece la tesis central de la gobernanza como ingeniería.

### Actualizaciones Estratégicas (Geopolítica y Soberanía)
* **Tesis Central de Gobernanza (Guía 15):** Se incorporó explícitamente la definición fundacional del enfoque GRC del libro: *"La gobernanza no es burocracia legal, es ingeniería de control"*, moviendo el foco de la normativa documental a la arquitectura de sistemas.
* **Prólogo (La Fractura Geopolítica):** Nueva sección "El Veredicto" que analiza el fin de la neutralidad técnica y la competencia entre bloques de IA (Woke vs. Anti-Woke).
* **Guía 15 (Reingeniería):** Renombrada a *"Ética, Soberanía y Confianza"*.
    * **Nueva Parte 5:** Se añadió "Estrategia: Soberanía y Alineación", introduciendo la **Matriz de Decisión** para elegir entre modelos SaaS (Safety-First) y Open Weights (Soberanos) según el riesgo de censura y ubicación de datos.
    * **Riesgo 2.1:** Se profundizó en la "Politización de la Arquitectura" y el sesgo de diseño.

### Actualizaciones Conceptuales (La Capa de Agencia)
* **Conclusión (Nueva Sección):** Se añadió "La Construcción de la Agencia", integrando la visión de Daniel Innerarity sobre la gobernanza como un acto de negociación entre oferta tecnológica y demanda humana.
* **Glosario Expandido:** Nuevos términos críticos: *IA Soberana (Sovereign AI)*, *Alineación Nacional*, *Problema de la Contención* y *Abdicación vs. Aumento*.

### Actualizaciones de Infraestructura y Visualización
* **Migración a MkDocs:** El repositorio migró de Jekyll a MkDocs (Material Theme) para mejorar la navegación, la búsqueda y la experiencia de lectura técnica.
* **Diagramas Vivos (Mermaid.js):** Se reemplazaron descripciones estáticas por diagramas de código renderizados en tiempo real para conceptos críticos:
    * Ciclo ReAct (Guía 05).
    * Arquitectura RAG vs Fine-Tuning (Guía 07).
    * Arquitectura LOSA (Guía 09).
    * Mapa de ROI (Guía 12).

### Referencias y Documentación
* **Bibliografía Blindada:** Nuevo bloque de referencias sobre **Geopolítica y Seguridad** (Anexo F), incluyendo órdenes ejecutivas recientes (2025), *papers* académicos (Loros Estocásticos) y literatura de estrategia (Suleyman/Amodei).

---

## Versión 1.2 (Noviembre 2025)

**Motivo:** Evolución a un estándar de arquitectura corporativa. Cambio de nombre a **"Arquitectura de IA"** para reflejar el enfoque en diseño y gobernanza de sistemas. Integración de estándares internacionales de seguridad (UK Safety Report 2025).

### Cambios Estructurales y de Arquitectura

* **Cambio de Nombre:** El título principal de la obra fue cambiado de *"Inteligencia Artificial Aplicada"* a **"Arquitectura de Inteligencia Artificial"**.
* **Reestructuración Modular:** El sistema de Guías fue reordenado y ampliado a **17 Guías** y **6 Anexos (A-F)**.
* **Nuevas Guías Clave:** Se crearon las guías de **ROI Financiero** (Guía 12), **Ajuste Fino** (Guía 07) y **Anatomía de Modelos** (Guía 01).

### Actualizaciones de Seguridad y Gobernanza (Nov 2025)

* **Validación de LOSA:** Se alineó la arquitectura LOSA con el estándar global de **"Defensa en Profundidad"** (Defence-in-Depth) citado en el reporte de seguridad del Reino Unido.
* **Nuevos Vectores de Riesgo:** Se incorporó el **Envenenamiento de Datos (Data Poisoning)** en la Guía 09, citando la vulnerabilidad crítica ante inserciones mínimas (250 documentos).
* **Estándar de Auditoría:** Se adoptó el concepto de **"Safety Cases"** (Casos de Seguridad) en el Anexo A y Guía 01 como el estándar para justificar despliegues seguros.
* **Observabilidad:** Se refinó el monitoreo para incluir la auditoría de **"Cadena de Pensamiento" (CoT)** en la Guía 11.

### Actualizaciones de Ética y Estrategia

* **Sostenibilidad (Green AI):** Se añadió en la Guía 15 el riesgo de impacto ambiental y la responsabilidad ESG en la selección de modelos.
* **Gestión del Cambio:** Se incorporó la sección de **"Resistencia Inmunológica"** y gestión del sabotaje interno en la Guía 15.
* **Portabilidad:** Se añadió la estrategia de **"Prompt-as-Code"** y desacople de proveedores en la Guía 11 para mitigar el *Vendor Lock-in*.

### Mejoras Didácticas y de Formato

* **Mapa del Territorio:** Inclusión del diagrama conceptual **IA > ML > DL > GenAI** en la Guía 01.
* **Marco CRF-R:** Se insertó explícitamente la síntesis del método de prompting (Contexto, Rol, Formato, Restricciones) en la Guía 02.
* **Sanitización:** Corrección de formatos en bloques de código para asegurar compatibilidad visual en móviles y editores Markdown.

---

## Versión 1.1 (Noviembre 2025)

**Motivo:** Transición a un marco de pensamiento estratégico completo. Consolidación del enfoque GRC.

### Cambios Estratégicos

* **Tesis Central:** El enfoque del libro se centró explícitamente en **GRC (Gobernanza, Riesgo y Cumplimiento)**.
* **Ingeniería de Contexto:** Se elevó el concepto de "Ingeniería de Prompts" a una disciplina de gestión de memoria y contexto.
* **Límites del Transformer:** Definición explícita del **Costo Cuadrático** y la **Amnesia Estática** como limitantes estructurales.

### Gobernanza y Responsabilidad

* **Arquitectura LOSA:** Introducción inicial de la capa *middleware* de seguridad.
* **Roles de Gobernanza:** Definición de "Dueño del Sistema" y "Monitor de Cumplimiento" en la Política Institucional (Anexo B).

---

## Versión 1.0 (Base Inicial)

**Motivo:** Publicación inicial del borrador de contenidos.

* **Lanzamiento:** Publicación del libro en dominio personalizado.
* **Contenido Base:** Principios de "Delegar, No Abdicar" y gestión de riesgos del sector público.