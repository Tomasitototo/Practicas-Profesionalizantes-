# Punto 3 – Modelos de Proceso

**FitConnect – Trabajo Práctico Primera Etapa**  
**Integrantes del grupo:** [Completar con los nombres de los integrantes]

---

# Análisis Comparativo de los Modelos de Proceso Aplicados a FitConnect

A continuación, se evalúan los distintos modelos de proceso de ingeniería de software, detallando sus ventajas y desventajas específicas frente a las necesidades técnicas, de negocio y legales del proyecto FitConnect.

## 1. Modelo Cascada
* **Ventaja aplicada a FitConnect:** Permite definir de manera sumamente estricta y documentada desde el primer día los requisitos de rendimiento innegociables exigidos por el CTO, tales como un instalador menor a 200MB, inicio en menos de 3 segundos y una arquitectura CDN con protocolo HLS/DASH [Ref: Enunciado (3).pdf - Testimonio de Diego].
* **Desventaja aplicada a FitConnect:** Es completamente inviable debido al conflicto de prioridades en el MVP: Gabriel prioriza estabilizar el core gratuito y el onboarding en 3 taps antes de potenciar el marketplace, mientras que Ana exige que el panel de entrenadores y las comisiones estén desde el Sprint 1 para que el contenido no sea genérico (Sesión P5 vs P7) [Ref: Enunciado (3).pdf - Testimonios de Gabriel y Ana]. Un cambio en etapas avanzadas bajo este modelo rígido paralizaría el desarrollo.

## 2. Modelo en V
* **Ventaja aplicada a FitConnect:** Vincula directamente cada fase de diseño con su respectivo plan de pruebas [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3]. Esto facilita la verificación temprana del backend para soportar un 99.5% de uptime y permite testear el comportamiento del fallback automático con frames estáticos cuando la latencia supera los 800 ms [Ref: Enunciado (3).pdf - Testimonio de Diego].
* **Desventaja aplicada a FitConnect:** Carece de la flexibilidad necesaria para resolver las discrepancias operativas del equipo. Si en fases avanzadas de la verificación se descubre que el flujo de comisiones del 20-30% exigido por Ana [Ref: Enunciado (3).pdf - Testimonio de Ana] o los contratos obligatorios de Mara [Ref: Enunciado (3).pdf - Testimonio de Mara] ralentizan el registro ágil de usuario planteado por Gabriel [Ref: Enunciado (3).pdf - Testimonio de Gabriel], la reingeniería y el retorno a fases previas serían extremadamente costosos.

## 3. Modelo Incremental
* **Ventaja aplicada a FitConnect:** Permite lanzar la aplicación por partes [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3], priorizando la visión de Gabriel para captar los 15k usuarios del MVP mediante un núcleo básico enfocado en el usuario final (configuración en menos de 3 taps y rutinas de 4, 8 o 16 semanas para que usuarios como Enzo inicien rápido) [Ref: Enunciado (3).pdf - Testimonio de Gabriel].
* **Desventaja aplicada a FitConnect:** Representa un peligro comercial y de adopción crítico. Ana advierte que, sin herramientas de gestión desde el inicio, no alcanzará su objetivo de retener el 85% de entrenadores, lo que dejaría la plataforma sin contenido de calidad [Ref: Enunciado (3).pdf - Testimonio de Ana]. Además, postergar las retenciones automatizadas e integraciones de términos legales vulnera las directrices mandatorias de compliance [Ref: Enunciado (3).pdf - Testimonio de Mara].

## 4. Modelo Iterativo
* **Ventaja aplicada a FitConnect:** Ayuda a combatir el brutal "churn" (deserción) del mercado fitness que tanto preocupa al Product Manager [Ref: Enunciado (3).pdf - Testimonio de Gabriel]. Permite lanzar versiones de la biblioteca de ejercicios de calistenia y ajustar el sistema de tracking básico ciclo a ciclo basándose en la experiencia y el progreso real de los usuarios [Ref: Enunciado (3).pdf - Descripción General y Testimonio de Gabriel].
* **Desventaja aplicada a FitConnect:** Existe el riesgo de que el equipo dedique demasiado tiempo a cambios poco importantes en la interfaz de usuario (UX) [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3], descuidando la implementación de la infraestructura base del backend, como la memoria caché local en disco limitada a 50MB administrada por LRU [Ref: Enunciado (3).pdf - Testimonio de Diego] o las auditorías de privacidad de datos sensibles [Ref: Enunciado (3).pdf - Testimonio de Mara].

## 5. Modelo de Prototipos
* **Ventaja aplicada a FitConnect:** Es ideal para diseñar maquetas rápidas de la herramienta drag-and-drop para rutinas que pide Ana [Ref: Enunciado (3).pdf - Testimonio de Ana] o las pantallas de consentimiento informado por separado que exige Legal [Ref: Enunciado (3).pdf - Testimonio de Mara], validando la usabilidad con los interesados antes de programar [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3].
* **Desventaja aplicada a FitConnect:** Existe el riesgo de utilizar los prototipos como producto final sin realizar las mejoras estructurales necesarias [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3], subestimando la altísima complejidad técnica del backend que el CTO debe configurar para soportar streaming adaptativo por bitrate y el cifrado de datos biométricos [Ref: Enunciado (3).pdf - Testimonio de Diego].

## 6. Modelo en Espiral
* **Ventaja aplicada a FitConnect:** Es excelente para identificar y reducir riesgos durante todo el proyecto, siendo de gran utilidad para aplicaciones que manejan datos personales y transacciones económicas [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3]. Ayuda a mitigar el riesgo de almacenamiento de videos de Diego [Ref: Enunciado (3).pdf - Testimonio de Diego] y la exposición patrimonial por incumplimiento de estándares HIPAA y GDPR advertida por Legal [Ref: Enunciado (3).pdf - Testimonio de Mara].
* **Desventaja aplicada a FitConnect:** Requiere más tiempo, planificación y recursos que otros modelos [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3]. Esto retrasaría drásticamente el lanzamiento rápido del MVP y los despliegues continuos, chocando directamente con la urgencia del Product Manager de captar demanda de forma inmediata [Ref: Enunciado (3).pdf - Testimonio de Gabriel].

## 7. Modelo Ágil (Scrum)
* **Ventaja aplicada a FitConnect:** Permite trabajar en períodos cortos llamados sprints, facilitando la incorporación de cambios frecuentes [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3]. Es el modelo óptimo para equilibrar las posturas encontradas del equipo, permitiendo estabilizar el flujo de usuario gratuito (Gabriel) al mismo tiempo que se desarrolla el panel base de entrenadores (Ana) y las pantallas de pre-actividad obligatorias (Mara) bajo la arquitectura eficiente de Diego [Ref: Enunciado (3).pdf - Testimonios del Equipo].
* **Desventaja aplicada a FitConnect:** Requre una participación activa de todos los involucrados y una rigurosa organización [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3]. Si el Product Owner no logra arbitrar con firmeza entre las presiones comerciales de Gabriel, las herramientas operativas de Ana y los bloqueos mandatorios de Mara, el sprint fracasará.

---

# Respuestas a las Preguntas del Proyecto

### ¿Qué modelo de proceso recomendarían para FitConnect y por qué?

**Recomendación:** Se recomienda utilizar el **Modelo Ágil (Scrum)**, complementado con un enfoque incremental para la liberación de las primeras iteraciones de la plataforma [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3].

**Justificación:** FitConnect es un marketplace simbiótico donde coexisten dos tipos de usuarios con necesidades interdependientes pero en conflicto directo para el MVP. Por un lado, Gabriel (PM) prioriza estabilizar el core gratuito y el onboarding en 3 taps antes de potenciar el marketplace, mientras que Ana exige que el panel de entrenadores y las comisiones estén desde el Sprint 1 para que el contenido no sea genérico (Sesión P5 vs P7) [Ref: Enunciado (3).pdf - Testimonios de Gabriel y Ana]. 

Scrum permite solucionar este conflicto mediante sesiones de *Sprint Planning*, donde los requerimientos se fragmentan en Historias de Usuario mínimas viables. De esta manera, en el Sprint 1 se puede desarrollar la configuración veloz de usuario (Gabriel) alimentada por un sistema básico de plantillas para entrenadores (Ana). Así se entrega valor inmediato a ambas partes, evitando el abandono prematuro de usuarios como Enzo [Ref: Enunciado (3).pdf - Testimonio de Gabriel] y asegurando contenido de calidad desde el inicio del ciclo de vida del software.

---

### ¿Qué factores del proyecto influyeron en su decisión?

Los factores determinantes extraídos de la realidad de FitConnect [Ref: Trabajo_Practico_-_Primera_Etapa_1 (4).pdf - Punto 3] son:

* **La interdependencia y conflicto de roles en el MVP:** El modelo de negocio freemium se alimenta de la calidad del trabajo del entrenador [Ref: Enunciado (3).pdf - Testimonio de Ana]. No es viable traer solo demanda de usuarios si la oferta carece de herramientas básicas. Ana advierte que, sin herramientas de gestión desde el inicio, no alcanzará su objetivo de retener el 85% de entrenadores, lo que dejaría la plataforma sin contenido de calidad [Ref: Enunciado (3).pdf - Testimonio de Ana]. Scrum permite balancear estas prioridades entrega tras entrega.
* **Las severas restricciones técnicas de arquitectura:** Diego (CTO) fijó límites estrictos (instalador <200MB, arranque <3s, uso de CDN con HLS/DASH y un límite de caché local de 50MB gestionado por LRU) [Ref: Enunciado (3).pdf - Testimonio de Diego]. El enfoque ágil permite realizar *Spikes* técnicos (investigaciones en Sprints) para asegurar estas metas de rendimiento antes del despliegue masivo.
* **El alto riesgo regulatorio y patrimonial:** Las fotografías de progreso premium constituyen datos sensibles vinculados a la salud sujetos a normas estrictas como HIPAA y GDPR [Ref: Enunciado (3).pdf - Testimonio de Mara]. Mara (Legal) dictamina que postergar su tratamiento a incrementos avanzados constituye una exposición patrimonial inaceptable [Ref: Enunciado (3).pdf - Testimonio de Mara]. Scrum permite mitigar esto incluyendo los flujos de consentimiento informado y verificación documental documental KYC como Criterios de Aceptación obligatorios (*Definition of Done*) desde el primer Sprint.
* **La volatilidad y el Churn del mercado fitness:** El mercado del fitness posee una deserción brutal [Ref: Enunciado (3).pdf - Testimonio de Gabriel]. La naturaleza iterativa de Scrum garantiza inspeccionar las métricas de progreso de los usuarios de forma empírica y adaptar la biblioteca de calistenia antes de que venza el ciclo crítico de adopción en la semana 4 [Ref: Enunciado (3).pdf - Testimonio de Gabriel].
*
