# FitConnect – Trabajo Práctico Primera Etapa

---

## Punto 1 – Conocimientos Aplicados

### Conocimiento Científico: Fisiología del Ejercicio

- **Obtención:** Se obtuvo mediante la búsqueda de información en libros, artículos especializados y consultas a profesionales del deporte y la nutrición.
- **Etapas del proceso:** Definición y Desarrollo.
- **Beneficio:** Gracias a este conocimiento, la aplicación puede ofrecer rutinas más seguras y adaptadas a cada usuario, mejorando la efectividad de los entrenamientos y generando mayor confianza en FitConnect.

---

### Conocimiento Científico: Psicología de la Motivación

- **Obtención:** Se obtuvo investigando sobre comportamiento de los usuarios y técnicas de motivación utilizadas en aplicaciones y plataformas digitales.
- **Etapas del proceso:** Definición y Diseño.
- **Beneficio:** Permite crear sistemas de recompensas, desafíos y objetivos que ayudan a que los usuarios mantengan la constancia y se sientan más motivados a seguir entrenando.

---

### Conocimiento Técnico: Arquitectura de Microservicios

- **Obtención:** Este conocimiento se obtuvo a través de cursos relacionados con ingeniería de software, investigación sobre servicios en la nube y práctica en el desarrollo de aplicaciones.
- **Etapas del proceso:** Definición y Desarrollo.
- **Beneficio:** Permite organizar la plataforma en distintos servicios independientes, logrando que el sistema sea más estable y pueda soportar una gran cantidad de usuarios conectados al mismo tiempo sin presentar fallas.

---

### Conocimiento Técnico: Seguridad de la Información

- **Obtención:** Se obtuvo mediante capacitaciones en ciberseguridad y el estudio de normas de protección de datos y privacidad.
- **Etapas del proceso:** Desarrollo y Prueba.
- **Beneficio:** Ayuda a proteger la información personal y los datos de salud de los usuarios, asegurando que estén resguardados correctamente y evitando problemas legales o pérdida de confianza en la plataforma.

---

## Punto 2 – Identificación de Problemas

### Problema 1: Lo caro y complicado que es empezar a entrenar de forma normal

- **¿A quién afecta?** A las personas que quieren arrancar una rutina de ejercicio pero los frenan las membresías caras de los gimnasios, no tener máquinas o directamente no saber por dónde empezar.
- **¿Cómo FitConnect resuelve este problema?** Se enfoca en la calistenia, que se puede practicar en cualquier lado y sin gastar en equipamiento. Aparte, gracias a su modelo freemium, ofrece una versión gratuita con programas básicos, eliminando completamente la barrera económica.
- **Nivel de impacto/importancia:** 1 (más importante).

---

### Problema 2: El límite de alcance que tienen los profes para conseguir clientes

- **¿A quién afecta?** A los entrenadores personales que se ven limitados a dar clases solo en el espacio físico de su gimnasio local y buscan llegar a más alumnos.
- **¿Cómo FitConnect resuelve este problema?** La app les da un espacio a los profes para ofrecer clases virtuales y rutinas personalizadas. También pueden poner sus propios precios, dándoles herramientas para diseñar rutinas y elegir cuánto cobrar.
- **Nivel de impacto/importancia:** 2.

---

### Problema 3: Estancarse y perder la motivación cuando se entrena por cuenta propia

- **¿A quién afecta?** A los usuarios que entrenan solos, que muchas veces no saben cómo medir si están mejorando o terminan abandonando por aburrimiento.
- **¿Cómo FitConnect resuelve este problema?** También tiene gráficos y seguimiento del progreso para que el usuario vea si está mejorando y no pierda la motivación. Además, suma grupos temáticos y retos entre usuarios para que no pierdan la motivación.
- **Nivel de impacto/importancia:** 3 (menos importante).

---

### ¿Por qué este orden y criterio?

El criterio se basa en la Etapa 0 del Proceso Ingenieril (Identificación del Problema), que nos dice que hay que enfocarse primero en el dolor principal para que el proyecto valga la pena. El Nivel 1 es la idea principal de la aplicación (la demanda de los usuarios). El Nivel 2 es importante para que la app funcione bien (la oferta de los entrenadores). Por último, el Nivel 3 (gráficos y seguimiento) queda al final porque es una función para retener al usuario, pero solo sirve si primero logramos resolver sus barreras de acceso.

---

## Punto 3 – Modelos de Proceso

### Comparación de los Modelos de Proceso para FitConnect

#### Modelo Cascada

* Permite organizar y documentar todos los requisitos desde el inicio del proyecto.
* Facilita la planificación porque cada etapa se realiza una sola vez y en un orden definido.
* Como desventaja, es difícil realizar cambios cuando el desarrollo ya está avanzado.
* No resulta conveniente para FitConnect porque las necesidades de los usuarios pueden cambiar a medida que la aplicación se prueba y mejora.

#### Modelo en V

* Incluye verificaciones y pruebas en cada etapa del desarrollo.
* Ayuda a garantizar que funciones importantes, como los pagos y el seguimiento del progreso, funcionen correctamente.
* Su principal desventaja es que los cambios pueden ser costosos y requerir volver a etapas anteriores.
* Puede resultar poco flexible para un proyecto que necesita adaptarse constantemente a los usuarios.

#### Modelo Incremental

* Permite desarrollar la aplicación por partes.
* Se puede lanzar una versión básica con algunas funciones y agregar nuevas características más adelante.
* Ayuda a que los usuarios comiencen a utilizar el producto antes de que esté completamente terminado.
* Si las primeras decisiones de diseño no son adecuadas, agregar nuevas funciones puede volverse más complicado.

#### Modelo Iterativo

* Permite mejorar continuamente el producto a partir de la experiencia de los usuarios.
* Cada nueva versión incorpora correcciones y mejoras.
* Favorece la adaptación a nuevas necesidades o sugerencias.
* Requiere una buena organización para evitar dedicar demasiado tiempo a cambios poco importantes.

#### Modelo de Prototipos

* Permite mostrar versiones preliminares de la aplicación antes de desarrollar el producto final.
* Ayuda a conocer la opinión de los usuarios y validar ideas.
* Reduce el riesgo de desarrollar funciones que luego no sean útiles.
* Como desventaja, existe el riesgo de utilizar prototipos como producto final sin realizar las mejoras necesarias.

#### Modelo en Espiral

* Se enfoca en identificar y reducir riesgos durante todo el proyecto.
* Es útil para aplicaciones que manejan datos personales y transacciones económicas.
* Permite analizar problemas antes de que generen grandes inconvenientes.
* Requiere más tiempo, planificación y recursos que otros modelos.

#### Modelo Ágil (Scrum)

* Permite trabajar en períodos cortos llamados sprints.
* Facilita la incorporación de cambios y sugerencias de los usuarios.
* Permite entregar nuevas funciones de manera frecuente.
* Favorece la comunicación constante entre el equipo y los interesados en el proyecto.
* Requiere una participación activa de todos los involucrados y una buena organización del equipo.

---

### Modelo Recomendado para FitConnect

Se recomienda utilizar el **Modelo Ágil (Scrum)**, complementado con un enfoque incremental durante las primeras versiones de la plataforma.

#### Justificación

* FitConnect se desarrolla en un mercado dinámico donde las necesidades de los usuarios pueden cambiar rápidamente.
* Los usuarios, entrenadores y responsables de la plataforma pueden brindar opiniones constantes para mejorar el producto.
* Permite lanzar una versión inicial funcional y agregar nuevas características progresivamente.
* Facilita realizar mejoras continuas en el rendimiento y la experiencia de uso.
* El modelo de negocio freemium necesita ser probado y ajustado según la respuesta de los usuarios.

#### Factores que influyeron en la decisión

* La plataforma está dirigida a distintos tipos de usuarios, cada uno con necesidades diferentes.
* Es importante validar constantemente que las funciones ofrecidas realmente aporten valor.
* Se necesita garantizar un buen funcionamiento en distintos dispositivos.
* Deben poder incorporarse cambios relacionados con aspectos legales o de seguridad sin afectar todo el desarrollo.
* La posibilidad de recibir retroalimentación constante favorece la mejora continua del producto.

---

## Punto 4 – Roles en el Equipo de Desarrollo (Versión Final Validada)

Basándonos en las restricciones técnicas y estratégicas de FitConnect, y habiendo validado la estructura con el CTO y el Product Manager, el equipo de desarrollo debe contar con los siguientes roles:

### 1. Líder de Proyecto / Product Manager (PM)

- **Responsabilidades principales:** Ser el nexo con la alta gerencia, traducir los objetivos del negocio (ej. lograr 15.000 usuarios y 200 entrenadores en el MVP) en prioridades claras, y proteger al equipo de distracciones para que se enfoquen en lo importante.
- **¿Por qué es necesario para FitConnect?** Porque garantiza que el producto cumpla su objetivo comercial y se asegure de que todo el equipo entienda la necesidad del usuario (como lograr que el registro sea en menos de 3 pasos). En nuestro caso, este rol lo ocupa Gabriel.

---

### 2. Desarrolladores Especializados (Mobile y Backend)

- **Responsabilidades principales:** Escribir el código, pero divididos por especialidad. Los Mobile Devs se encargan de la aplicación en el celular, y el Backend Dev de la lógica en los servidores.
- **¿Por qué es necesario para FitConnect?** Como nos confirmó el CTO (Diego), desarrolladores genéricos (full-stack) harían que la app sea lenta. Necesitamos especialistas Mobile para lograr que la app pese menos de 200MB y arranque en menos de 3 segundos, y un especialista Backend para la lógica de datos.

---

### 3. Tester / Aseguramiento de Calidad (QA)

- **Responsabilidades principales:** Crear pruebas automatizadas desde el día uno y hacer regresiones constantes para evitar deudas técnicas, probando la app para encontrar fallas.
- **¿Por qué es necesario para FitConnect?** Es vital porque funciones críticas como el módulo de seguimiento de métricas y récords personales no pueden fallar; si fallan, usuarios activos como Enzo abandonan la app al tercer día.

---

### 4. DevOps y SRE (Site Reliability Engineer)

- **Responsabilidades principales:** Automatizar procesos, gestionar la infraestructura en la nube y ser los dueños de las alertas para responder rápido si el sistema se cae.
- **¿Por qué es necesario para FitConnect?** FitConnect exige un 99.5% de tiempo en línea (uptime) y soportar videollamadas entre entrenadores y alumnos. Una sola persona no alcanza, por lo que Diego (CTO/DevOps) necesita estar acompañado de un SRE dedicado exclusivamente a mantener la infraestructura estable.

---

### Respuestas a las preguntas de justificación

**¿Los roles irán rotando durante el proceso de desarrollo de FitConnect o no? Justifica tu respuesta.**
Técnicamente no rotarán, ya que los roles requieren una altísima especialización (un desarrollador Backend no puede rotar a Mobile porque la app se volvería lenta, ni a DevOps por la complejidad técnica). Sin embargo, como nos exigió Gabriel (PM), existe una condición innegociable: aunque los roles técnicos sean fijos, la visión sobre el usuario debe ser compartida. Nadie puede encerrarse exclusivamente en su especialidad (código o servidores) perdiendo de vista qué necesita el usuario final. Todo el equipo debe entender el flujo del cliente.

**¿Quién representa al cliente/stakeholder?**
Al ser un marketplace, FitConnect tiene clientes en ambos extremos de la plataforma, por lo que están representados por dos personas:
- **Por la demanda (los deportistas):** Enzo, el usuario activo. Es la voz del cliente que usará la app para entrenar y asegura que las funciones (como el botón de "20 minutos") realmente sirvan para no entrenar a ciegas.
- **Por la oferta (los profesionales):** Ana, la Head de Entrenadores. Representa a los coaches que pondrán su reputación en la app, asegurando que se construyan herramientas útiles para que no abandonen la plataforma.

**¿Quién representa a la alta gerencia de la empresa que desarrolla FitConnect?**
Este rol lo ocupa Gabriel, el Product Manager. Como él mismo nos confirmó, es su trabajo natural ser el nexo indiscutible con la gerencia, traduciendo las metas comerciales en tareas concretas para el equipo de desarrollo.
