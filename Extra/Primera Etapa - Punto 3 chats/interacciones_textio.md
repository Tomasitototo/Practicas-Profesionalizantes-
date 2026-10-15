# Trazabilidad de Aserciones y Requerimientos de Negocio

Este documento establece el mapeo formal y la validación cruzada entre las decisiones metodológicas de desarrollo y las necesidades de infraestructura planteadas por los interesados del proyecto FitConnect.

---

## 1. Restricciones Técnicas de Infraestructura (Diego - CTO)
**Aserción Analizada:** *"instalador menor a 200MB, inicio en menos de 3 segundos y la arquitectura CDN con protocolo HLS/DASH"*
* **Validación Metodológica:** Incorporado en [Modelos de Proceso](./punto3_modelos_de_proceso.md#1-modelo-cascada) dentro de la evaluación de viabilidad estructural en el Modelo Cascada.
* **Origen del Requerimiento:** Detallado formalmente en el análisis de restricciones del documento de [Stakeholders](./stakeholders).

---

## 2. Métrica de Retención y Onboarding de Usuarios (Gabriel - PM)
**Aserción Analizada:** *"onboarding en 3 taps" / "configuración en menos de 3 taps"*
* **Validación Metodológica:** Justificado en [Modelos de Proceso](./punto3_modelos_de_proceso.md#3-modelo-incremental) como una de las ventajas operativas clave del Enfoque Incremental para captar la masa inicial de usuarios.
* **Origen del Requerimiento:** Establecido como métrica de éxito crítico en el apartado de objetivos de negocio en [Stakeholders](./stakeholders).

---

## 3. Riesgo de Deserción en la Oferta de Contenido (Ana - Head de Entrenadores)
**Aserción Analizada:** *"el 85% de los entrenadores abandonará la plataforma"*
* **Validación Metodológica:** Evaluado en [Modelos de Proceso](./punto3_modelos_de_proceso.md#3-modelo-incremental) dentro de los riesgos y desventajas de postergar entregas funcionales en el Modelo Incremental.
* **Origen del Requerimiento:** Planteado como un conflicto de prioridad operativa en el informe de [Stakeholders](./stakeholders).

---

## 4. Mitigación de Riesgos Legales y Datos Sensibles (Mara - Legal)
**Aserción Analizada:** *"fotografías de progreso premium constituyen datos sensibles sujetos a HIPAA y GDPR"*
* **Validación Metodológica:** Mapeado en [Modelos de Proceso](./punto3_modelos_de_proceso.md#6-modelo-en-espiral) como el núcleo de la gestión de riesgos cíclicos dentro del Modelo en Espiral.
* **Origen del Requerimiento:** Registrado bajo las restricciones de cumplimiento normativo de la organización en [Stakeholders](./stakeholders).

---

## 5. Continuidad de Servicio y Estrategia de Contingencia
**Aserción Analizada:** *"soportar un 99.5% de uptime"* junto con los mecanismos automáticos de fallback del servidor de backend.
* **Validación Metodológica:** Incluido en [Modelos de Proceso](./punto3_modelos_de_proceso.md#2-modelo-en-v) en la fase de verificación y pruebas dinámicas del Modelo en V.
* **Origen del Requerimiento:** Fijado como métrica técnica de alta disponibilidad de infraestructura en [Stakeholders](./stakeholders).

---

## 6. Dinámica Comercial y Deserción del Mercado Fitness
**Aserción Analizada:** *"el brutal 'churn' (deserción) del mercado fitness"*
* **Validación Metodológica:** Analizado en [Modelos de Proceso](./punto3_modelos_de_proceso.md#4-modelo-iterativo) para fundamentar los ciclos rápidos de adaptación del Modelo Iterativo.
* **Origen del Requerimiento:** Derivado de la planificación estratégica y comercial registrada en [Stakeholders](./stakeholders).

