# Punto 3 – Modelos de Proceso

**FitConnect – Trabajo Práctico Primera Etapa**
**Integrantes del grupo:** Agustín Curvetto y Santiago Menghi

---

## Análisis Comparativo de los Modelos de Proceso Aplicados a FitConnect

A continuación se evalúan los distintos modelos de proceso de ingeniería de software vistos en la materia, detallando una ventaja y una desventaja específica de cada uno frente a las necesidades técnicas, de negocio y legales de FitConnect.

| Modelo | Ventaja aplicada a FitConnect | Desventaja aplicada a FitConnect |
|---|---|---|
| **1. Cascada** | Permite definir de forma estricta y documentada, desde el día uno, los requisitos de rendimiento no negociables exigidos por el CTO: instalador menor a 200MB, inicio en menos de 3 segundos y arquitectura CDN con protocolo HLS/DASH. | Es inviable por el conflicto de prioridades del MVP: Gabriel necesita captar 15.000 usuarios en 3 meses con onboarding en máximo 3 taps, mientras Ana advierte que el 85% de los entrenadores abandonará si no hay herramientas desde el inicio. Cascada no permite reconciliar estas demandas hasta fases muy avanzadas. |
| **2. Modelo en V** | Vincula cada fase de diseño con su plan de pruebas, facilitando la verificación temprana del backend para soportar un 99,5% de uptime y validar el fallback automático en paralelo con el desarrollo. | Carece de flexibilidad para resolver discrepancias que surgen tarde: si en la verificación se descubre que el onboarding requiere cambios arquitectónicos, el modelo no permite pivotear sin descartar trabajo ya hecho. |
| **3. Incremental** | Permite lanzar la app por partes, priorizando primero el descubrimiento de entrenadores y funcionalidades básicas, e incorporando en incrementos posteriores las herramientas de creación de rutinas. | Si el primer incremento no incluye capacidades mínimas de gestión para entrenadores, Ana advierte que no se alcanzará la retención necesaria, y fallará la base de contenido que alimenta el modelo freemium. |
| **4. Iterativo** | Ayuda a combatir el alto "churn" (deserción) del mercado fitness: las iteraciones cortas permiten recolectar feedback real y ajustar la experiencia en cada ciclo. | Existe riesgo de invertir demasiado tiempo en cambios menores de interfaz sin avanzar en funcionalidades críticas, o de exponer datos sensibles (fotos de progreso) si no hay una estrategia de cumplimiento clara desde el inicio. |
| **5. Prototipos** | Ideal para maquetar rápido la herramienta drag-and-drop de rutinas que pide Ana, o las pantallas de onboarding que Gabriel quiere validar antes de invertir en desarrollo profundo. | Existe el riesgo de que el prototipo termine usándose como producto final sin las mejoras estructurales necesarias, obligando después a refactorizar para cumplir los límites técnicos de Diego o los requisitos legales de Mara. |
| **6. Espiral** | Es excelente para reducir riesgos durante todo el proyecto, incluyendo evaluaciones iterativas de cumplimiento regulatorio (GDPR/HIPAA) que Mara considera críticas. | Requiere más tiempo, planificación y recursos que otros modelos, lo que retrasaría el lanzamiento del MVP y entra en conflicto con el objetivo comercial de captar 15.000 usuarios en 3 meses. |
| **7. Ágil (Scrum)** | Trabajar en sprints cortos permite reconciliar, incremento a incremento, las demandas de Gabriel (onboarding rápido), Ana (herramientas de entrenadores), Diego (restricciones técnicas) y Mara (cumplimiento legal). | Requiere participación activa y constante de todos los interesados; si no están disponibles para el Sprint Planning o las revisiones, las decisiones se retrasan y el equipo trabaja sobre supuestos incorrectos. |

---

## Respuestas a las Preguntas del Proyecto

### ¿Qué modelo de proceso recomendarían para FitConnect y por qué?

**Recomendación:** un **Modelo de Ciclo de Vida Incremental**, donde cada incremento se gestiona internamente con prácticas ágiles de **Scrum** (sprints de 2 semanas, Sprint Planning, revisiones y retrospectivas).

**Justificación:** FitConnect es un marketplace de dos lados con necesidades interdependientes pero en tensión directa para el MVP. Gabriel necesita captar usuarios rápido con un onboarding mínimo; Ana necesita herramientas de gestión desde el inicio o pierde entrenadores. Un ciclo de vida **incremental** resuelve esta tensión a nivel macro: permite entregar primero un núcleo funcional (usuario freemium + descubrimiento de entrenadores) y sumar en incrementos posteriores las herramientas más complejas (plantillas avanzadas, drag-and-drop, panel de progreso). Dentro de cada incremento, trabajar con **Scrum** permite ajustar el detalle semana a semana según el feedback real de usuarios y entrenadores, sin comprometer la fecha de entrega del incremento completo.

### ¿Qué factores del proyecto influyeron en la decisión?

- **Interdependencia y conflicto de roles en el MVP:** el modelo freemium depende de la calidad del contenido que suben los entrenadores; si Ana ve que abandonan, el flujo de contenido colapsa. El enfoque incremental permite avanzar ambas necesidades en paralelo, evitando la parálisis del modelo Cascada.
- **Restricciones técnicas estrictas:** Diego fijó límites duros (instalador < 200MB, arranque < 3s, CDN con HLS/DASH, uptime 99,5%). Trabajar por incrementos con sprints cortos permite validar cada restricción apenas se libera un incremento, sin esperar al final del proyecto.
- **Riesgo regulatorio alto:** las fotos de progreso premium son datos sensibles de salud sujetos a GDPR/HIPAA. Cada incremento incluye revisión de compliance antes de pasar al siguiente, evitando acumular deuda legal.
- **Alta volatilidad del mercado fitness:** el churn del sector es alto, por lo que necesitamos poder pivotear la experiencia de onboarding rápido si las métricas de retención bajan; los sprints dentro de cada incremento dan esa velocidad de reacción.

---

## Conclusión

Se adopta un **Modelo de Ciclo de Vida Incremental**, con **Scrum** como método de trabajo dentro de cada incremento. Este enfoque combinado reconcilia la urgencia comercial (lanzamiento en 3 meses), la complejidad técnica (múltiples restricciones no negociables), la volatilidad del negocio (alto churn) y los requisitos regulatorios (datos sensibles de salud), sin sacrificar ninguno de esos cuatro ejes de presión.
