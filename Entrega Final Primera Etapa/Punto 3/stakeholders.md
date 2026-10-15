# Análisis de Stakeholders y Definición del MVP

Este documento resume qué necesita cada stakeholder de FitConnect, en qué puntos sus necesidades entran en conflicto, cómo se resolvió cada conflicto y qué alcance tiene el Producto Mínimo Viable (MVP). La información surge del enunciado y de las consultas realizadas a cada stakeholder entre junio y octubre de 2026. Entre paréntesis se indica la fecha de la consulta de la que proviene cada dato.

---

## 1. Stakeholders

| Stakeholder | Rol | Qué representa |
|---|---|---|
| Gabriel | Product Manager | El negocio y la alta gerencia |
| Ana | Head de Entrenadores | La oferta: los entrenadores |
| Enzo | Usuario activo | La demanda: los deportistas |
| Mara | Legal (Risk & Insurance) | El cumplimiento legal y la gestión de riesgos |
| Diego | CTO / DevOps | La factibilidad técnica y la operación |

### Gabriel, Product Manager

- **Objetivo:** llegar a 15.000 usuarios y 200 entrenadores verificados en el MVP, y reducir el abandono temprano, que en el mercado fitness es muy alto (16/06).
- **Necesidades:**
  - Que el usuario configure su cuenta en menos de 3 toques y pueda empezar una rutina con su entrenador en 3 pasos (16/06).
  - Que el programa inicial se recomiende según el nivel, el objetivo y la disponibilidad que declara el usuario, y luego se ajuste con su progreso (04/10).
  - Rachas, logros y desafíos semanales para retener al usuario; la versión gratuita limitada a 2 programas para que Premium tenga valor (11/07).
- **Restricciones:** nutrición, reportes para entrenadores y calendario avanzado quedan para una fase posterior (16/06, 04/10).

### Ana, Head de Entrenadores

- **Objetivo:** retener al menos al 85 % de los entrenadores (26/06).
- **Necesidades:**
  - Un panel de trabajo completo: plantillas para editar y duplicar planes, armado de rutinas arrastrando ejercicios, registro de alumnos y vista del progreso de cada uno (16/06, 26/06).
  - Poder crear ejercicios nuevos, que quedan privados hasta ser revisados y aprobados (04/10).
  - Comisión clara y calificación obligatoria: el alumno califica de 1 a 5 después de cada sesión, con comentario opcional (04/10).
- **Restricciones:** reglas de entrenamiento que la app debe respetar: aumento semanal de carga de hasta 15 %, 48 horas de descanso entre sesiones del mismo grupo muscular, prerrequisitos por ejercicio y una pregunta posterior a la sesión sobre dolor (11/07).

### Enzo, Usuario activo

- **Objetivo:** ver que progresa y no lesionarse; su meta personal es lograr el muscle-up en 12 semanas (16/06, 26/06).
- **Necesidades:**
  - Gráficos de avance por mes y récords personales desde el primer día (16/06, 26/06).
  - Modo "hoy 20 minutos": una rutina corta inmediata, sin navegar menús (26/06).
  - Contador manual de repeticiones, sin sensores ni cámaras (26/06).
  - Un aviso si está entrenando más de lo que aguanta, basado en su propio reporte de cómo se siente (26/06).
- **Restricciones:** no quiere cargar datos médicos ni completar formularios largos (16/06). El costo y el equipamiento no son su barrera principal: entrena calistenia con una barra (16/06).

### Mara, Legal (Risk & Insurance)

- **Objetivo:** minimizar la exposición patrimonial, civil y regulatoria de FitConnect (16/06).
- **Necesidades:**
  - Términos y condiciones aceptados antes de cualquier transacción, con el porcentaje de comisión, el momento de la retención y una cláusula de exoneración por lesiones (16/06).
  - Verificación documental de los entrenadores antes de que puedan publicar o cobrar: automatizada con un servicio externo y revisión manual en los casos dudosos (16/06, 04/10).
  - Fotos de progreso con un consentimiento explícito y separado para cada foto que se sube, guardadas de forma cifrada y visibles solo para el usuario (11/07, 04/10).
- **Restricciones:** los datos de salud y las fotos son datos sensibles; su protección debe estar desde las primeras iteraciones, no en etapas posteriores (16/06).

### Diego, CTO / DevOps

- **Objetivo:** que la plataforma sea técnicamente viable y estable (16/06).
- **Necesidades:**
  - Videos de ejercicios por streaming desde una red de distribución de contenido, nunca dentro de la app (16/06).
  - Un equipo técnico especializado: dos desarrolladores mobile, dos backend, QA, un SRE junior y el CTO/DevOps (28/06, 04/10).
- **Restricciones:** instalador de menos de 200 MB, arranque en menos de 3 segundos y 99,5 % de disponibilidad (enunciado, 16/06).

---

## 2. Conflictos y cómo se resolvieron

| Conflicto | Postura de cada uno | Resolución acordada |
|---|---|---|
| **Qué entra en el primer sprint** (Gabriel y Ana) | Gabriel prioriza estabilizar la versión gratuita y el onboarding; Ana sostiene que sin herramientas para el entrenador no hay programas de calidad (16/06) | Gabriel acepta en el Sprint 1 un panel mínimo: seleccionar y duplicar plantillas, editar ejercicios, series y descansos, reordenar arrastrando, asignar planes y ver un progreso básico. Lo avanzado queda para después (04/10) |
| **Porcentaje de comisión** (Ana y el negocio) | Ana proponía entre 20 % y 30 % (16/06) | Comisión fija y visible del 20 % por transacción en el MVP (Ana 04/10, Gabriel 06/10) |
| **Registro rápido frente a requisitos legales** (Gabriel y Mara) | Gabriel exige menos de 3 toques; Mara exige términos y consentimientos explícitos | Los consentimientos se piden en el momento en que corresponden y no al registrarse: los términos, antes de la primera actividad o transacción; el de fotos, al subir cada foto (16/06, 04/10) |
| **Contenido completo frente a los límites técnicos** (Enzo y Ana, frente a Diego) | La biblioteca necesita videos desde varios ángulos; Diego exige menos de 200 MB y menos de 3 segundos | Los videos se reproducen por streaming y la app solo descarga lo necesario; si el video tarda más de 800 ms, se muestra una imagen fija con instrucciones (16/06, 04/10) |

---

## 3. Alcance del MVP

Del análisis anterior surge el alcance del primer incremento:

| Para quién | Qué incluye |
|---|---|
| Usuario | Registro en menos de 3 toques, programa recomendado según su nivel, biblioteca de ejercicios, programas de 4 a 16 semanas, contador manual de repeticiones, récords y gráficos de avance, reporte de cómo se sintió |
| Entrenador | Panel mínimo (plantillas, duplicación, armado arrastrando ejercicios, asignación a alumnos y progreso básico), verificación de identidad y certificaciones, comisión del 20 % visible, calificación de 1 a 5 |
| Legal | Términos y condiciones con exoneración, consentimientos separados para datos de salud y para cada foto |
| Técnica | Streaming de videos, instalador de menos de 200 MB, arranque en menos de 3 segundos |

Quedan para fases posteriores: nutrición, reportes detallados para entrenadores y calendario avanzado (16/06, 04/10).

---

## 4. Conclusión

Las necesidades de los stakeholders no son fijas: durante el relevamiento cambiaron el porcentaje de comisión, el contenido del primer sprint y la forma de pedir los consentimientos. Además, la oferta (Ana) y la demanda (Gabriel y Enzo) dependen una de la otra, y cada incremento tiene que respetar los límites de Diego y de Mara.

Por eso este análisis respalda la recomendación del Punto 3: **Scrum, complementado con un enfoque incremental**. Cada sprint entrega una parte usable del producto, permite volver a priorizar con los stakeholders lo que cambió y verificar en cada entrega las restricciones técnicas y legales, en lugar de descubrirlas al final.
