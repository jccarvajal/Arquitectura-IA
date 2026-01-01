# Anexo G: Orquestación y Automatización de Actuadores

## 1. El Motor de Ejecución: De la Cognición a la Acción

Este anexo establece el marco de diseño para transformar una IA de "Generación de Contenido" en una IA de **"Ejecución de Procesos"**. La arquitectura de orquestación es el "sistema nervioso" que conecta la **inferencia probabilística no determinística** del modelo (Sistema 1) con la acción operativa en el mundo real, bajo el control humano explícito y estratégico (Sistema 2).

La elección del orquestador define la **Soberanía de Datos**, la **Escalabilidad** del negocio y la capacidad de la organización para integrar modelos modernos con su infraestructura heredada (*Legacy*).

---

## 2. Matriz Estratégica de Selección

Para el Arquitecto de IA, existen tres filosofías dominantes para desplegar y mover agentes en producción:

| Filosofía | Ejemplo Típico | Ventaja Estratégica | Riesgo GRC Clave |
| :--- | :--- | :--- | :--- |
| **SaaS / No-Code** | **Zapier, Make** | **Velocidad:** Ideal para prototipos rápidos y validación de MVPs. | **Caja Negra:** Los datos viajan por servidores externos de terceros. |
| **Corporativa / RPA** | **UiPath, Power Automate** | **Compatibilidad:** El puente necesario para interactuar con sistemas antiguos (*Legacy*) sin API. | **Vendor Lock-in:** Alta dependencia y costos crecientes de licenciamiento. |
| **Ingeniería Soberana** | **n8n (Self-hosted), Python** | **Control Total:** Los datos y la lógica residen en infraestructura propia. | **Capacidad:** Requiere un equipo técnico interno para mantenimiento y seguridad. |

---

## 3. Definición de la Frontera de Control

El principal desafío de la **automatización basada en modelos generativos** es la **Gestión del Actuador**, no el "razonamiento" del modelo. Para evitar la abdicación del juicio, definimos tres niveles de responsabilidad:

* **Nivel Gerencial (Captura de Valor):** Foco en eficiencia operativa, eliminación del costo del "clic humano" y disponibilidad continua.

* **Nivel Jefatura (Supervisión):** Definición explícita del grado de autonomía permitido:
    * **Interlock (HITL):** El humano autoriza *antes* de la ejecución (Human-in-the-Loop).
    * **Shadow (HOTL):** El humano audita la ejecución *después* mediante evidencia (Human-on-the-Loop).
    * **Full Auto:** Permitido únicamente para acciones de impacto nulo o técnicamente reversibles.

* **Nivel Ingeniería (Ejecución):** Implementación de **Actuadores Digitales** (APIs, Bases de Datos) protegidos por una **Capa de Desacoplamiento**. La IA nunca escribe directamente en sistemas core sin una validación determinística intermedia.

---

## 4. Ecosistema de Ejecución (Dónde se implementan)

La plataforma de orquestación se selecciona según la criticidad del proceso:

1. **Orquestadores Low-Code (Agilidad):** **n8n, Make, Zapier**. Conectores universales para SaaS. Óptimos para reducir el *Time-to-Market*.
2. **Frameworks de Agentes y Código (Control):** **LangGraph, CrewAI, Semantic Kernel**. Permiten definir flujos donde el modelo **propone** herramientas, pero el código **determina y valida** la ejecución lógica.
3. **Servicios Cloud Nativos (Escala y Seguridad):** **AWS Step Functions, Azure Logic Apps**. Proveen trazabilidad industrial, reintentos controlados y alineación con marcos de cumplimiento (SOC2, ISO 27001).
4. **RPA Tradicional (Sistemas Legado):** **UiPath, Blue Prism**. Se utilizan cuando no existen APIs y la interacción ocurre vía interfaces gráficas, bajo reglas determinísticas externas al modelo.

---

## 5. Matriz de Riesgo y Supervisión Operativa

| Categoría de Acción | Impacto en Negocio | Mecanismo de Control | Supervisión Sugerida |
| :--- | :--- | :--- | :--- |
| **Consulta** | Nulo (Solo lectura) | Caché / ACLs | Auditoría periódica |
| **Modificación** | Bajo/Medio (Escritura) | Validación estricta de esquema | Revisión post-ejecución |
| **Transacción** | Alto (Compromiso) | **Circuit Breaker** + Firma | Aprobación Humana previa |

---

## 6. Checklist de Readiness (Auditoría de Automatización)

*Antes de habilitar un Actuador en producción, el Arquitecto debe validar:*

### I. Factibilidad Técnica
* [ ] **Mínimo Privilegio (IAM):** Identidad digital del agente con permisos estrictamente acotados al proceso.
* [ ] **Entorno Sandbox:** Capacidad de prueba del actuador sin impacto en datos productivos.

### II. Seguridad y Resiliencia (Capa LOSA)
* [ ] **Validador Determinístico:** Código intermedio que valida la estructura y parámetros del JSON antes de la ejecución.
* [ ] **Simetría de Acción (Undo):** Procedimiento técnico o funcional para revertir la acción en caso de error lógico.
* [ ] **Circuit Breakers:** Límites duros de volumen y valor monetario que no pueden ser sobreescritos por el modelo.

### III. Trazabilidad y Cumplimiento (CoT-Safe)
* [ ] **No Persistencia de CoT:** Por diseño de seguridad, el sistema no almacena cadenas de pensamiento legibles para evitar fugas de lógica interna. **El CoT no constituye evidencia, explicación causal ni insumo válido para la toma de decisiones.**
* [ ] **Evidencia Post-Hoc:** Registro inmutable del *input*, el *output final* y la acción ejecutada para auditoría forense (Pilar 18).
* [ ] **Log de Correlación:** Asociación técnica entre la solicitud original, las validaciones aplicadas por el sistema y el resultado operativo final.

---

!!! success "Axioma del Arquitecto"
    **El modelo propone; el sistema dispone; el humano responde.** Si una acción no puede ser **medida, limitada y revertida**, no debe ser delegada a un sistema de IA.
