# Arquitectura de Inteligencia Artificial
## Guías para Decidir, Diseñar y Gobernar

**Versión 1.6 (Enero 2025)**

**Autor:** [Juan Carlos Carvajal](https://www.jccarvajal.com/)

<img src="assets/images/portada-ia.png" alt="Portada del Libro - Arquitectura de Inteligencia Artificial" width="500">

---

## Descripción del Proyecto

Esta obra no es un libro tradicional; es una **documentación técnica y estratégica** diseñada para cerrar la brecha entre la experimentación con Inteligencia Artificial y su implementación productiva en organizaciones.

Mientras el mercado se enfoca en las herramientas ("qué modelo usar"), este repositorio se enfoca en el **criterio de ingeniería y gestión** ("cómo construir sistemas fiables").

El objetivo es proporcionar un **Marco de GRC (Gobernanza, Riesgo y Cumplimiento)** que permita a líderes técnicos y estratégicos:

1.  **Decidir** con base en la viabilidad técnica y el valor de negocio (no en el *hype*).
2.  **Diseñar** sistemas cognitivos robustos utilizando patrones de ingeniería (RAG, Agentes, CoT).
3.  **Gobernar** la operación mitigando riesgos de seguridad, alucinaciones y asegurando la rentabilidad.

---

## Tesis Central: GRC y Sinergia

La premisa fundamental es que la IA generativa actual opera como un "Sistema 1" (rápido, probabilístico, sin juicio). Para su implementación segura, requiere una arquitectura que delegue la ejecución táctica pero mantenga la responsabilidad estratégica ("Sistema 2") en el operador humano.

Este repositorio propone el principio de **"Delegar, no Abdicar"**, implementado a través de controles técnicos de Ciberseguridad y políticas de uso que aseguran la trazabilidad y la ética en la toma de decisiones.

---

## Estructura de la Documentación

El contenido está organizado modularmente siguiendo el ciclo de vida de un proyecto de IA.

### Introducción
Marco conceptual y filosófico.

* [Nota al Lector](./nota-al-lector.md)
  *Alcance y definición de roles (Arquitecto vs. Profesional).*
* [Prólogo: Fundación](./prologo.md)
  *Bases teóricas (Kahneman, Dreyfus, Taleb).*
* [Ideas Centrales](./ideas-centrales.md)
  *Resumen ejecutivo de los conceptos clave.*

### Bloque 1: Fundamentos y Mecánica (Guías 1 a 4)
Comprensión de las capacidades y límites del motor.

* [Guía 01: Anatomía de Modelos](./guias/01-Anatomia-Modelos.md)
  *Arquitectura LLM, Hardware y el ciclo ML (Training-Inference).*
* [Guía 02: Ingeniería de Prompts](./guias/02-Ingenieria-Prompts.md)
  *Diseño de instrucciones deterministas y el método CRF-R.*
* [Guía 03: Contexto y Memoria](./guias/03-Contexto-Memoria.md)
  *Gestión de memoria, RAG vs. Memoria Explícita y Amnesia Estática.*
* [Guía 04: Estrategia de Datos](./guias/04-Estrategia-Datos.md)
  *Gobernanza de la fuente y el pipeline ETL-V.*

### Bloque 2: Arquitectura y Construcción Avanzada (Guías 5 a 8)
Diseño del sistema agente, especialización y validación del prototipo.

* [Guía 05: Ingeniería de Agentes](./guias/05-Ingenieria-Agentes.md)
  *Orquestación y Ciclos ReAct (El motor del Agente).*
* [Guía 06: Sistemas Cognitivos](./guias/06-Sistemas-Cognitivos.md)
  *Patrones de razonamiento (Chain of Thought, Tree of Thoughts).*
* [Guía 07: Ajuste Fino (Fine-Tuning)](./guias/07-Fine-Tuning.md)
  *Guía técnica para especializar un motor: RAG vs. Fine-Tuning.*
* [Guía 08: Prototipado](./guias/08-Prototipado.md)
  *Metodología del Quick Win y Gobernanza Mínima Viable.*

### Bloque 3: Operación y GRC (Guías 9 a 12)
El paso a producción: seguridad, calidad y monitoreo de la fábrica.

* [Guía 09: Gobernanza](./guias/09-Gobernanza.md)
  *Arquitectura LOSA y control de riesgos (Inyección, Shadow AI).*
* [Guía 10: Evaluación y QA](./guias/10-Evaluacion-Calidad.md)
  *El Golden Set Vivo y Protocolo de Validación Semántica.*
* [Guía 11: Industrialización](./guias/11-Industrializacion.md)
  *Observabilidad Ampliada y LLM-Ops.*
* [Guía 12: ROI Financiero](./guias/12-ROI-Financiero.md)
  *Mapa de las Cinco Zonas: Dónde invertir y dónde evitar la destrucción de valor.*

### Bloque 4: Estrategia e Impacto Humano (Guías 13 a 16)
Decisiones de alto nivel, habilitación de habilidades y alineación de la misión.

* [Guía 13: Estrategia y Valor](./guias/13-Estrategia-Valor.md)
  *Modelos de negocio y el Foso Competitivo.*
* [Guía 14: Modelos y Mercado](./guias/14-Modelos-Mercado.md)
  *Estrategia de portafolio y el Triángulo de Adquisición.*
* [Guía 15: Ética y Confianza](./guias/15-Etica-Confianza.md)
  *Licencia Social y Sinergia S1/S2.*
* [Guía 16: Protocolos de Operación Cognitiva](./guias/16-Aprender-A-Pensar.md)
  *De Usuario Pasivo a Operador de Sistema.*

### Bloque 5: Proyección (Guía 17)
Prospección tecnológica.

* [Guía 17: Perspectivas](./guias/17-Perspectivas.md)
  *Web Agéntica   y el rol del Vigilante Estratégico.*

### Conclusión
El cierre del ciclo estratégico.

* [Cierre: De la Fundación a la Expansión](./conclusion.md)
  *Síntesis del marco GRC y el mandato de vigilancia continua.*

---

## Anexos y Herramientas (Biblioteca del Arquitecto)

### Estrategia y Gobernanza
Herramientas para el "Día 0": Definición y Permisos.

* [Anexo A: Formulación de Proyectos](./anexos/A-Formulacion-Viabilidad.md)
  *Canvas de viabilidad técnica, ética y financiera ("Screening").*
* [Anexo B: Política Institucional](./anexos/B-Politica-Institucional.md)
  *Marco regulatorio base para el uso responsable de IA.*

### Arquitectura y Diseño
Herramientas para la toma de decisiones técnicas y de compra.

* [Anexo C: Blueprints](./anexos/C-Blueprints.md)
  *Patrones de arquitectura y casos de uso reales (Soporte, Legal, Estrategia).*
* [Anexo D: Plantillas y Recursos](./anexos/D-Plantillas-Recursos.md)
  *Prompts maestros (CRF-R) y rúbricas de evaluación de calidad.*

### Control, Auditoría y Resiliencia
Metodologías para el blindaje lógico y la protección del criterio humano ante la automatización.

* [Anexo E: Soberanía del Criterio](./anexos/E-Soberania-Criterio.md)
  *Metodología para evitar la atrofia profesional y ejercicios para el Sistema 2.*
* [Anexo F: Vulnerabilidades Lógicas](./anexos/F-Vulnerabilidades.md)
  *Catálogo de falacias argumentativas, fallas sintéticas y vectores de manipulación semántica.*

### Integración y Operación
Marcos operativos para conectar la inteligencia con la acción y garantizar el blindaje técnico del sistema en producción.

* [Anexo G: Orquestación y Automatización](./anexos/G-Automatizaciones.md)
  *Matriz de selección entre SaaS, RPA e Ingeniería Soberana para agentes.*
* [Anexo H: Seguridad Operativa (LOSA)](./anexos/H-Seguridad-Operativa.md)
  *Definición de peajes y controles técnicos para la capa de razonamiento.*

### Estándares y Cumplimiento
Marcos internacionales para certificación y resiliencia legal.

* [Anexo I: Gobernanza Global](./anexos/I-Gobernanza-Global.md)
  *Mapeo de controles ISO/IEC 42001 y NIST AI RMF para auditoría y certificación.*
* [Anexo J: Marco Regulatorio EU](./anexos/J-Marco-Regulatorio-EU.md)
  *Guía de clasificación de riesgos y obligaciones legales (Efecto Bruselas).*

---

## Referencias y Fundamentos
Base de conocimiento para alinear equipos y profundizar el criterio.

* [Glosario](./referencias/Glosario.md)
  *Definiciones unificadas para evitar la ambigüedad conceptual.*
* [Bibliografía](./referencias/Bibliografia.md)
  *Papers fundacionales y reportes de industria (2017-2025).*

---

## Changelog
* **v1.6 (Enero 2026):** Refinamiento doctrinal y endurecimiento operativo. Se introducen "Dictámenes del Arquitecto" con reglas de veto, se ajusta el tono editorial y se formaliza la filosofía política del control humano.
* **v1.5 (Diciembre 2025):** Consolidación de la fase operativa y resiliencia. Finaliza la redacción de los Anexos E, F, G y H, reestructurando el marco de cumplimiento (antiguos E y F, ahora I y J) como un sello de certificación final.
* Ver [Historial Completo](./changelog.md).

## Sugerencias y Mejoras
Este es un documento vivo. Si encuentras una errata o tienes una sugerencia de mejora, puedes reportarla directamente en el [Repositorio de GitHub](https://github.com/jccarvajal/Arquitectura-IA).

## Licencia
El contenido se distribuye bajo licencia **CC BY-NC-ND 4.0**.
Se autoriza su uso educativo y de referencia profesional. No se permite la modificación ni el uso comercial sin autorización expresa del autor.