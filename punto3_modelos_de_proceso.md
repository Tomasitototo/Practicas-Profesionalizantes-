# Punto 3 – Modelos de Proceso

> **FitConnect – Trabajo Práctico Primera Etapa**

---

## Tabla comparativa de Modelos de Proceso

| Modelo de Proceso | Ventaja para FitConnect | Desventaja para FitConnect |
|---|---|---|
| **Modelo Cascada** | Permite documentar muy bien los requisitos iniciales (marketplace de trainers, sistema de seguimiento, modelo freemium), lo que facilita una arquitectura ordenada desde el principio. | FitConnect requiere feedback constante de usuarios y trainers; la cascada no permite volver atrás fácilmente si los requisitos cambian o si las pruebas revelan problemas en etapas anteriores. |
| **Modelo en V** | Al tener pruebas definidas para cada fase de desarrollo, garantiza que funcionalidades críticas como el sistema de pagos (comisión de la plataforma) y el seguimiento de progreso sean verificadas formalmente. | Es rígido y costoso de modificar. Si durante las pruebas de integración se descubre que el sistema de seguimiento no satisface a los usuarios, corregirlo implica retroceder varias fases. |
| **Modelo Incremental** | Permite lanzar una versión funcional básica de FitConnect (biblioteca de ejercicios + dos programas básicos del plan gratuito) e ir agregando funcionalidades como el marketplace o el análisis avanzado en incrementos posteriores. | Cada incremento debe integrarse con los anteriores; si la arquitectura inicial no fue bien pensada, la integración de módulos como la comunidad o las herramientas para trainers puede volverse compleja y generar deuda técnica. |
| **Modelo Iterativo** | Permite refinar funcionalidades a partir del feedback real de usuarios como Enzo (usuario activo) y Ana (Head de Entrenadores), mejorando aspectos como la UX de búsqueda de trainers o la visualización de gráficos de progreso en cada iteración. | Sin un backlog bien priorizado, las iteraciones pueden perder foco y consumir tiempo en mejoras menores en lugar de avanzar en funcionalidades core de la plataforma. |
| **Modelo de Prototipos** | Muy útil en las etapas tempranas para validar con usuarios reales cómo debería verse el marketplace de trainers, el flujo de suscripción freemium o el sistema de seguimiento, antes de invertir en desarrollo. | El riesgo de "prototype creep": que el equipo termine construyendo sobre un prototipo descartable en lugar de rediseñar correctamente, generando una base de código frágil que no cumpla los requisitos de rendimiento (inicio < 3 segundos, < 200 MB). |
| **Modelo en Espiral** | Incorpora análisis de riesgos en cada vuelta, ideal para una plataforma que maneja datos sensibles de usuarios y transacciones económicas (Mara – Legal/Risk & Insurance), y que debe cumplir requisitos de rendimiento en dispositivos de gama media-baja. | Es un modelo costoso en tiempo y recursos de gestión. Para un proyecto que necesita salir al mercado con agilidad, las múltiples rondas de análisis de riesgo pueden retrasar los lanzamientos. |
| **Modelo Ágil (Scrum/XP)** | Permite trabajar con sprints cortos, adaptarse rápido a cambios de mercado (el fitness digital es muy dinámico), incorporar feedback continuo de Gabriel (Product Manager), Ana y Enzo, y entregar valor incremental con cada sprint. | Requiere disponibilidad constante del cliente/stakeholder y un equipo con experiencia en Agile. Si los roles no están bien definidos o hay poca comunicación entre el equipo y los stakeholders, los sprints pueden perder dirección. |

---

## Modelo recomendado para FitConnect

**Recomendamos el Modelo Ágil (Scrum)**, complementado con prácticas de **Modelo Incremental** para las primeras versiones.

### Justificación

**Scrum** es el modelo más adecuado por los siguientes motivos directamente relacionados con el contexto de FitConnect:

1. **Requisitos cambiantes y dinámicos:** FitConnect opera en el mercado del fitness digital, que cambia rápido. Las necesidades de los usuarios (Enzo) y los trainers (Ana) pueden evolucionar durante el desarrollo; Scrum permite adaptarse en cada sprint sin frenar el proyecto.

2. **Stakeholders accesibles para feedback continuo:** El enunciado presenta personas concretas con quienes dialogar: Gabriel (Product Manager), Ana (Head de Entrenadores), Enzo (usuario activo), Mara (Legal) y Diego (CTO/DevOps). Esto es exactamente lo que Scrum necesita: un Product Owner con acceso a interesados reales que puedan validar cada entrega.

3. **Entrega de valor temprana:** Con Scrum se puede lanzar una primera versión funcional con la biblioteca de ejercicios y los dos programas básicos (plan gratuito), e ir sumando el marketplace, el sistema de seguimiento avanzado y las herramientas para trainers en sprints posteriores.

4. **Requisitos técnicos no funcionales claros:** Los requisitos de rendimiento (inicio < 3 segundos, < 200 MB, compatibilidad con gama media-baja) pueden incorporarse como criterios de aceptación en cada sprint, asegurando que no se descuiden a lo largo del desarrollo.

5. **Modelo freemium requiere iteración:** La lógica del modelo de negocio (gratuito vs. premium, comisión por transacción de trainers) necesita validarse con usuarios reales antes de escalar; Scrum permite pivotar rápido si algo no funciona como se espera.

### Factores del proyecto que influyeron en la decisión

- La existencia de **distintos tipos de usuarios** (personas que entrenan, trainers, administradores de la plataforma) con necesidades diferentes requiere iterar y validar con cada grupo.
- El **modelo freemium** implica que las funcionalidades premium deben justificarse con valor real percibido por el usuario, algo que solo se descubre con feedback continuo.
- Los **requisitos de rendimiento en dispositivos de gama media-baja** requieren pruebas frecuentes en condiciones reales, lo cual encaja con los ciclos cortos de Scrum.
- La **presencia de un área legal (Mara)** que debe revisar aspectos de riesgo y seguros sugiere que el equipo necesita flexibilidad para incorporar observaciones legales sin bloquear el desarrollo completo.
