# 7. Atributos de Calidad (Unidad 3)

## 1. Usabilidad

**Atributo identificado:** Facilidad de aprendizaje y eficiencia de uso en el flujo de onboarding y primer entrenamiento.

**Justificación del enunciado:** el enunciado establece que el registro y la configuración inicial deben completarse en un máximo de "3 taps", y que existe un botón de "hoy 20 minutos" pensado para que el usuario entrene sin tener que armar ni navegar por la app.

**¿Por qué es importante para FitConnect?** Porque el negocio depende de captar usuarios que hoy abandonan el ejercicio por pereza o por menús complicados en otras apps; si el onboarding tiene fricción, se pierde al usuario antes de que pruebe el producto.

---

## 2. Eficiencia (Performance)

**Atributo identificado:** Tiempo de respuesta y throughput de streaming de video.

**Justificación del enunciado:** se exige un tiempo de arranque inicial (cold start) inferior a 3 segundos y una arquitectura de streaming adaptativo (HLS/DASH) sobre CDN para el contenido de video.

**¿Por qué es importante para FitConnect?** Un arranque lento o un video que se corta durante la rutina rompe la experiencia justo en el momento en que el usuario está entrenando, generando frustración y abandono inmediato de la sesión.

---

## 3. Mantenibilidad

**Atributo identificado:** Modularidad del sistema para evolucionar por partes.

**Justificación del enunciado:** el proyecto adopta un modelo de ciclo de vida **incremental** que aísla el flujo de onboarding y da ventanas de tiempo para que el área de arquitectura valide cada incremento antes de expandir el sistema.

**¿Por qué es importante para FitConnect?** Porque las reglas de negocio (comisiones, legal) y de contenido (rutinas, ejercicios) cambian con frecuencia; un sistema modular permite actualizar un componente (por ejemplo, el motor de comisiones) sin re-testear ni re-desplegar toda la aplicación.

---

## 4. Portabilidad

**Atributo identificado:** Peso reducido del instalador y compatibilidad con distintos dispositivos.

**Justificación del enunciado:** se establece que el instalador APK no debe superar los 200MB, lo cual condiciona qué contenido puede vivir localmente en el dispositivo versus qué debe resolverse por streaming remoto.

**¿Por qué es importante para FitConnect?** Gran parte del público objetivo (personas que no pueden pagar un gimnasio) puede tener dispositivos con almacenamiento limitado o conexiones más lentas; una app liviana reduce la barrera de instalación y descarga.

---

## 5. Seguridad

**Atributo identificado:** Confidencialidad e integridad de datos sensibles.

**Justificación del enunciado:** el enunciado exige cumplimiento de GDPR y HIPAA para el tratamiento de datos sensibles (fotografías de progreso premium), con cifrado en tránsito (TLS 1.3) y en reposo (AES-256), y flujos de consentimiento opt-in independientes.

**¿Por qué es importante para FitConnect?** Porque se manejan datos de salud y fotos corporales de los usuarios; una filtración no solo genera daño reputacional sino exposición legal y regulatoria directa para la organización (riesgo señalado explícitamente por Legal en la Primera Etapa).

---

## Otros atributos de calidad críticos no mencionados explícitamente

- **Disponibilidad/Confiabilidad:** más allá del uptime del 99,5% (que en rigor es un requisito no funcional derivado de este atributo), es clave que el sistema tolere fallas parciales —por ejemplo, que un usuario pueda seguir entrenando aunque el servicio de pagos esté caído— dado el diseño de microservicios elegido.
- **Escalabilidad:** la capacidad de sostener picos de uso en horarios de entrenamiento (mañana/noche) sin degradar el servicio, especialmente en el módulo de streaming de video.
- **Interoperabilidad:** la posibilidad de integrar en el futuro wearables o apps de salud externas (Google Fit, Apple Health) para enriquecer el seguimiento de progreso sin rediseñar el sistema.

## ¿Cómo medirían el cumplimiento de estos atributos de calidad?

- **Usabilidad:** pruebas de caja negra cronometrando el flujo de registro (objetivo: ≤ 3 taps y bajo cierto tiempo total), y tests de usuario con nuevos usuarios reales.
- **Performance:** monitoreo automatizado del tiempo de cold start en cada build, y métricas de buffering/latencia del streaming en producción.
- **Mantenibilidad:** métricas de código por servicio (cobertura de tests, tiempo de build/deploy por microservicio) y tiempo promedio para incorporar un cambio menor sin afectar otros servicios.
- **Portabilidad:** verificación automatizada en el pipeline de CI/CD que bloquea el release si el APK supera los 200MB.
- **Seguridad:** auditorías periódicas de cifrado (TLS/AES), pruebas de penetración, y revisión de logs de acceso a datos sensibles conforme a GDPR/HIPAA.
- **Disponibilidad/Escalabilidad:** monitoreo de uptime real vs. objetivo (99,5%) y pruebas de carga simulando picos de uso.
