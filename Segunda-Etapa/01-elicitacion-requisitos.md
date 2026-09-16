# 1. Técnicas de Recolección de Requisitos (Unidad 4)

Para FitConnect elegimos dos técnicas de elicitación complementarias: una cualitativa y profunda (**Entrevistas**) y otra cuantitativa y masiva (**Encuestas / Cuestionarios**). La combinación permite validar en profundidad las necesidades de los perfiles clave (entrenadores, usuarios activos) y, al mismo tiempo, confirmar con números si esas necesidades se repiten en el resto del mercado objetivo.

---

## Técnica 1: Entrevistas

**Descripción del proceso — ¿Cómo se aplicaría en FitConnect?**

Se realizarían entrevistas semiestructuradas individuales a los distintos perfiles de stakeholders identificados en la Primera Etapa:

- **Ana (Head de Entrenadores)** y 2-3 entrenadores externos, para entender cómo arman rutinas hoy (Excel, WhatsApp) y qué necesitan de un panel de control.
- **Enzo (usuario activo)** y 3-4 usuarios nuevos, para relevar el miedo a lesionarse, la falta de motivación y qué esperan del onboarding.
- **Gabriel (Product Manager)** y **Diego (CTO)**, para confirmar restricciones de negocio (conversión, churn) y técnicas (APK < 200MB, uptime 99,5%).

Cada entrevista se guía con una lista de preguntas abiertas ("Contame cómo armás hoy la rutina de un alumno a distancia"), dejando lugar a repreguntas según lo que surja. Se graban (con consentimiento) y se transcriben para extraer requisitos candidatos.

**¿Qué información permitiría obtener?**

- Motivaciones y frustraciones reales de entrenadores y usuarios, con ejemplos concretos.
- Detalles del flujo actual de trabajo (cómo siguen el progreso de un alumno, cómo cobran, cómo entrenan solos) que no aparecen en un documento de enunciado.
- Prioridades y matices que permiten refinar los criterios de aceptación de las historias de usuario.

**Dificultad**

Los entrenadores tienen agendas muy ajustadas (dan clases, atienden alumnos) y coordinar horarios para la entrevista es difícil; además, al ser una técnica 1 a 1, la cantidad de personas que se puede entrevistar es limitada y el resultado puede sesgarse hacia la opinión de quienes sí tuvieron tiempo de participar (sesgo de disponibilidad).

---

## Técnica 2: Encuestas / Cuestionarios

**Descripción del proceso — ¿Cómo se aplicaría en FitConnect?**

Se diseñaría un cuestionario online (Google Forms o Typeform) de 10-15 preguntas cerradas (escala Likert, opción múltiple) más 1-2 abiertas, distribuido a:

- Usuarios de la comunidad de calistenia y redes sociales de fitness, para medir cuánta gente sufre el problema de "no tener plata/tiempo para el gimnasio".
- Entrenadores freelance, para cuantificar cuántos usan hoy herramientas informales (Excel/WhatsApp) y cuánto pagarían/qué comisión aceptarían.

Preguntas ejemplo: "¿Cuántas veces abandonaste una rutina de entrenamiento por miedo a lastimarte?", "¿Pagarías una suscripción premium si incluye seguimiento de un entrenador real?".

**¿Qué información permitiría obtener?**

- Datos cuantitativos (porcentajes, promedios) que permiten priorizar problemas por volumen de gente afectada, validando el orden de impacto definido en la Primera Etapa (captar → retener → organizar).
- Segmentación de usuarios (principiantes vs. avanzados) útil para definir criterios de aceptación de las historias de usuario relacionadas con onboarding y progresión.

**Dificultad**

Las respuestas cerradas no permiten indagar el "por qué" detrás de una opinión, y suele haber una tasa de respuesta baja o sesgada (solo contestan quienes ya están interesados en fitness/apps), lo que puede dar una imagen poco representativa del usuario promedio que FitConnect quiere captar.
