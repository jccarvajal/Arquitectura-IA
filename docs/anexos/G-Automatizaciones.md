# Anexo G: Orquestación y Automatización de Actuadores

## 1. Introducción: De la Generación a la Ejecución

Este anexo establece el marco de diseño para transformar una IA de "Generación de Contenido" en una IA de **"Ejecución de Procesos"**. Define la arquitectura necesaria para conectar el razonamiento probabilístico con la acción operativa determinística y gobernada.

---

## 2. Niveles de Implementación Estratégica

La automatización no es solo un reto de ingeniería; es un cambio en la gobernanza organizacional.

### A. Nivel Gerencial: Captura de Valor
* **Eficiencia Unitaria:** Eliminación del costo del "clic humano" en tareas repetitivas.
* **Disponibilidad 24/7:** Ejecución instantánea sin dependencia de turnos laborales.
* **Reducción de Error:** Minimización de fallas por fatiga en el procesamiento de datos.

### B. Nivel Jefatura: Frontera de Control
* **Capa de Desacoplamiento:** La IA nunca escribe directamente en los sistemas centrales. Requiere un *middleware* que valide la orden.
* **Niveles de Autonomía:**
    * **Interlock:** El humano autoriza *antes* de la acción (HITL).
    * **Shadow:** El humano supervisa *después* de la acción.
    * **Full Auto:** Solo auditoría de logs (Permitido únicamente para acciones reversibles, de impacto nulo o controladas por límites físicos inmutables).

### C. Nivel Ingeniería: Protocolos de Seguridad
* **Validación de Esquema:** El JSON generado por la IA debe pasar por un validador estricto de tipado y sanitización antes de ser ejecutado.
* **Gatekeepers (Capa LOSA – Separación Lógica de Autoridad):** Implementación de reglas de negocio duras (ej: límites de descuento) que el código puede rechazar aunque la IA lo ordene.

---

## 3. Matriz de Riesgo y Supervisión Operativa (2025)

| Categoría de Acción | Impacto | Mecanismo de Control | Supervisión Sugerida |
| :--- | :--- | :--- | :--- |
| **Consulta** | Nulo (Lectura) | Caché de tokens / ACLs | Auditoría periódica |
| **Modificación** | Medio (Escritura) | Validación de esquema JSON | Registro de logs inmutables (Post) |
| **Transacción** | Alto (Recursos) | **Circuit Breaker** + Firma | Aprobación Humana (Pre) |

---

## 4. Ecosistema de Ejecución

La elección de la plataforma depende de la criticidad y la soberanía requerida:

1.  **Orquestadores Low-Code (Agilidad):** Herramientas como n8n (Soberana) o Zapier. Ideales para conectar aplicaciones SaaS rápidamente.
2.  **Frameworks Agénticos (Control):** Bibliotecas de código (Python/Node.js) para ciclos de razonamiento complejos donde la IA decide qué herramienta usar.
3.  **Cloud Nativo (Escala):** AWS Step Functions o Azure Logic Apps para procesos industriales con cumplimiento SOC2 o ISO 27001.
4.  **RPA Tradicional (Legacy):** Para interactuar con software antiguo que carece de APIs, simulando clics humanos bajo la lógica del modelo.

---

## 5. Checklist de Readiness para Automatización
*El Arquitecto debe validar estos puntos antes de habilitar cualquier actuador en producción.*

### I. Madurez del Proceso
* [ ] **Documentación:** ¿El proceso manual actual no tiene ambigüedades?
* [ ] **Determinismo:** ¿Sabemos qué debe ocurrir en el sistema de destino ante cada orden?

### II. Factibilidad Técnica
* [ ] **Entorno Sandbox:** ¿Existe un ambiente de pruebas donde el actuador pueda fallar sin afectar datos reales?
* [ ] **Mínimo Privilegio:** ¿La automatización tiene permisos limitados (IAM) solo para lo estrictamente necesario?

### III. Seguridad y GRC
* [ ] **Circuit Breakers:** ¿Se han establecido límites físicos de volumen (transacciones/hora) y de valor (montos máximos)?.
* [ ] **Plan de Reversión (Rollback):** ¿Existe un procedimiento técnico para deshacer la acción si la IA comete un error lógico?.

---

!!! success "Conclusión del Anexo"
    La automatización no debe ser una caja negra, sino un sistema de lazo cerrado donde el actuador devuelva siempre un reporte de éxito o falla a la capa de gobernanza. **Si no puedes medirlo, controlarlo y auditarlo, no lo automatices.**
