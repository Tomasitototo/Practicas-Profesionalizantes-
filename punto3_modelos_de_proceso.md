# Punto 3 – Modelos de Proceso


# Análisis Comparativo de los Modelos de Proceso Aplicados a FitConnect

A continuación, se evalúan los distintos modelos de proceso de ingeniería de software, detallando sus ventajas y desventajas específicas frente a las necesidades técnicas, de negocio y legales del proyecto FitConnect.

## 1. Modelo Cascada
* **Ventaja aplicada a FitConnect:** Permite definir de manera sumamente estricta y documentada desde el primer día los requisitos de rendimiento innegociables exigidos por Diego (CTO), tales como un instalador menor a 200MB, inicio en menos de 3 segundos y la arquitectura CDN con protocolo HLS/DASH.
* **Desventaja aplicada a FitConnect:** Es completamente inviable debido al conflicto de prioridades en el MVP. Gabriel (Product Manager) quiere postergar el marketplace para la fase 2 y priorizar al usuario final, mientras que Ana exige el panel de entrenadores desde el Sprint 1 y Mara (Legal) exige auditorías inmediatas. Un cambio en etapas avanzadas bajo este modelo paralizaría el proyecto.

## 2. Modelo en V
* **Ventaja aplicada a FitConnect:** Vincula directamente cada fase de diseño con su respectivo plan de pruebas. Esto facilita la verificación temprana del backend para soportar un 99.5% de uptime y permite testear el comportamiento del fallback automático (frame estático y descripción) cuando la latencia supera los 800 ms o el CDN falla.
* **Desventaja aplicada a FitConnect:** Carece de la flexibilidad necesaria para resolver las discrepancias operativas del equipo. Si en fases avanzadas de la verificación se descubre que el flujo de comisiones del 20-30% exigido por Ana o los contratos de Mara espantan a los usuarios que Gabriel intenta registrar en menos de 3 taps, la reingeniería y el retorno a fases previas serían extremadamente costosos.

## 3. Modelo Incremental
* **Ventaja aplicada a FitConnect:** Permite priorizar la visión de Gabriel para captar los 15k usuarios del MVP, lanzando primero un núcleo básico (configuración en 3 taps y rutinas de 4, 8 o 16 semanas para que usuarios como Enzo inicien rápido), dejando las funciones más complejas de monetización y reportes para incrementos futuros.
* **Desventaja aplicada a FitConnect:** Representa un peligro comercial y legal crítico. Si se lanza un incremento inicial que carezca de las plantillas de entrenamiento que pide Ana, la app tendrá programas genéricos y el 85% de los entrenadores abandonará la plataforma. Además, postergar las retenciones automatizadas e integraciones legales viola las advertencias de Mara.

## 4. Modelo Iterativo
* **Ventaja aplicada a FitConnect:** Ayuda a combatir el brutal "churn" (deserción) del mercado fitness que tanto preocupa a Gabriel. Permite lanzar versiones funcionales de la biblioteca de ejercicios y ajustar el sistema de tracking básico ciclo a ciclo basándose en el progreso y enganche real de los usuarios.
* **Desventaja aplicada a FitConnect:** Existe el riesgo de que el equipo se quede atrapado en ciclos infinitos de mejoras cosméticas en la interfaz de usuario (UX) o la biblioteca, descuidando la implementación de la infraestructura base del backend, como la memoria caché local LRU de 50MB o las auditorías de bases de datos sensibles.

## 5. Modelo de Prototipos
* **Ventaja aplicada a FitConnect:** Es ideal para diseñar maquetas rápidas de la herramienta drag-and-drop para rutinas que pide Ana o las pantallas de pre-actividad de Términos y Condiciones que exige Mara. Permite validar la aceptación de los entrenadores y usuarios antes de escribir una sola línea de código en el backend.
* **Desventaja aplicada a FitConnect:** Los stakeholders o los entrenadores podrían confundir un prototipo visual interactivo con la aplicación final lista, subestimando la altísima complejidad técnica del backend que Diego debe configurar para procesar el bitrate adaptativo de video y el cifrado de datos biométricos.

## 6. Modelo en Espiral
* **Ventaja aplicada a FitConnect:** Es excelente para mapear y mitigar de raíz los riesgos críticos del proyecto: el riesgo técnico de Diego (evitar que el APK suba de 500MB si se embeben videos en local) y el riesgo regulatorio/patrimonial de Mara (exposición a demandas si no se cumple con HIPAA y GDPR al almacenar fotos de progreso premium).
* **Desventaja aplicada a FitConnect:** Requiere una cantidad masiva de tiempo, planificación y especialistas para evaluar los riesgos en cada vuelta de la espiral. Esto retrasaría drásticamente el lanzamiento rápido del MVP y el despliegue continuo, chocando con la necesidad comercial de Gabriel de captar usuarios con urgencia.

## 7. Modelo Ágil (Scrum)
* **Ventaja aplicada a FitConnect:** Es el modelo óptimo para equilibrar los requerimientos en conflicto. A través de Sprints cortos (de 2 a 4 semanas), el equipo puede estabilizar el core del usuario final (Gabriel) al mismo tiempo que incluye un panel de plantillas básicas para entrenadores (Ana) y las pantallas de consentimiento legal obligatorio (Mara), todo bajo el control técnico de Diego.
* **Desventaja aplicada a FitConnect:** Requiere que todos los líderes (Gabriel, Ana, Diego y Mara) actúen de forma coordinada y participativa. Si el Product Owner no sabe mediar con firmeza entre las presiones de captar usuarios rápido y los bloqueos obligatorios de Legal, el sprint fracasará y el equipo caerá en parálisis.

---

# Respuestas a las Preguntas del Proyecto

### ¿Qué modelo de proceso recomendarían para FitConnect y por qué?

**Recomendación:** Se recomienda utilizar el **Modelo Ágil (Scrum)**, complementado con un enfoque incremental para la liberación de las primeras versiones de la plataforma.

**Justificación:** FitConnect no es una aplicación lineal; es un marketplace donde coexisten e interactúan dos tipos de usuarios clave (clientes finales como Enzo y entrenadores personales) cuyas necesidades chocan directamente en el MVP. Gabriel (PM) exige un flujo de 3 taps para retener usuarios ante el brutal churn del mercado, mientras que Ana (Head de Entrenadores) advierte que sin un panel drag-and-drop para crear planes personalizados, el 85% de los entrenadores abandonará la app. 

Scrum permite solucionar este conflicto sentando a ambos líderes en una mesa de *Sprint Planning* para desglosar sus requerimientos en Historias de Usuario mínimas viables. Así, en el Sprint 1 se puede desarrollar la configuración rápida de usuario alimentada por un sistema básico de plantillas para entrenadores. De este modo, se entrega valor inmediato a ambas partes sin comprometer el proyecto a un diseño rígido que no pueda adaptarse al feedback del mercado.

---

### ¿Qué factores del proyecto influyeron en su decisión?

Los factores determinantes extraídos directamente de la realidad del proyecto FitConnect son:

* **El conflicto y la interdependencia de roles en el MVP:** El éxito del negocio freemium depende de un equilibrio simbiótico. No sirve la estrategia de Gabriel de traer solo demanda de usuarios si no hay un panel mínimo para que los entrenadores de Ana carguen contenido de calidad. Scrum permite balancear estas prioridades entrega tras entrega.
* **Las severas restricciones técnicas de arquitectura:** Diego (CTO) ha fijado límites estrictos e innegociables basados en el rendimiento (instalador de menos de 200MB, carga en menos de 3 segundos, uso de CDN con HLS/DASH y fallback automático de alta resolución ante latencias mayores a 800ms). El desarrollo en sprints permite realizar pruebas de estrés e investigación técnica (*Spikes*) de forma temprana para validar el backend.
* **El altísimo riesgo regulatorio y patrimonial:** Mara (Legal) dejó en claro que postergar las políticas de privacidad y los Términos y Condiciones representa un peligro inaceptable para FitConnect. Las fotografías de progreso premium constituyen datos sensibles médicos/biométricos sujetos a estándares internacionales como HIPAA y GDPR. Scrum nos obliga a integrar estos flujos regulatorios (pantallas de consentimiento separado y verificación de identidad documental KYC de entrenadores) como parte del *Definition of Done* (Criterios de Aceptación obligatorios) desde las primeras iteraciones, neutralizando demandas legales antes del lanzamiento comercial.
* **La volatilidad y el Churn del mercado fitness:** Al operar bajo un modelo freemium en un entorno competitivo, es fundamental recolectar datos reales de uso lo antes posible. La naturaleza iterativa e incremental de Scrum garantiza inspeccionar el producto con usuarios reales como Enzo y adaptar la biblioteca de calistenia antes de que se venza el ciclo crítico de adopción (semana 4).
