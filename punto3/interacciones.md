# Interacciones — Punto 3

Resumen ejecutivo
-----------------
En este documento se describen las interacciones, conflictos y decisiones clave entre los stakeholders del proyecto FitConnect (Gabriel, Ana, Diego, Mara). El objetivo es dejar constancia de roles, prioridades para el MVP y reglas mínimas para la planificación del Sprint 1.

1. Roles y responsabilidades
---------------------------
- Gabriel — Product Manager
  - Objetivo principal: captar usuarios rápidamente, reducir el churn y optimizar el onboarding a "3 taps" para maximizar la conversión del MVP.
  - Responsabilidades: priorización del backlog, métricas de adopción, definición de Historias de Usuario de mercado.

- Ana — Head de Entrenadores
  - Objetivo principal: asegurar que los entrenadores dispongan de herramientas para crear y administrar rutinas (drag-and-drop, plantillas) que garanticen calidad de contenido y retención.
  - Responsabilidades: definición de requisitos funcionales para el panel de entrenadores, plantillas, comisiones y workflows de publicación.

- Diego — CTO
  - Objetivo principal: asegurar la viabilidad técnica y el rendimiento (APK < 200MB, arranque < 3s, CDN HLS/DASH con fallback, caché local LRU 50MB, 99.5% uptime objetivo).
  - Responsabilidades: arquitectura, decisiones de infraestructura, pruebas de rendimiento y spikes técnicos.

- Mara — Legal
  - Objetivo principal: garantizar cumplimiento regulatorio (GDPR / HIPAA cuando aplique) y minimizar exposición patrimonial y legal.
  - Responsabilidades: requisitos de consentimiento, manejo de datos sensibles (fotos de progreso), términos y condiciones, políticas de privacidad y revisiones contractuales.

2. Conflictos principales
-------------------------
- Gabriel vs Ana
  - Conflicto: Gabriel prioriza un onboarding ultrarrápido y funcionalidades orientadas al usuario final; Ana exige desde el inicio un panel de entrenadores completo para evitar contenido genérico.
  - Impacto: Sin el mecanismo de creación de plantillas de Ana, existe alto riesgo de churn entre entrenadores (posible abandono del 85% según estimación), lo que dejaría la oferta vacía pese a traer usuarios.

- Gabriel vs Mara
  - Conflicto: Gabriel desea un camino de registro lo más simple posible; Mara exige flujos de consentimiento y revisiones legales que pueden aumentar la fricción en el registro.
  - Impacto: Omisión de requisitos legales puede exponer la empresa a riesgo patrimonial y bloqueo del lanzamiento.

- Diego vs Product (Gabriel/Ana)
  - Conflicto: Los requerimientos de producto (videos embebidos, plantillas pesadas) pueden chocar con las restricciones técnicas de Diego sobre tamaño del instalador, memoria y rendimiento.
  - Impacto: Sin acuerdos técnicos tempranos, hay riesgo de reingeniería costosa y retrasos.

3. Decisiones sugeridas para el MVP / Sprint 1
---------------------------------------------
Priorizar una mezcla de demandas para entregar valor a usuarios y entrenadores sin comprometer cumplimiento legal ni rendimiento.

Sprint 1 (entrega mínima sugerida)
- Objetivos funcionales mínimos:
  1. Onboarding en 3 pasos/taps (Gabriel).
  2. Panel mínimo para entrenadores: creación de rutinas mediante plantillas básicas (no drag-and-drop completo) y publicación limitada (Ana).
  3. Pantallas de consentimiento y Términos y Condiciones en pre-actividad, con checkbox explícito y link a la política (Mara).
  4. Spike técnico liderado por Diego para validar CDN HLS/DASH y fallback ante latencias > 800 ms.
  5. Implementación de límites no negociables: verificación de tamaño de APK y pruebas de arranque.

- Criterios de aceptación (Definition of Done) para Sprint 1:
  - Registro de usuario completo en ≤ 3 taps incluyendo aceptación legal.
  - Entrenadores pueden crear y publicar al menos 1 plantilla de rutina.
  - Resultados iniciales del spike técnico documentados (latencias, viabilidad del fallback).
  - Checklist de privacidad con acciones mitigantes para fotos de progreso (ej.: almacenamiento cifrado, campos opt-in explícitos).

4. Riesgos y mitigaciones
-------------------------
- Riesgo técnico: APK > 200MB o arranque > 3s.
  - Mitigación: aplicar estrategias de lazy-loading, usar CDN para assets, no embebedar videos en el APK, medir tamaño en CI.

- Riesgo de rendimiento: fallos de streaming o alta latencia.
  - Mitigación: Spike para validar streaming adaptativo (HLS/DASH) y fallback (frame estático + descripción); pruebas de estrés en entorno staging.

- Riesgo legal/regulatorio: incumplimiento GDPR/HIPAA por fotos/premium.
  - Mitigación: incluir pantallas de consentimiento separadas, políticas claras, minimizar datos sensibles recolectados en MVP, cifrado en tránsito y reposo, registro de consentimientos.

- Riesgo comercial: abandono de entrenadores (churn de oferta).
  - Mitigación: incluir plantillas básicas en Sprint 1 y plan de incentivos tempranos para entrenadores (beta con beneficios), además de roadmap público de features para entrenadores.

5. Acciones pendientes / responsables
------------------------------------
- Gabriel: definir y escribir las Historias de Usuario de onboarding (Due: Sprint 1 Planning).
- Ana: entregar especificación de 3 plantillas iniciales y criterios de publicación (Due: Sprint 1 Planning).
- Diego: ejecutar spike streaming y entregar informe técnico (Due: fin de Sprint 1 - sugerido: 2 semanas desde inicio).
- Mara: redactar versión inicial de pantallas de consentimiento y checklist legal mínimo (Due: fin de Sprint 1).
- Equipo: añadir en CI una verificación automática del tamaño del APK y pruebas de arranque (Responsable: DevOps / Diego).

6. Notas y recomendaciones adicionales
-------------------------------------
- Reunión recomendada: Sprint 0 (1 semana) para alinear alcance, definir Definition of Done y calendarizar entregables.
- Comunicación: establecer sync diario (15 min) y demo de Sprint semanal para mantener alineación y resolver bloqueos legales o técnicos de forma temprana.
- Roadmap: comunicar públicamente a los entrenadores un roadmap de features para reducir incertidumbre y retener colaboradores.

---

Archivo generado automáticamente por Copilot a partir de los documentos aportados por el equipo y la conversación en la Copilot Space.