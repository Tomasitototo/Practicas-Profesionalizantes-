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

## Punto 4 – Roles en el Equipo de Desarrollo

### Product Owner

- **Responsabilidades principales:** Definir qué va a incluir la app, decidir qué se hace primero, pensar en las necesidades de los usuarios y revisar que el proyecto avance bien.
- **¿Por qué es necesario para FitConnect?** Porque ayuda a que la aplicación tenga funciones útiles para quienes la van a usar.

---

### Coordinador del Proyecto

- **Responsabilidades principales:** Repartir tareas, organizar reuniones, ayudar a resolver problemas y seguir el avance del proyecto.
- **¿Por qué es necesario para FitConnect?** Porque mantiene el trabajo organizado durante el desarrollo.

---

### Desarrollo Visual

- **Responsabilidades principales:** Diseñar pantallas, crear botones, menús y secciones, y hacer que la aplicación se vea clara y ordenada.
- **¿Por qué es necesario para FitConnect?** Porque permite que la app sea fácil de usar y visualmente cómoda.

---

### Desarrollo Interno

- **Responsabilidades principales:** Guardar información, manejar perfiles y registros, organizar los datos y mantener funcionando el sistema.
- **¿Por qué es necesario para FitConnect?** Porque hace posible que la aplicación funcione correctamente.

---

### Diseño y Experiencia de Uso

- **Responsabilidades principales:** Diseñar la apariencia general, pensar cómo se va a mover el usuario dentro de la app y hacer que sea simple y cómoda de usar.
- **¿Por qué es necesario para FitConnect?** Porque mejora la experiencia de uso dentro de la aplicación.

---

### Revisión y Pruebas

- **Responsabilidades principales:** Probar funciones, buscar errores y revisar que todo responda bien.
- **¿Por qué es necesario para FitConnect?** Porque ayuda a detectar fallas antes de que la aplicación llegue al usuario.

---

### Preguntas sobre los roles

**¿Los roles irán rotando durante el proceso de desarrollo de FitConnect?**
No, los roles no irán rotando durante el desarrollo de FitConnect ya que cada integrante mantiene su función principal porque cada rol tiene tareas específicas y eso ayuda a que el trabajo sea más ordenado.

**¿Quién representa al cliente o stakeholder?**
Lo representa el **Product Owner**, ya que es quien se encarga de pensar qué necesita el usuario y transmitir esas necesidades al equipo de desarrollo.

**¿Quién representa a la alta gerencia de la empresa que desarrolla FitConnect?**
Lo representa el **Coordinador del proyecto**, que es quien se ocupa de organizar al equipo, seguir el avance del trabajo y controlar que el proyecto avance correctamente.
