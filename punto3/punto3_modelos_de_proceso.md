# Punto 3 – Modelos de Proceso

**FitConnect – Trabajo Práctico Primera Etapa**  
**Integrantes del grupo:** Agustín Curvetto y Santiago Menghi

---

# Análisis Comparativo de los Modelos de Proceso Aplicados a FitConnect

A continuación, se evalúan los distintos modelos de proceso de ingeniería de software, detallando sus ventajas y desventajas específicas frente a las necesidades técnicas, de negocio y legales de FitConnect.

## 1. Modelo Cascada

* **Ventaja aplicada a FitConnect:** Permite definir de manera sumamente estricta y documentada desde el primer día los requisitos de rendimiento innegociables exigidos por el CTO. Diego estableció límites claros: instalador menor a 200MB, inicio en menos de 3 segundos, arquitectura CDN con protocolo HLS/DASH, y caché local de 50MB con fallback automático (ver evidencia 03_diego_cto_restricciones.md).

* **Desventaja aplicada a FitConnect:** Es completamente inviable debido al conflicto de prioridades en el MVP. Gabriel necesita captar 15.000 usuarios en 3 meses con onboarding en máximo 3 taps, mientras que Ana advierte que el 85% de los entrenadores abandonará si no hay herramientas desde el inicio. Cascada no permite reconciliar estas demandas contradictorias hasta fases muy avanzadas.

## 2. Modelo en V

* **Ventaja aplicada a FitConnect:** Vincula directamente cada fase de diseño con su respectivo plan de pruebas. Esto facilita la verificación temprana del backend para soportar un 99.5% de uptime y validar el fallback automático en paralelo con el desarrollo, reduciendo riesgos técnicos.

* **Desventaja aplicada a FitConnect:** Carece de la flexibilidad necesaria para resolver las discrepancias operativas del equipo. Si en fases avanzadas de la verificación se descubre que el flujo de onboarding requiere cambios arquitectónicos, el modelo no permite pivotear sin descartar trabajo considerable.

## 3. Modelo Incremental

* **Ventaja aplicada a FitConnect:** Permite lanzar la aplicación por partes, priorizando la visión de Gabriel para captar los 15.000 usuarios iniciales con funcionalidades básicas de descubrimiento de entrenadores. Las fases posteriores incorporan herramientas de creación de rutinas (ver evidencia 01_gabriel_pm_onboarding.md).

* **Desventaja aplicada a FitConnect:** Representa un peligro comercial y de adopción crítico. Ana advierte que sin herramientas de gestión desde el inicio, no alcanzará su objetivo de retención de entrenadores. Si la fase 1 no incluye capacidades mínimas de creación de rutinas, fracasará la base de suministro de contenido que alimenta el modelo de negocio freemium (ver evidencia 02_ana_entrenadores_retention.md).

## 4. Modelo Iterativo

* **Ventaja aplicada a FitConnect:** Ayuda a combatir el brutal "churn" (deserción) del mercado fitness que tanto preocupa a Gabriel. Las iteraciones cortas permiten recopilar feedback de usuarios reales y ajustar rápidamente la experiencia para mejorar retención en cada ciclo.

* **Desventaja aplicada a FitConnect:** Existe el riesgo de que el equipo dedique demasiado tiempo a cambios poco importantes en la interfaz de usuario sin avanzar en funcionalidades críticas. Además, sin una estrategia clara sobre cumplimiento regulatorio, pueden exponerse datos sensibles de fotos de progreso sin las protecciones legales requeridas (ver evidencia 04_mara_legal_gdpr_hipaa.md).

## 5. Modelo de Prototipos

* **Ventaja aplicada a FitConnect:** Es ideal para diseñar maquetas rápidas de la herramienta drag-and-drop para rutinas que Ana necesita o las pantallas de onboarding que Gabriel quiere validar antes de inversión de desarrollo profundo. Los prototipos permiten tomar decisiones informadas sobre requisitos conflictivos.

* **Desventaja aplicada a FitConnect:** Existe el riesgo de utilizar los prototipos como producto final sin realizar las mejoras estructurales necesarias. Si se presentan prototipos a usuarios finales y luego debe refactorizarse la arquitectura para cumplir con los límites técnicos de Diego o los requisitos legales de Mara, se perderá credibilidad y tiempo valioso.

## 6. Modelo en Espiral

* **Ventaja aplicada a FitConnect:** Es excelente para identificar y reducir riesgos durante todo el proyecto. Permite evaluaciones iterativas de conformidad regulatoria (GDPR/HIPAA) que Mara considera críticas. Cada ciclo espiral incluye análisis de riesgos: técnicos, de negocio, de retención y legales.

* **Desventaja aplicada a FitConnect:** Requiere más tiempo, planificación y recursos que otros modelos. Esto retrasaría drásticamente el lanzamiento del MVP, conflictando directamente con el objetivo de Gabriel de captar 15.000 usuarios en 3 meses. El overhead de gestión de riesgos iterativa no es viable bajo presión comercial de lanzamiento rápido.

## 7. Modelo Ágil (Scrum)

* **Ventaja aplicada a FitConnect:** Permite trabajar en períodos cortos llamados sprints, facilitando la incorporación de cambios frecuentes basados en feedback de usuarios. Los sprints de 2 semanas permiten al equipo reconciliar las demandas contradictorias de Gabriel (onboarding rápido), Ana (herramientas de entrenadores), Diego (restricciones técnicas) y Mara (cumplimiento legal) de forma incremental.

* **Desventaja aplicada a FitConnect:** Requiere participación activa de todos los involucrados y rigurosa organización. Si los stakeholders no están disponibles para sesiones de Sprint Planning o revisiones de Sprint, las decisiones se retrasan y el equipo trabaja sobre supuestos incorrectos.

---

# Respuestas a las Preguntas del Proyecto

### ¿Qué modelo de proceso recomendarían para FitConnect y por qué?

**Recomendación:** Se recomienda utilizar el **Modelo Ágil (Scrum)**, complementado con un enfoque incremental para la liberación de las primeras iteraciones de la plataforma.

**Justificación:** FitConnect es un marketplace simbiótico donde coexisten dos tipos de usuarios con necesidades interdependientes pero en conflicto directo para el MVP. Por un lado, Gabriel necesita captar 15.000 usuarios en 3 meses con onboarding en máximo 3 taps. Por otro, Ana advierte que el 85% de los entrenadores abandonará si no hay herramientas desde el inicio.

Scrum permite solucionar este conflicto mediante sesiones de Sprint Planning donde los requerimientos se fragmentan en Historias de Usuario mínimas viables. De esta manera:

- **Sprint 1-2:** Núcleo de usuario gratuito + descubrimiento de entrenadores + herramientas básicas de creación de rutinas
- **Sprint 3-4:** Herramientas avanzadas drag-and-drop + panel de progreso de clientes + encriptación de fotos
- **Sprint 5+:** Optimización de performance, fallback automático, auditoría de acceso

Cada sprint incluye verificación de restricciones técnicas (Diego con benchmarks), cumplimiento regulatorio (Mara revisa acceso a datos sensibles) y métricas de retención (Gabriel mide abandono en onboarding).

---

### ¿Qué factores del proyecto influyeron en su decisión?

Los factores determinantes extraídos de las sesiones de trabajo con stakeholders son:

* **La interdependencia y conflicto de roles en el MVP:** El modelo de negocio freemium se alimenta de la calidad del trabajo del entrenador. Si Ana ve que los entrenadores abandonan, el flujo de contenido colapsa y Gabriel no puede justificar la retención de usuarios gratuitos. Scrum permite que ambas necesidades avancen en paralelo dentro de cada sprint, evitando la parálisis de cascada (ver evidencia 05_conflicto_incremental_vs_scrum.md).

* **Las severas restricciones técnicas de arquitectura:** Diego fijó límites estrictos (instalador <200MB, arranque <3s, CDN con HLS/DASH, caché local 50MB, uptime 99.5%). Scrum con sprints de 2 semanas permite validación incremental de cada restricción sin esperar al final del proyecto. Si un sprint viola algún límite, se detecta y corrige inmediatamente (ver evidencia 03_diego_cto_restricciones.md).

* **El alto riesgo regulatorio y patrimonial:** Las fotografías de progreso premium constituyen datos sensibles vinculados a la salud, sujetos a GDPR y HIPAA. Scrum permite revisiones de compliance en la Demo del Sprint y Sprint Retrospective, asegurando que no se acumule deuda de conformidad (ver evidencia 04_mara_legal_gdpr_hipaa.md).

* **La volatilidad y el churn del mercado fitness:** Gabriel señala que la deserción en el mercado fitness es brutal. Scrum con feedback de usuarios en cada sprint permite pivotar rápidamente la experiencia de onboarding si las métricas de retención están bajando (ver evidencia 01_gabriel_pm_onboarding.md).

---

## Conclusión

El Modelo Ágil (Scrum) es el más adecuado para FitConnect porque reconcilia la urgencia comercial (lanzamiento en 3 meses), la complejidad técnica (múltiples restricciones), la volatilidad del negocio (churn alto) y los requisitos regulatorios (datos sensibles de salud). Los otros modelos, si bien tienen fortalezas específicas, no logran manejar simultáneamente estos cuatro ejes de presión sin sacrificar alguno de ellos.