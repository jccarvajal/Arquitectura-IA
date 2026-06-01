# Anexo K: Doctrina de IA Agéntica (AEPD 2026)

## Integración Regulatoria y Arquitectura de Control

### 1. Contexto: El Giro Doctrinal de 2026

En febrero de 2026, la **Agencia Española de Protección de Datos (AEPD)** publicó la guía titulada **"Inteligencia Artificial Agéntica"**. El documento marca un **cambio de enfoque regulatorio**: deja de analizar la IA como generador de contenido (riesgo de lo que el modelo *dice* o *inventa*) para analizarla como actor autónomo (riesgo de lo que el modelo *hace* de forma autónoma).

El documento reconoce que un agente no es un chatbot; es un sistema con capacidad de **percibir, planificar, recordar y actuar** sobre el entorno. Por tanto, el problema deja de ser semántico y se vuelve operativo. Este anexo integra dicha guía no como una lista de obligaciones legales, sino como doctrina de ingeniería para diseñar arquitecturas robustas.

### 2. La "Regla del 2": El Triángulo de Riesgo

La contribución más crítica de la guía para la arquitectura de sistemas es la formalización de la **Regla del 2**.

Para entenderla, hay que visualizar un triángulo de riesgo compuesto por tres vértices concurrentes:

1.  **Input Incontrolado:** El agente procesa información externa no confiable (correos, webs, inputs de usuarios).
2.  **Datos Sensibles:** El agente tiene acceso a información interna confidencial o datos personales.
3.  **Acción Automática:** El agente tiene capacidad de ejecutar efectos reales (borrar archivos, enviar dinero, firmar documentos).

**Principio de Bloqueo:**
Jamás pueden concurrir los tres factores simultáneamente.

Si se unen, el riesgo se vuelve inaceptable por diseño.

Para cumplir la regla, la arquitectura debe "romper" el triángulo eliminando al menos uno de los vértices:

* Si el agente necesita leer datos sensibles y ejecutar acciones (vértices 2 y 3), **debe estar aislado de inputs incontrolados** (romper vértice 1).
* Si el agente procesa inputs externos y ejecuta acciones (vértices 1 y 3), **no puede tener acceso a datos sensibles** (romper vértice 2).

Desde la gobernanza, esto es un veto de diseño. Si la arquitectura permite que el triángulo se cierre, ninguna supervisión humana posterior podrá compensar la vulnerabilidad de origen.

### 3. Autonomía y Reversibilidad

La autonomía es graduada, no absoluta. Cada incremento en la capacidad del agente desplaza el momento de la decisión humana. En los sistemas agénticos, a diferencia del software tradicional, **la ejecución puede preceder a la revisión humana**.

Esto introduce una obligación técnica ineludible: la **Reversibilidad**.

A mayor autonomía, mayor debe ser la capacidad técnica de deshacer (*rollback*). La regla es simple: si una acción —como eliminar un registro crítico o realizar una transferencia irrevocable— no puede revertirse técnica o jurídicamente, esa acción no puede delegarse a un agente autónomo. La autonomía sin reversibilidad es, por definición, ingobernable.

### 4. Nuevas Vulnerabilidades Estructurales

**4.1. Shadow Leaks (Fugas Inferenciales)**
Un *shadow leak* no es una brecha de seguridad tradicional donde alguien roba una base de datos. Es una fuga por inferencia legítima. El agente no expone el dato bruto, sino que revela información sensible a través de sus metadatos, sus tiempos de respuesta o los patrones de sus decisiones. La gobernanza debe asumir que todo *output* agéntico contiene más información implícita de la que muestra en superficie.

**4.2. Errores Compuestos**
En cadenas de razonamiento largas (*pipelines*), un pequeño error inicial no se mantiene constante, sino que **se amplifica progresivamente**. La precisión del sistema decae con cada paso que da el agente. Por ello, supervisar solo el resultado final es insuficiente; la arquitectura exige establecer puntos de validación obligatorios entre las etapas intermedias del proceso.

### 5. Infraestructura de Contención

La supervisión humana, por sí sola, es insuficiente frente a la velocidad operativa de los agentes. Se requiere contención automatizada por diseño:

* **Cortacircuitos (Circuit Breakers):** Son mecanismos de código obligatorios que interrumpen "físicamente" la ejecución del agente si detectan bucles de razonamiento, consumo anómalo de recursos o desviación de objetivos.
* **Sandboxing:** La ejecución de herramientas debe ocurrir siempre en entornos aislados y efímeros. Un agente nunca puede operar con **acceso directo e irrestricto a la red corporativa**.

### 6. BYOAgentic: Automatización en la Sombra

La facilidad actual para orquestar agentes introduce el fenómeno **BYOAgentic** (*Build Your Own Agent*). Empleados no cualificados pueden hoy desplegar flujos de automatización complejos fuera de la arquitectura formal de la empresa.

La gobernanza no puede limitarse a aprobar los sistemas oficiales; debe contar con capacidad técnica para detectar esta automatización espontánea. Si la organización no institucionaliza y ofrece canales seguros para la automatización, esta se volverá informal, invisible y sistémicamente peligrosa.

### 7. Conclusión

La llegada de la IA agéntica no elimina la responsabilidad humana; al contrario, la intensifica y la hace más exigente.

A medida que delegamos autonomía, memoria y capacidad de acción en el software, la necesidad de una estructura de control se vuelve más crítica. El agente puede operar la tarea, pero el humano sigue respondiendo por el resultado. La gobernanza, en última instancia, es la arquitectura que asegura que esa respuesta humana siga siendo posible y sostenible en el tiempo.