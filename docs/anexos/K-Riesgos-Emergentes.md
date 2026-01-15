# Anexo K: Radar de Riesgos Emergentes
## La Cara Oculta de la Escala Cognitiva

!!! abstract "Propósito del Anexo"
    Este documento no describe tendencias tecnológicas ni amenazas de ciberseguridad convencionales. Describe **fallas estructurales latentes** que emergen cuando los sistemas de IA dejan de ser experimentales y pasan a operar como infraestructura crítica.
    
    El mandato del Arquitecto es mantener estos riesgos visibles, precisamente porque son **silenciosos, acumulativos y de alto impacto estratégico**.

---

### 1. Conservadurismo Cognitivo Sistémico (La Trampa del Promedio)

!!! warning "El Riesgo de la Regresión a la Media"
    Los LLMs, operando a escala y sin fricción exploratoria, tienden a reforzar patrones existentes, estabilizar consensos y penalizar la desviación.

**La Mecánica del Fallo**

Aclaración de Alcance: No debe confundirse con "conservadurismo político". La IA no tiene ideología; tiene inercia estadística. Mientras la política debate visiones del mundo, la estadística de un modelo simplemente penaliza la desviación (lo atípico).

**El Impacto en la Organización**

Si tu equipo confía ciegamente en la IA para la estrategia o la innovación, la organización sufrirá una **normalización de la mediocridad**:

* Confundirá consenso con verdad.
* Confundirá estabilidad con validez.
* Invisibilizará las señales débiles o emergentes que la estadística descarta como "ruido".

> **Mitigación:** Introducir intencionalmente "Temperatura" en procesos creativos o utilizar *Red Teaming* humano para desafiar el consenso de la máquina.

---

### 2. Ceguera por Baja Frecuencia (*Low-Frequency Blindness*)

!!! danger "La Paradoja de la Estabilidad"
    Los sistemas de IA funcionan excepcionalmente bien en el 99% de los casos normales, creando una falsa sensación de seguridad que se rompe catastróficamente ante el evento del 1% (Cisne Negro).

**La Mecánica del Fallo**

Los eventos raros, por definición, tienen pocos datos de entrenamiento. La IA no tiene "sentido común" para extrapolar en situaciones inéditas; solo tiene analogías probabilísticas que fallan cuando cambia el contexto.

**El Impacto**

* **Atrofia de Simulacros:** Como el sistema "nunca falla", la organización deja de ensayar protocolos de crisis manuales.
* **Improvisación:** Cuando ocurre lo inevitable (el ataque inédito, el colapso de mercado), el humano confía demasiado en una IA que está alucinando soluciones para un problema que no comprende.

---

### 3. Degradación del Criterio Humano (Delegación Cognitiva)

!!! failure "El Riesgo del 'Sello de Goma'"
    El mayor riesgo no es que la IA se equivoque, sino que el humano pierda la capacidad de detectar el error.
    *(Ver también: [Anexo E: Soberanía del Criterio](./E-Soberania-Criterio.md))*

**La Mecánica del Fallo**

Es un problema de **eficiencia vs. resiliencia**. El cerebro humano tiende a ahorrar energía. Si la IA acierta 50 veces seguidas, el operador humano deja de auditar (pasa de "evaluar" a "validar por defecto").

**El Impacto**

* **Normalización de Alucinaciones:** Los errores sutiles se integran en la base de conocimiento corporativa.
* **Dilución de Responsabilidad:** Cuando el error explota, nadie se siente dueño de la decisión porque "el sistema dijo que estaba bien".

---

### 4. Conflictos de Lealtad y Persuasión Adversaria

!!! strategic "Lealtad ≠ Ética"
    Un modelo es leal a su instrucción (*prompt*), no a la ley, la ética ni el interés estratégico de tu empresa.
    *(Ver también: [Guía 15: Lealtad Agéntica](../guias/15-Etica-Confianza.md))*

**La Mecánica del Fallo**

En la "Web Agéntica", tu Agente de Compras interactuará con Agentes de Ventas de terceros. Estos últimos estarán optimizados para **persuadir** a tu agente (inyección de prompts lógica, manipulación semántica) para que acepte términos desfavorables.

**El Impacto**

* Optimización local (cerrar el trato rápido) contra el interés global (ahorrar dinero).
* Fuga de información estratégica ante agentes "encantadores" diseñados para ingeniería social automatizada.

---

### 5. Envenenamiento Cognitivo en Aprendizaje Continuo

!!! shield "La Vulnerabilidad del RAG"
    Aprender rápido no es lo mismo que aprender bien. Una memoria sin curaduría es el vector de ataque más simple.

**La Mecánica del Fallo**

Si tu sistema utiliza RAG (Recuperación Aumentada) sobre fuentes externas (internet, correos entrantes) sin esterilización, un atacante puede "plantar" documentos diseñados para alterar la visión del mundo del modelo (*Indirect Prompt Injection*).

**El Impacto**

La IA comienza a tomar decisiones sesgadas no por un error de código, sino porque su "realidad" (los datos que recupera) ha sido comprometida.

---

### 6. Fetichización de la Herramienta (Tecno-Solucionismo)

!!! info "Riesgo Cultural"
    Cuando la tecnología se vuelve fetiche, sus límites dejan de discutirse.

**Síntomas de Alerta**

* **Sobreconfianza en Demos:** Tomar decisiones de compra basadas en videos de marketing y no en pruebas de estrés.
* **Desprecio por Fallos "Raros":** "Eso solo pasó una vez" se convierte en la excusa para ignorar vulnerabilidades sistémicas.
* **Desplazamiento del Debate:** Se discute qué modelo es más "inteligente" en lugar de qué proceso es más **necesario**.

---

### Nota Final: El Mandato del Vigilante

La IA no es el problema; es una herramienta de apalancamiento extraordinaria. El problema es usarla sin entender su física.

El rol del **Vigilante Estratégico** no es oponerse a la adopción de la IA, sino **estresar el sistema** antes de que la realidad lo haga, asegurando que la eficiencia nunca se compre al precio de la soberanía.
