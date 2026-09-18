## 4.6. Domain-Driven Software Architecture

En esta sección se presenta el modelado del dominio de Vitalita y la representación de su arquitectura de software aplicando C4 Model. El punto de partida es el Big Picture EventStorming del capítulo II, sobre el cual se profundiza hasta identificar bounded contexts, aggregates, commands, policies y read models.

### 4.6.1. Design-Level EventStorming

Se utilizó la guía de Philippe Bourgau, proporcionada en la rúbrica del Final Project Statement, para llevar a cabo el proceso de Design-Level EventStorming con el objetivo de identificar los Bounded Contexts, siguiendo sus etapas:

- Unstructured Exploration
- Timelines
- Pain Points
- Pivotal Points
- Commands
- Policies
- Read Models
- External Systems
- Aggregates
- Bounded Contexts

> **PENDIENTE DE IMPLEMENTACIÓN:** 

Como resultado se identificaron siete bounded contexts, cuya nomenclatura corresponde a los sub-dominios habituales de una plataforma SaaS orientada a negocios de servicio:

| **Bounded Context** | **Tipo** | **Responsabilidad** | **User Stories** |
| --- | --- | --- | --- |
| Identity and Access Management | Supporting | Cuentas, autenticación y autorización por rol. | US05, US06 |
| Profiles Management | Supporting | Perfiles de cuidadoras y familiares, adultos mayores y accesos familiares. | US07–US12 |
| Service Execution and Monitoring | **Core** | Reportes diarios, signos vitales, medicación, citas, exámenes y actividades. | US13–US18, US20, US21 |
| Resource and Asset Management | Supporting | Evidencias fotográficas, documentos clínicos y reportes de emergencia. | US19, US26 |
| Dashboard and Analytics | **Core** | Panel consolidado e historial cronológico para el familiar. | US22, US23, US27 |
| Service Design and Planning | Generic | Recordatorios y notificaciones del cuidado. | US24, US25 |
| Subscriptions and Payment Management | Supporting | Planes, límites, suscripciones y pagos. | US28, US29, US30 |

Service Execution and Monitoring y Dashboard and Analytics son los contextos core porque concentran la propuesta de valor: registrar el cuidado y hacerlo visible para la familia. El sub-dominio *Loyalty and Engagement* quedó fuera del alcance del MVP.

Las User Stories US01–US04 corresponden al Landing Page, que no constituye un bounded context sino un producto de presentación del modelo de negocio.

### 4.6.2. Software Architecture Context Diagram

El diagrama de contexto presenta una visión de alto nivel del sistema Vitalita, mostrando su interacción con los dos segmentos objetivo y los servicios externos con los que se integra, sin entrar en detalles técnicos internos.

![Software Architecture Context Diagram](../assets/images/diagrams/C3_context-diagram.png)

La cuidadora alimenta el sistema y gestiona su suscripción; el familiar consulta el seguimiento y recibe avisos. Hacia afuera, Vitalita se integra con cuatro servicios externos: **Niubiz** como pasarela de pagos, por su cobertura de tarjetas y billeteras digitales en el mercado peruano; **Twilio** para notificaciones por SMS y WhatsApp; **SendGrid** para el correo transaccional; y **Amazon S3** para almacenar evidencias y reportes. Cada uno se consume mediante un adaptador, de modo que sustituirlo por una alternativa evaluada (Culqi o Izipay, Firebase Cloud Messaging, Azure Blob Storage) no afectaría al modelo de dominio.

### 4.6.3. Software Architecture Container Diagrams

El diagrama de contenedores descompone el sistema en sus unidades de despliegue independientes, mostrando cómo se distribuyen las responsabilidades, las tecnologías empleadas y la forma en que se comunican entre sí.

![Software Architecture Container Diagram](../assets/images/diagrams/C3_containers_diagram.png)

| **Container** | **Tecnología** | **Responsabilidad** |
| --- | --- | --- |
| Landing Page | HTML5, CSS3, JavaScript | Presenta el modelo de negocio y redirige a la aplicación. |
| Web Application | Vue 3, PrimeVue, Axios | Interfaz de cuidadoras y familiares. |
| Vitalita API | ASP.NET Core 10, EF Core, MediatR | Lógica de dominio y servicios RESTful. |
| Database | MySQL 8.4 LTS | Persistencia de la solución. |

La Web Application nunca accede a la base de datos: toda comunicación ocurre mediante JSON sobre HTTPS con autenticación por token JWT. La API persiste con Entity Framework Core y encapsula cada proveedor externo en un adaptador.

La API se implementa como **monolito modular**: los siete bounded contexts residen en un mismo proceso desplegable, pero mantienen fronteras estrictas a nivel de código. El alcance del proyecto define un RESTful API de elaboración interna, y la arquitectura orientada a servicios se cumple con la separación entre frontend y backend, no con fragmentar el backend en múltiples procesos. Un bounded context es una frontera del modelo, no del despliegue, por lo que esta decisión es consistente con Domain-Driven Design y permite extraer cualquier contexto como servicio independiente más adelante.
