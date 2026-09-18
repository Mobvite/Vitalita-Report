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

### 4.6.4. Software Architecture Components Diagrams

El diagrama de componentes profundiza en cada contenedor, detallando los módulos internos que lo conforman y sus interacciones.

![Vitalita API Components Overview](../assets/images/diagrams/C3_API_Overview.png)

Cada bounded context se organiza en cuatro capas, lo que hace el código predecible:

- **Interface:** controladores que exponen los endpoints REST.
- **Application:** command services para las operaciones que modifican estado y query services para las consultas.
- **Domain:** los aggregates con sus reglas de negocio.
- **Infrastructure:** repositorios con EF Core y adaptadores hacia proveedores externos.

Los contextos no se invocan directamente entre sí. Para las consultas se emplean **interfaces publicadas**: Dashboard and Analytics consume Profile Read Contract y Care Read Contract en lugar de conocer el modelo interno de esos contextos, y Profiles Management consulta Plan Entitlement Contract para saber si el plan permite registrar otro adulto mayor, sin acceder al agregado Subscription.

Para las reacciones se emplean **eventos de dominio in-process** mediante MediatR: AppointmentScheduled origina un recordatorio y FamilyAccessInvited origina el envío del correo de invitación, sin que el emisor conozca al receptor.

![Web Application Component Diagram](../assets/images/diagrams/C3_WebApplication.png)

El router controla la navegación y aplica los guards según el rol, apoyándose en el auth store que conserva el token. Las vistas están separadas por dominio y todas consumen la API mediante un único cliente Axios que inyecta el token automáticamente.

#### Bounded Contexts de Vitalita

Cada contexto sigue la misma estructura en cuatro capas, lo que hace el código predecible:

- **Interface:** controladores que exponen los endpoints REST.
- **Application:** command services para las operaciones que modifican estado y query services para las consultas.
- **Domain:** los agregados con sus reglas de negocio, y las políticas donde aplica.
- **Infrastructure:** repositorios con EF Core y adaptadores hacia servicios externos.

#### 1. Component Diagram - Identity and Access Management (IAM)

![Component Diagram - Identity and Access Management](../assets/images/diagrams/C3_Identity.png)

Gestiona el alta de cuentas y la autenticación. El agregado User concentra credenciales, rol y estado; ITokenService e IPasswordHasher abstraen la emisión de tokens y la protección de contraseñas.

#### 2. Component Diagram - Profiles Management

![Component Diagram - Profiles Management](../assets/images/diagrams/C3_Profiles.png)

Administra los perfiles de cuidadoras y familiares, los adultos mayores y la entidad FamilyAccess, que autoriza a un familiar a consultar a un paciente. Publica Profile Read Contract para que otros contextos validen el acceso, y consulta Plan Entitlement Contract antes de permitir registrar un adulto mayor adicional.

#### 3. Component Diagram - Service Execution and Monitoring

![Component Diagram - Service Execution and Monitoring](../assets/images/diagrams/C3_ServiceExecution.png)

Contexto core. Contiene los aggregates DailyReport, Medication, MedicalAppointment y MedicalExam, junto con las entidades VitalSign, MedicationAdministration y CareActivity. Publica Care Read Contract hacia Dashboard and Analytics y Resource and Asset Management.

#### 4. Component Diagram - Resource and Asset Management

![Component Diagram - Resource and Asset Management](../assets/images/diagrams/C3_Assets.png)

Administra los archivos del seguimiento clínico. ClinicalAsset representa el archivo almacenado, ExamEvidence lo vincula con su examen y EmergencyReport registra el documento generado con su estado. IFileStorage abstrae el almacenamiento de objetos.

#### 5. Component Diagram - Dashboard and Analytics

![Component Diagram - Dashboard and Analytics](../assets/images/diagrams/C3_Dashboard.png)

Contexto core. No contiene aggregates propios: `FamilyDashboard` y `PatientHistory` son **read models** que proyectan información ya registrada en otros contextos, obtenida mediante las interfaces publicadas.

#### 6. Component Diagram - Service Design and Planning

![Component Diagram - Service Design and Planning](../assets/images/diagrams/C3_Planning.png)

Programa y despacha recordatorios y notificaciones a partir de los eventos de dominio. El procesador de trabajos en segundo plano (Hangfire) es un componente interno de la API, no un contenedor aparte, porque se ejecuta en el mismo proceso.

#### 7. Component Diagram - Subscription and Payment Management

![Component Diagram - Subscription and Payment Management](../assets/images/diagrams/C3_Subscriptions.png)

Administra el catálogo de planes, las suscripciones y los pagos. El agregado Plan define el límite maxOlderAdults, que conecta la gestión de múltiples pacientes con el plan contratado. Niubiz se aísla mediante IPaymentGateway, que actúa como capa anticorrupción.