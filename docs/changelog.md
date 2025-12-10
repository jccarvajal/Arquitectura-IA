# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Arquitectura de Inteligencia Artificial: Guías para Decidir, Diseñar y Gobernar"**

---

## Versión 1.3 (Diciembre 2025)

**Motivo:** Consolidación del concepto de "Agencia Humana" y actualización mayor de infraestructura. Migración a plataforma de documentación técnica (MkDocs) y validación filosófica post-lanzamiento (Innerarity).

### Actualizaciones Conceptuales (La Capa de Agencia)

* **Conclusión (Nueva Sección):** Se añadió "La Construcción de la Agencia", integrando la visión de Daniel Innerarity sobre la gobernanza como un acto de negociación entre oferta tecnológica y demanda humana.
* **Guía 15 (Nuevo Riesgo):** Se incorporó la "Politización de la Arquitectura" (Riesgo 2.1), abordando el sesgo intencional de diseño (Caso Grok) y la no-neutralidad de los modelos.
* **Bibliografía Blindada:** Inclusión de referencias críticas sobre teoría política de la IA en el Anexo F.

### Actualizaciones de Infraestructura y Visualización

* **Migración a MkDocs:** El repositorio migró de Jekyll a **MkDocs (Material Theme)** para mejorar la navegación, la búsqueda y la experiencia de lectura técnica.
* **Diagramas Vivos (Mermaid.js):** Se reemplazaron descripciones estáticas por diagramas de código renderizados en tiempo real para conceptos críticos:
    * **Ciclo ReAct** (Guía 05).
    * **Arquitectura RAG vs Fine-Tuning** (Guía 07).
    * **Arquitectura LOSA** (Guía 09).
    * **Mapa de ROI** (Guía 12).

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