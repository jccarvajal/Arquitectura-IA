# Historial de Versiones

Este documento registra todas las modificaciones estructurales, técnicas y conceptuales realizadas en el libro **"Arquitectura de Inteligencia Artificial: Guías para Decidir, Diseñar y Gobernar"**.

---

# Versión 1.4 (Diciembre 2025) - "Hardened Edition"

**Motivo:** Endurecimiento industrial del marco GRC. Esta versión transforma la arquitectura de "teóricamente correcta" a "financiera y operacionalmente viable", aplicando parches críticos de seguridad, rentabilidad y cultura. Se reestructura la jerarquía de contenidos separando las Herramientas (Anexos) de las Referencias Teóricas.

### 🛡️ Seguridad y Gobernanza
* **Guía 02 (Prompts):** Se redefinió el prompt como instrumento de *Alineación Probabilística*, eliminando la falacia de seguridad dura.
* **Guía 04 (Datos):** Nuevo protocolo de **"Esterilización de Documentos"** para mitigar ataques de *Inyección Indirecta* en RAG.
* **Guía 05 (Agentes):** Implementación del **"Principio de Simetría de Acción"**. Obligatoriedad de funciones de reversión (*Undo*) y *Kill-Switch* para herramientas de escritura.
* **Anexo C (Blueprints):** Alerta crítica sobre gestión de credenciales y prohibición de *hardcoded secrets*.

### 💰 Finanzas y Estrategia
* **Guía 13 (Estrategia):** **"Regla de Autofinanciamiento"**. La innovación (Transformación) solo puede financiarse con los ahorros de la eficiencia (Soporte).
* **Guía 11 (Industrialización):** **"Política de Purga de Logs"**. Retención máxima de 30 días para trazas de razonamiento (CoT) para control de costos.
* **Anexo A (Viabilidad):** **"Veto Automático del 50%"**. Rechazo inmediato de proyectos cuyo costo unitario IA supere la mitad del costo humano.
* **Glosario:** Redefinición financiera de **"Aumento"** (más output, mismo headcount) vs. **"Abdicación"**.

### 🏗️ Ingeniería y Operaciones
* **Guía 06 (Sistemas Cognitivos):** Restricción de latencia para *Tree of Thoughts* (ToT). Prohibido en tiempo real; exclusivo para procesos *Batch*.
* **Guía 14 (Modelos):** Optimización del **Agente Enrutador** mediante modelos ligeros (Flash/Haiku) para reducir latencia inicial.
* **Guía 10 (Calidad):** Estrategia de **"Cosecha Automática"** (Harvesting). El Golden Set se actualiza capturando *Edge Cases*, feedback negativo y baja confianza.

### 🧠 Cultura y Talento
* **Guía 15 (Ética):** Protocolos de **"Simulacro de Desconexión"** para combatir la atrofia cognitiva.
* **Guía 16 (Operación):** **"Teoría del Seguro"**. Redefinición del salario humano como una *Prima de Riesgo* por la responsabilidad legal, no por la producción.
* **Carrera Técnica:** Definición de roles de transición (Validador -> Entrenador -> Diseñador de Flujos).

### 📚 Cambios Estructurales
* **Jerarquía de Referencias:** El Glosario y la Bibliografía pierden la etiqueta de "Anexo" y se mueven a su propia categoría (`/referencias`) para distinguirlos de las herramientas operativas.

---

## Versión 1.3 (Diciembre 2025)

**Motivo:** Consolidación de la tesis de gobernanza como **"Ingeniería de Control"**. Esta versión integra la estrategia de **Soberanía y Geopolítica**, la visión de **Agencia Humana** (Innerarity) y profundiza en los riesgos de politización técnica.

### Actualizaciones Estratégicas y Filosóficas
* **Tesis Central (Guía 15 y Conclusión):** Se estableció el axioma de la "Agencia Humana" integrando la **"Advertencia de los Fundadores"** (Wiener/Lanier).
* **Prólogo:** Nueva estructura basada en las cuatro metáforas de futuros (Utopía, Distopía, Caos, Estructura).
* **Geopolítica:** Inclusión de la **Matriz de Decisión** (SaaS vs. Open Weights).

### Mejoras Técnicas
* **Infraestructura:** Migración completa a **MkDocs** e implementación de diagramas **Mermaid.js**.
* **Anexo A:** Adición del bloque de **Dictamen Final (Triage)**.
* **Anexo D:** Migración de prompts a bloques de código copiables.

---

## Versión 1.2 (Noviembre 2025)

**Motivo:** Estandarización de conceptos de "Agencia" y refinamiento de la "Ingeniería de Agentes".

### Cambios Técnicos
* **Guía 05 (Agentes):** Formalización del ciclo **ReAct** (Razonar + Actuar).
* **Guía 14 (Modelos):** Introducción de la **Estrategia de Portafolio** y métricas de *Token-Economics*.

---

## Versión 1.1 (Noviembre 2025)

**Motivo:** Transición a un marco de pensamiento estratégico completo (GRC).

### Cambios Estratégicos
* **Tesis Central:** Enfoque explícito en **GRC (Gobernanza, Riesgo y Cumplimiento)**.
* **Ingeniería de Contexto:** Elevación del Prompting a gestión de memoria.
* **Límites:** Definición del **Costo Cuadrático** y la **Amnesia Estática**.

---

## Versión 1.0 (Base Inicial)

**Motivo:** Publicación inicial del borrador de contenidos.

* **Lanzamiento:** Publicación del libro con la estructura base de 17 guías y 6 anexos.