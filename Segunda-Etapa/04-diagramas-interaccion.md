# 4. Diagramas de Interacción (Unidad 5)

Se optó por **Diagramas de Secuencia** para los tres casos de uso, ya que la temporalidad y el orden de los mensajes son especialmente relevantes en estos flujos (validaciones, alertas y notificaciones dependen del orden en que ocurren los eventos).

---

## Secuencia CU-01: Registrar usuario y completar onboarding

**Participantes:** Usuario, App (cliente), API Gateway, Servicio de Autenticación, Servicio Legal, Base de Datos

```mermaid
sequenceDiagram
    actor U as Usuario
    participant App
    participant GW as API Gateway
    participant Auth as Servicio Autenticación
    participant Legal as Servicio Legal
    participant DB as Base de Datos

    U->>App: Completa email, contraseña, objetivo y nivel
    App->>GW: POST /registro
    GW->>Auth: Validar y crear credenciales
    Auth->>DB: Verificar si el email ya existe
    DB-->>Auth: Email disponible
    Auth->>DB: Guardar usuario (modo freemium)
    DB-->>Auth: OK
    Auth-->>GW: Usuario creado
    GW->>Legal: Registrar aceptación de Términos
    Legal->>DB: Guardar consentimiento legal
    DB-->>Legal: OK
    Legal-->>GW: Consentimiento registrado
    GW-->>App: Registro exitoso + token de sesión
    App-->>U: Muestra pantalla principal con "Hoy 20 minutos" habilitado
```

---

## Secuencia CU-02: Registrar sesión de entrenamiento con prevención de lesiones

**Participantes:** Usuario, App (cliente), API Gateway, Servicio de Entrenamiento, Módulo de Alertas, Base de Datos

```mermaid
sequenceDiagram
    actor U as Usuario
    participant App
    participant GW as API Gateway
    participant Entr as Servicio de Entrenamiento
    participant Alert as Módulo de Alertas
    participant DB as Base de Datos

    U->>App: Toca "+1 repetición" por cada serie
    App->>App: Acumula repeticiones localmente
    U->>App: Finaliza rutina y reporta esfuerzo percibido
    App->>GW: POST /sesiones {repeticiones, esfuerzo}
    GW->>Entr: Procesar sesión
    Entr->>DB: Guardar sesión de entrenamiento
    DB-->>Entr: OK
    Entr->>Alert: Evaluar nivel de esfuerzo
    alt Esfuerzo por encima del umbral
        Alert-->>Entr: Alerta de sobreentrenamiento
        Entr-->>GW: Sesión guardada + alerta
        GW-->>App: Sesión guardada + alerta
        App-->>U: Muestra aviso de descanso sugerido
    else Esfuerzo dentro del rango seguro
        Alert-->>Entr: Sin alerta
        Entr-->>GW: Sesión guardada
        GW-->>App: Sesión guardada
        App-->>U: Actualiza gráfico de progreso mensual
    end
```

---

## Secuencia CU-03: Gestionar rutina de alumno desde panel de entrenador

**Participantes:** Entrenador, Panel Web/App, API Gateway, Servicio de Rutinas, Servicio de Notificaciones, Base de Datos, App del Alumno

```mermaid
sequenceDiagram
    actor E as Entrenador
    participant Panel as Panel del Entrenador
    participant GW as API Gateway
    participant Rut as Servicio de Rutinas
    participant Notif as Servicio de Notificaciones
    participant DB as Base de Datos
    participant AppAl as App del Alumno

    E->>Panel: Selecciona alumno y ve su progreso
    Panel->>GW: GET /alumnos/{id}/progreso
    GW->>Rut: Solicitar historial del alumno
    Rut->>DB: Consultar sesiones e historial
    DB-->>Rut: Datos de progreso
    Rut-->>GW: Progreso del alumno
    GW-->>Panel: Progreso del alumno
    Panel-->>E: Muestra progreso

    E->>Panel: Edita/duplica plantilla y ajusta cargas
    Panel->>GW: PUT /rutinas/{id}
    GW->>Rut: Validar suscripción activa del alumno
    Rut->>DB: Verificar estado de suscripción
    DB-->>Rut: Suscripción activa
    Rut->>DB: Guardar rutina actualizada
    DB-->>Rut: OK
    Rut->>Notif: Notificar actualización de rutina
    Notif->>AppAl: Push "Tu rutina fue actualizada"
    Rut-->>GW: Rutina actualizada
    GW-->>Panel: Confirmación
    Panel-->>E: Muestra cambios guardados
```
