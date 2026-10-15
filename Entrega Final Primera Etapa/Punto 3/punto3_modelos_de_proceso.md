# Punto 3: Modelos de Proceso

**FitConnect: Trabajo Práctico, Primera Etapa**
**Integrantes del grupo:** Agustín Curvetto, Santiago Menghi, Bautista Suero y Tomás Rodil

---

## Análisis comparativo de los modelos de proceso aplicados a FitConnect

La siguiente tabla evalúa cada modelo de proceso visto en la materia, con una ventaja y una desventaja de aplicarlo a FitConnect según las necesidades técnicas, de negocio y legales relevadas con los stakeholders.

| Modelo de Proceso | Ventaja | Desventaja |
|---|---|---|
| **Modelo Cascada** | Permite definir desde el primer día, de forma estricta y documentada, los requisitos de rendimiento de Diego: instalador menor a 200 MB, inicio en menos de 3 segundos, streaming por CDN (HLS/DASH) y caché local de 50 MB con fallback automático. | Es inviable por el conflicto de prioridades del MVP: Gabriel necesita captar 15.000 usuarios con un registro de máximo 3 toques, y Ana advierte que sin herramientas desde el inicio los entrenadores abandonan (su meta es retener al 85 %). Cascada no permite reconciliar estas demandas hasta fases muy avanzadas. |
| **Modelo en V** | Vincula cada fase de diseño con su plan de pruebas. Facilita verificar temprano que el backend soporte un 99,5 % de disponibilidad y validar el fallback automático en paralelo con el desarrollo, reduciendo riesgos técnicos. | Carece de la flexibilidad necesaria para resolver las discrepancias entre stakeholders. Si en fases avanzadas de la verificación se descubre que el registro requiere cambios de arquitectura, el modelo no permite cambiar de rumbo sin descartar trabajo considerable. |
| **Modelo Incremental** | Permite lanzar la aplicación por partes, priorizando la visión de Gabriel: un primer incremento con la versión gratuita (biblioteca de ejercicios y programas básicos) para captar los 15.000 usuarios iniciales. | Si el primer incremento no incluye herramientas mínimas para crear rutinas, Ana no alcanza su objetivo de retener al 85 % de los entrenadores, y fracasa la fuente de contenido que alimenta el modelo freemium. |
| **Modelo Iterativo** | Ayuda a combatir la deserción del mercado fitness, que Gabriel describe como "brutal". Las iteraciones cortas permiten recopilar opiniones de usuarios reales y ajustar rápidamente la experiencia para mejorar la retención en cada ciclo. | Existe el riesgo de dedicar demasiado tiempo a cambios poco importantes en la interfaz sin avanzar en funcionalidades críticas. Además, sin una estrategia clara de cumplimiento legal, las fotos de progreso pueden quedar expuestas sin las protecciones que exige Mara. |
| **Modelo de Prototipos** | Es ideal para diseñar maquetas rápidas del armado de rutinas arrastrando ejercicios que necesita Ana, o de las pantallas de registro que Gabriel quiere validar, antes de invertir en el desarrollo. Permite tomar decisiones informadas sobre requisitos en conflicto. | Existe el riesgo de usar los prototipos como producto final sin las mejoras estructurales necesarias. Si después hay que rehacer la arquitectura para cumplir los límites técnicos de Diego o los requisitos legales de Mara, se pierde credibilidad y tiempo. |
| **Modelo en Espiral** | Es excelente para identificar y reducir riesgos durante todo el proyecto. Permite evaluar en cada ciclo el cumplimiento de las normas de privacidad (GDPR y HIPAA) que Mara considera críticas, junto con los riesgos técnicos, de negocio y de retención. | Requiere más tiempo, planificación y recursos que otros modelos. Retrasaría el lanzamiento del MVP, en conflicto con el objetivo de Gabriel de captar rápido los primeros 15.000 usuarios. |
| **Modelo Ágil (Scrum/XP)** | Permite trabajar en sprints cortos e incorporar cambios frecuentes basados en la opinión de los usuarios. Los sprints de 2 semanas permiten reconciliar las demandas de Gabriel (registro rápido), Ana (herramientas para entrenadores), Diego (restricciones técnicas) y Mara (cumplimiento legal). Las prácticas de XP, como las pruebas automatizadas, responden a lo que pidió Diego: QA y pruebas desde el primer día. | Requiere participación activa de todos los involucrados y una organización rigurosa. Si los stakeholders no están disponibles para la planificación y las revisiones de cada sprint, las decisiones se retrasan y el equipo trabaja sobre supuestos incorrectos. |

---

## Respuestas a las preguntas del proyecto

### ¿Qué modelo de proceso recomendarían para FitConnect y por qué?

**Recomendación:** se recomienda utilizar el **Modelo Ágil (Scrum)**, complementado con un enfoque incremental para la liberación de las primeras versiones de la plataforma.

**Justificación:** FitConnect es un marketplace donde conviven dos tipos de usuarios con necesidades que dependen una de la otra, pero que compiten por el primer lanzamiento. Por un lado, Gabriel necesita captar 15.000 usuarios con un registro de máximo 3 toques. Por otro, Ana advierte que, sin herramientas desde el inicio, los entrenadores abandonan la plataforma, y su meta es retener al 85 %.

Scrum permite resolver este conflicto en la planificación de cada sprint, donde los requerimientos se dividen en historias de usuario mínimas. Así se acordó con los stakeholders:

- **Sprints 1 y 2 (primer incremento, el MVP):** registro en máximo 3 toques con un programa recomendado según el nivel del usuario; biblioteca de ejercicios y programas de 4 a 16 semanas; registro de entrenamientos con contador manual de repeticiones, récords y gráficos de avance; panel mínimo del entrenador (plantillas, duplicación, armado de rutinas arrastrando ejercicios, asignación a alumnos y progreso básico); comisión del 20 % visible y calificación de 1 a 5; términos y consentimientos separados, y fotos de progreso cifradas.
- **Sprints 3 y 4:** búsqueda en el marketplace por especialidad, tarifa y disponibilidad; reserva de sesiones; suscripción premium; comunidad con rachas y desafíos.
- **Sprint 5 en adelante:** calendario avanzado, reportes detallados para entrenadores, nutrición y optimizaciones de rendimiento.

Cada sprint incluye la verificación de las restricciones técnicas (Diego con pruebas de rendimiento), del cumplimiento legal (Mara revisa el acceso a datos sensibles) y de las métricas de retención (Gabriel mide el abandono en el registro).

### ¿Qué factores del proyecto influyeron en su decisión?

- **La dependencia entre oferta y demanda en el MVP:** el modelo freemium se alimenta de la calidad del trabajo del entrenador. Si los entrenadores abandonan, el flujo de contenido colapsa y Gabriel no puede retener a los usuarios gratuitos. Scrum permite que ambas necesidades avancen en paralelo dentro de cada sprint, evitando la parálisis de cascada.
- **Las restricciones técnicas:** Diego fijó límites estrictos (instalador menor a 200 MB, arranque en menos de 3 segundos, CDN con HLS/DASH, caché local de 50 MB y 99,5 % de disponibilidad). Con sprints de 2 semanas, cada restricción se valida a medida que se construye; si un sprint viola algún límite, se detecta y corrige de inmediato.
- **El riesgo legal y patrimonial:** las fotos de progreso son datos sensibles vinculados a la salud, sujetos a GDPR y HIPAA, y Mara exige que su protección esté desde las primeras iteraciones. Scrum permite revisar el cumplimiento en la revisión y la retrospectiva de cada sprint, para que no se acumulen deudas legales.
- **Los cambios en las necesidades de los stakeholders:** durante el relevamiento cambiaron el porcentaje de comisión (de una propuesta de 20 % a 30 % a un 20 % fijo) y el contenido del primer sprint. Scrum permite volver a priorizar en cada sprint sin rehacer el plan completo.

---

## Conclusión

El Modelo Ágil (Scrum), con entregas incrementales, es el más adecuado para FitConnect porque reconcilia la urgencia comercial (lanzar rápido el MVP), la complejidad técnica (múltiples restricciones), la volatilidad del negocio (alta deserción) y los requisitos legales (datos sensibles de salud). Los otros modelos tienen fortalezas específicas, pero no logran manejar al mismo tiempo estos cuatro ejes sin sacrificar alguno.
