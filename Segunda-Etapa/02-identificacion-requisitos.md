# 2. Identificación de Requisitos (Unidad 4)

## a) Requisitos Funcionales (Historias de Usuario)

### RF-01 — Onboarding rápido y freemium

**Como** usuario nuevo
**Quiero** registrarme y configurar mi perfil de entrenamiento en pocos pasos
**Para** empezar a entrenar sin fricción y sin necesidad de pagar

**Criterios de aceptación:**
- El registro completo (datos básicos + aceptación de términos legales) se realiza en un máximo de 3 taps.
- El usuario puede acceder al modo gratuito (freemium) sin ingresar datos de pago.
- Al finalizar el registro, el usuario queda habilitado para usar el modo "Hoy 20 minutos".

### RF-02 — Rutina instantánea ("Hoy 20 minutos")

**Como** usuario que quiere empezar a entrenar ya
**Quiero** tocar un botón y recibir una rutina corta armada automáticamente
**Para** entrenar sin tener que diseñar ni buscar ejercicios en la app

**Criterios de aceptación:**
- El botón "Hoy 20 minutos" está visible en la pantalla principal.
- Al presionarlo, el sistema genera una rutina de calistenia de ~20 minutos acorde al nivel del usuario.
- El usuario puede iniciar la rutina generada sin pasos intermedios adicionales.

### RF-03 — Registro de entrenamiento con prevención de lesiones

**Como** usuario que entrena solo
**Quiero** registrar mis repeticiones con un contador manual y reportar cómo me sentí
**Para** llevar un control simple de mi esfuerzo y evitar lesionarme por sobreentrenar

**Criterios de aceptación:**
- Cada ejercicio muestra un botón para sumar una repetición por toque, sin usar cámara.
- Al finalizar la rutina, el sistema solicita un reporte rápido de esfuerzo percibido (escala simple).
- Si el esfuerzo reportado supera el umbral seguro, el sistema muestra una alerta de posible sobreentrenamiento.

### RF-04 — Visualización de progreso mensual

**Como** usuario activo
**Quiero** ver un gráfico de mi evolución mes a mes
**Para** mantenerme motivado al notar avances reales

**Criterios de aceptación:**
- El sistema muestra un gráfico con repeticiones/series completadas por mes.
- El usuario puede filtrar el progreso por tipo de ejercicio.
- El gráfico se actualiza automáticamente tras cada sesión registrada.

### RF-05 — Panel de gestión de rutinas para entrenadores

**Como** entrenador
**Quiero** crear, duplicar y asignar plantillas de rutinas a mis alumnos, y ver su progreso
**Para** trabajar de forma organizada sin depender de Excel o WhatsApp

**Criterios de aceptación:**
- El entrenador puede crear una plantilla de rutina y duplicarla para reutilizarla con otros alumnos.
- El entrenador puede ver el progreso individual de cada alumno asignado y ajustar cargas/repeticiones desde la misma pantalla.
- Los cambios que el entrenador guarda se reflejan de inmediato en la app del alumno.

### RF-06 — Monetización y calificación de entrenadores

**Como** entrenador
**Quiero** cobrar una comisión por mis alumnos premium y recibir calificaciones
**Para** generar ingresos y construir mi reputación dentro de la plataforma

**Criterios de aceptación:**
- El sistema calcula automáticamente la comisión (20%-30%) sobre cada suscripción premium asociada al entrenador.
- Al finalizar un ciclo de entrenamiento, el alumno puede calificar al entrenador (rating).
- El puntaje promedio del entrenador es visible en su perfil público.

---

## b) Requisitos No Funcionales — Calidad (mínimo 3)

1. **Usabilidad:** el flujo crítico de registro e inicio de la primera rutina debe completarse en un máximo de 3 taps, medido mediante pruebas de caja negra.
2. **Performance (eficiencia):** el tiempo de arranque en frío de la aplicación no debe superar los 3 segundos, y el streaming de video de rutinas debe entregarse mediante protocolos adaptativos (HLS/DASH) para evitar cortes según la conexión del usuario.
3. **Seguridad:** toda la información sensible (datos personales, fotos de progreso premium) debe cifrarse en tránsito con TLS 1.3 y en reposo con AES-256, con consentimiento explícito (opt-in) para el uso de fotos.
4. **Disponibilidad:** el sistema debe garantizar un uptime igual o superior al 99,5%, dado que interrumpir el servicio afecta directamente la retención de usuarios y entrenadores.

---

## c) Restricciones (mínimo 2)

1. **Restricción técnica:** el instalador (APK) no puede superar los 200MB, lo que condiciona el uso de assets pesados (videos embebidos, imágenes sin comprimir) y obliga a resolver el contenido audiovisual vía streaming CDN en lugar de archivos locales.
2. **Restricción legal:** el tratamiento de datos de salud y fotos de progreso debe cumplir las normativas GDPR y HIPAA, lo que implica flujos de consentimiento explícito, cifrado obligatorio y limitación en la retención de datos sensibles.
3. **Restricción de negocio:** el onboarding completo (registro + aceptación legal) no puede exceder los 3 taps, ya que Producto definió esa métrica como no negociable para minimizar el abandono temprano (churn).

---

## d) Requerimiento de Negocio (mínimo 1)

**Reducir la deserción temprana (churn) y maximizar la conversión de usuarios freemium a premium**, ofreciendo una barrera de entrada nula (modelo gratuito enfocado en calistenia, sin gimnasio ni equipamiento) y reteniendo tanto a usuarios (mediante seguimiento de progreso y prevención de lesiones) como a entrenadores (mediante un panel de trabajo profesional y un esquema claro de comisiones y reputación), tal como se definió en el análisis de stakeholders de la Primera Etapa.

---

## e) Requisitos Técnicos (mínimo 2)

1. **Arquitectura basada en microservicios con API Gateway**, que permita escalar de forma independiente los módulos críticos (autenticación, rutinas, streaming de video, pagos) sin afectar al resto del sistema.
2. **Streaming adaptativo de contenido audiovisual** mediante los protocolos HLS/DASH, servido desde una CDN, para cumplir el requisito de performance sin incrementar el tamaño del instalador.
3. **Cifrado de extremo a extremo** (TLS 1.3 en tránsito, AES-256 en reposo) para todo dato clasificado como sensible según GDPR/HIPAA.

---

## f) Requisitos de Infraestructura (mínimo 1)

**Infraestructura cloud con auto-escalado horizontal y una red de distribución de contenidos (CDN) global**, necesaria para servir video bajo demanda con baja latencia en distintas regiones y sostener el objetivo de disponibilidad del 99,5% incluso ante picos de uso (por ejemplo, franjas horarias de mayor entrenamiento).
