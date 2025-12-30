# Anexo I: Orquestación y Automatización

## 1. El Motor de Ejecución: Filosofía de Orquestación

Una vez definido el modelo de lenguaje (el "cerebro"), la arquitectura requiere un **sistema nervioso** que mueva los datos y ejecute acciones. La elección del orquestador no es un detalle administrativo; define la **Soberanía**, la **Escalabilidad** y la capacidad de la organización para conectar sistemas modernos con su infraestructura heredada (*Legacy*).

---

## 2. Matriz Estratégica de Selección

Para el Arquitecto de IA, existen tres filosofías para desplegar y mover agentes en producción:

| Filosofía | Ejemplo Típico | Ventaja Estratégica | Riesgo GRC Clave |
| :--- | :--- | :--- | :--- |
| **SaaS / No-Code** | Zapier, Make | **Velocidad:** Ideal para prototipos rápidos y validación de MVPs. | **Caja Negra:** Los datos viajan por servidores externos fuera del control institucional. |
| **Corporativa / RPA** | UiPath, Power Automate | **Compatibilidad:** El puente necesario para interactuar con sistemas antiguos (*Legacy*) sin API. | **Vendor Lock-in:** Alta dependencia del proveedor y costos crecientes de licenciamiento. |
| **Ingeniería Soberana** | n8n (Self-hosted), Python | **Control Total:** Los datos y la lógica de ejecución residen en infraestructura propia. | **Capacidad:** Requiere un equipo técnico interno para su mantenimiento y seguridad. |

---

## 3. Criterios de Decisión para el Arquitecto

La selección del "motor de ejecución" debe alinearse con la naturaleza del proceso y el apetito de riesgo definido en la gobernanza:

* **Integración Nativa (API First):** Si el ecosistema tecnológico es moderno, se debe priorizar la **Ingeniería Soberana** para garantizar la seguridad de los datos sensibles y optimizar la economía unitaria.
* **Infraestructura Legacy (UI-Driven):** En entornos que dependen de sistemas de escritorio o "pantallas verdes" (SAP Legacy, Mainframes), la automatización robótica (**RPA**) es el estándar obligatorio para simular la interacción humana.
* **Experimentación Segura:** Se recomienda el uso de aplicaciones de escritorio de orquestadores soberanos para desarrollar flujos complejos en un entorno local (Localhost), eliminando riesgos de fuga de datos durante la fase de diseño.

---

## 4. Soberanía y Jurisdicción Legal (GRC)

La decisión de orquestar en la nube o en servidores propios es un imperativo de **Residencia de Datos** y cumplimiento legal. Bajo marcos internacionales de alta exigencia, la ubicación física del procesamiento define la validez legal del sistema completo.

!!! abstract "Principio de Soberanía en la Automatización"
    La arquitectura de automatización debe garantizar que la **frontera de datos** coincida con la **frontera legal** de la organización, blindando la estrategia ante cambios regulatorios o geopolíticos externos.

---

## 5. Checklist de Gestión Operativa (Puntos de Control)

Antes de autorizar el paso de una automatización a producción, el Arquitecto debe validar la existencia de estos mecanismos de control:

* **Simetría de Acción:** Capacidad técnica de revertir o compensar cualquier acción ejecutada por el agente (ej: cancelar una reserva o deshacer un cambio).
* **Visibilidad Cognitiva:** El orquestador debe permitir el registro inmutable de la **Cadena de Pensamiento (CoT)** para facilitar auditorías forenses tras un incidente.
* **Límites de Emergencia (Circuit Breakers):** Configuración de interruptores técnicos que detengan el flujo automáticamente ante la detección de bucles de costos o desviaciones lógicas.
