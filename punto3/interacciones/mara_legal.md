# Interacciones - Mara (Legal)

## Sesión 1: Requisitos Regulatorios
**Fecha:** 2024-11-18  
**Hora:** 10:15 - 11:00

**Pregunta del equipo:**
¿Qué regulaciones afectan a FitConnect y qué implicaciones tienen para el desarrollo?

**Respuesta de Mara:**
FitConnect maneja datos sensibles. Las fotografías de progreso están vinculadas a la salud del usuario. Eso nos pone bajo GDPR (si tenemos usuarios en EU) y potencialmente bajo HIPAA (si ofrecemos servicios relacionados con salud). 

Los requisitos más importantes:
1. **Consentimiento explícito:** Antes de almacenar cualquier foto de progreso, necesitamos consentimiento documentado del usuario.
2. **Encriptación:** Los datos en tránsito y en reposo deben estar encriptados.
3. **Derecho al olvido:** Si un usuario pide que se borren sus datos, tenemos que poder hacerlo en 30 días (GDPR).
4. **Auditoría:** Necesitamos registros de quién accede a qué datos y cuándo.

Esto no es opcional. Si violamos estas regulaciones, las multas son severísimas: hasta 4% del revenue anual en GDPR.

---

## Sesión 2: Impacto en la Arquitectura
**Fecha:** 2024-11-25  
**Hora:** 15:30 - 16:15

**Pregunta del equipo:**
¿Cómo impactan estas regulaciones en el modelo de proceso que elijamos?

**Respuesta de Mara:**
El modelo de proceso tiene que permitir revisiones de seguridad y compliance en cada iteración. Cascada sería un desastre porque tocaríamos compliance al final. El Modelo en Espiral es perfecto para esto: cada ciclo incluye una evaluación de riesgos que cubre la conformidad regulatoria. Scrum también puede funcionar si hacemos una revisión de compliance al final de cada sprint.

La clave es no dejar para el final lo que debería estar presente desde el inicio.
