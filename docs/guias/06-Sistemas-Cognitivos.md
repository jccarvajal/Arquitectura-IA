## Guía 06: Diseño de Sistemas Cognitivos

Subtítulo: El Plano de la Mente: De 'Trabajadores' Reactivos a 'Equipos' Cognitivos

### Introducción: La Mente detrás de la Herramienta

Darle herramientas a un agente sin enseñarle a pensar es imprudente.

En la **Guía 05**, construimos el **Cuerpo**: le dimos al agente "manos" (Herramientas) para tocar el mundo digital y "piernas" (Ciclo ReAct) para moverse. Pero un cuerpo sin mente es peligroso; es solo un script glorificado disparando acciones al azar, gastando presupuesto y cometiendo errores a velocidad de máquina.

Esta guía trata sobre el **Cerebro**.

La "Brecha de Aprendizaje" a menudo no es falta de conocimiento, sino falta de **estrategia**. El modelo sabe *qué* es una factura, pero no sabe *cómo* razonar sobre una discrepancia contable compleja sin un plan.

Aquí dejamos de diseñar la ejecución para diseñar la **Ingeniería de la Cognición**. Instalaremos patrones de razonamiento (como *Chain-of-Thought* y *Tree of Thoughts*) que actúan como el "manual de procedimientos" del cerebro sintético, transformando a un trabajador reactivo en un estratega deliberado.

---

### Parte 1: El Salto Cognitivo: Del Trabajador Reactivo al Equipo Pensante

El error más común es tratar a un LLM (un Modelo de Lenguaje Grande) como una calculadora (un sistema reactivo).

* **El Trabajador Reactivo (IA Básica):** Le das un input, genera un output. *Prompt → Respuesta*.  
    * *Ejemplo:* "Traduce este texto."  
    * *Metáfora:* Un trabajador en la línea de ensamblaje que solo aprieta un tornillo cuando la pieza pasa frente a él.  
* **El Equipo Cognitivo (Agente Diseñado):** Le das un objetivo, y el sistema genera y ejecuta un plan para alcanzarlo. ​*​Objetivo → Pensamiento → Acción → Observación → Pensamiento → ... → Resultado*.  
    * *Ejemplo:* "Reserva un vuelo para mi a Madrid la próxima semana, que sea económico y salga por la mañana."  
    * *Metáfora:* Un "Jefe de Taller" que recibe el objetivo, consulta el inventario (una herramienta), habla con el equipo de logística (otra herramienta) y luego presenta un plan de acción.

Esta guía se enfoca en diseñar al "Jefe de Taller".

---

### Parte 2: Patrones de Razonamiento: El "Manual de Procedimientos" de la IA

Para que un agente "piense", debemos darle un "Manual de Procedimientos" (un patrón de razonamiento). Estos son los patrones más cruciales que debes diseñar:

**A. Chain of Thought (CoT): La "Línea de Ensamblaje"**

* **Qué es:** El patrón más básico. Forzamos al modelo a "pensar paso a paso" antes de dar la respuesta final.  
* **Metáfora:** Una simple línea de ensamblaje. No se puede pasar al Paso 2 hasta completar el Paso 1\.  
* **Cuándo usarlo:** Para problemas lógicos, matemáticos o de razonamiento deductivo que se benefician de un proceso lineal.  
* **Ejemplo Práctico (Prompt):**  
    "Pregunta: Juan tiene 5 manzanas. Regala 2 a Ana y compra 3 más. ¿Cuántas tiene?  
    Respuesta: Pensemos paso a paso:  
    1. Juan empieza con 5 manzanas.  
    2. Regala 2 a Ana, le quedan 5−2=3 manzanas.  
    3. Compra 3 manzanas más, ahora tiene 3+3=6 manzanas. Respuesta final: 6\.
> **Nota Técnica:** El CoT no implica razonamiento consciente; es un patrón de estructuración verbal que reduce errores al forzar una secuencia explícita.

**B. ReAct (Reason \+ Act): El "Detective con Herramientas"**

* **Qué es:** Como establecimos en la **Guía 05**, el ciclo ReAct es el pilar de la agencia moderna. Se basa en un bucle donde el modelo genera un **Pensamiento** (Reason) sobre su objetivo, ejecuta una **Acción** (Act) mediante una herramienta externa y luego **Observa** el resultado para ajustar su siguiente paso. Es el mecanismo que transforma una IA pasiva en un trabajador capaz de interactuar con el mundo real.
* **Metáfora:** Un detective que, en lugar de adivinar, usa activamente sus herramientas (lupa, teléfono, base de datos de huellas).
* **Cuándo usarlo:** Casi siempre. Es la arquitectura fundamental para cualquier agente que deba interactuar con el mundo exterior.

* **Ejemplo Práctico (Ciclo):**
    * *Input:*
        `Recomiéndame un restaurante italiano cerca de la oficina.`
    * *Ciclo 1:*
        * *Reason (Pensamiento):* "Necesito la ubicación de la oficina y una lista de restaurantes. Usaré la herramienta `get_office_location`."
        * *Act (Acción):*
            ```yaml
            acción: get_office_location
            argumentos: {}
            ```
    * *Observe (Observación):* "Ubicación: Av. Principal 123."
    * *Ciclo 2:*
        * *Reason (Pensamiento):* "Tengo la ubicación. Ahora necesito buscar restaurantes. Usaré `search_google_maps`."
        * *Act (Acción):*
            ```yaml
            acción: search_google_maps
            argumentos:
              query: "restaurante italiano"
              ubicacion: "Av. Principal 123"
            ```
        * *Observe (Observación):* "Resultados: \[Restaurante A, Restaurante B, Restaurante C\]."
    * *Ciclo 3:*
        * *Reason (Pensamiento):* "Tengo la lista. Ahora puedo formular la respuesta."
        * *Act (Acción):* (Genera la respuesta final al usuario).

**C. Tree of Thoughts (ToT): El "Comité de Estrategia"**

* **Qué es:** Un patrón avanzado donde el agente explora múltiples caminos de razonamiento en paralelo (como ramas de un árbol). Evalúa qué camino es más prometedor y descarta los callejones sin salida.  
* **Metáfora:** Un "Comité de Estrategia" o un departamento de I+D que hace una lluvia de ideas de 5 posibles slogans, evalúa los pros y contras de cada uno, y presenta solo los 2 mejores.  
* **Cuándo usarlo:** Para problemas complejos y abiertos sin una única respuesta correcta (ej. estrategia creativa, planificación compleja, redacción de un documento legal).

**D. Reflexión: El "Auditor de Calidad"**

* **Qué es:** El agente genera un primer borrador (ej. un bloque de código o un email). Luego, invoca a un "agente crítico" (o a sí mismo con un prompt de "auditor") para que revise, critique y corrija su propio trabajo. Es una forma de cerrar la "Brecha de Aprendizaje" permitiendo al agente aprender de sus propios errores.  
* **Metáfora:** El "Auditor de Calidad" al final de la línea de ensamblaje que revisa el producto y, si encuentra un defecto, lo devuelve para su corrección.  
* **Cuándo usarlo:** Para tareas que requieren alta precisión y fiabilidad (ej. generación de código, redacción de contratos, análisis financieros).

!!! tip "Requisito de Auditoría: La Legibilidad del Pensamiento"
    El patrón *Chain-of-Thought* (CoT) no es solo para que la IA razone mejor; es para que el humano pueda auditarla.
    
    **La Regla de Transparencia:**
    Diseña tu prompt de sistema para que el agente genere su razonamiento en un bloque separado (ej. `<pensamiento>...</pensamiento>`) **en contextos de desarrollo, auditoría o depuración**, antes de ejecutar herramientas o emitir la respuesta final.

    * Si la respuesta es mala pero el pensamiento es lógico, el problema es falta de contexto (Guía 03).
    * Si el pensamiento es ilógico, el problema es el modelo o el prompt (Guía 02).
    
    Sin pensamiento visible, corregir a un agente es adivinar.

    En producción, este razonamiento debe capturarse como **telemetría interna** (logs, trazas), no exponerse al usuario.

!!! warning "Restricción de Ingeniería: Costo y Latencia (La Regla del Batch)"
    Los patrones avanzados como *Tree of Thoughts* (ToT) o *Reflexion* no solo triplican el consumo de tokens (Dinero), sino que aumentan la latencia exponencialmente (Tiempo).
    
    * **La Prohibición de UX:** Jamás uses ToT en interfaces de chat en tiempo real. El usuario no esperará 45 segundos por una respuesta.
    * **El Caso de Uso:** Reserva estos patrones exclusivamente para procesos **Offline** o **Batch Jobs** (ej. análisis nocturno de contratos) donde la profundidad del razonamiento vale más que la velocidad de respuesta.
    * **Regla de Escalamiento:** Empieza siempre con *Direct Shot*. Solo escala a *Chain of Thought* si fallas, y a *Agentes* si hay incertidumbre. La "inteligencia excesiva" es un error de arquitectura.

---

### Parte 3: Metacognición: El "Jefe de Taller" (Agente Enrutador)

Ya no pensamos en un solo "trabajador". El sistema cognitivo más robusto es un equipo modular. 

No construyas un "super-agente" monolítico. Construye una "cuadrilla de especialistas" dirigida por un "Jefe de Taller".

* **El "Jefe de Taller" (Agente Enrutador):** Este es un agente de **Metacognición** (piensa sobre el pensamiento). Su único trabajo es recibir la solicitud del usuario y decidir qué "especialista" es el mejor para la tarea. Es el que optimiza el portafolio de modelos.  
* **Los "Especialistas" (Agentes de Tarea):**  
    * El "Archivero" (Agente RAG, el sistema que recupera conocimiento de la "biblioteca" interna).  
    * El "Analista de Datos": Experto en procesar números y tablas.  
    * El "Redactor Creativo": Experto en marketing y redacción.  
    * El "Motor Barato": Un LLM rápido y económico para tareas simples como resumir emails.

Esta arquitectura modular es la implementación técnica de tu estrategia de portafolio.

---

### Parte 4: El "Plano Cognitivo": El Entregable de Diseño

Antes de escribir una sola línea de código para tu prototipo, debes entregar este "Plano Cognitivo". Este plano es la "Ficha de Diseño de Agente" (que encontrarás en los Anexos) y debe responder obligatoriamente:

1. **El Objetivo:** ¿Qué problema resuelve este agente?  
2. **El Patrón de Razonamiento:** ¿Usará ReAct (para herramientas), ToT (para estrategia), o una combinación?  
3. **Las Herramientas:** ¿A qué APIs, bases de datos (RAG) o funciones tendrá acceso?  
4. **La Arquitectura de Equipo:** ¿Es un solo agente o un sistema modular con un "Jefe de Taller" (Enrutador)?  
5. **El Criterio de Éxito:** ¿Cómo sabe el agente (y nosotros) que ha terminado y lo ha hecho bien?

---

### Parte 5: Cognición y Control: La Conexión con la Gobernanza

Un sistema que "piensa" es poderoso, pero también puede fallar de formas complejas. Un agente ReAct puede entrar en un bucle infinito, costar una fortuna en llamadas de API, o "alucinar" un plan desastroso.  
Por lo tanto, un diseño cognitivo debe incluir "guardarrailes" (barandillas). El diseño de la mente está inseparablemente ligado a la **Gobernanza**. Tu plano cognitivo debe incluir:

* **Interruptores (Circuit Breakers):** Un límite máximo de pasos o de costo.  
* **Validación Humana:** Puntos de control donde el agente debe detenerse y pedir aprobación a un humano antes de ejecutar una acción crítica (ej: "He encontrado 3 vuelos. ¿Apruebas la compra de este?").  
* **Monitoreo (Observabilidad):** La capacidad de ver la "cadena de pensamiento" (CoT) del agente para poder auditarla.

---

### Conclusión: Del Contrato al Plan Cognitivo Detallado

Hemos pasado de "contratar" al trabajador a diseñar su "plan de trabajo" detallado. Ahora tenemos el "plano de la mente". Con este plano cognitivo en mano, estamos listos para ir al taller y construir la primera versión funcional de la maquinaria en la **Guía 08: Prototipado y Experimentación**.
