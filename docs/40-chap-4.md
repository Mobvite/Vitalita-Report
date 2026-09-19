## Capítulo IV: Product Design

## 4.1. Style Guidelines.

Un Style Guideline es un conjunto de criterios y lineamientos que permiten mantener uniformidad en la redacción, el diseño y la presentación de documentos, contenidos digitales, proyectos de software y otros productos creativos. A continuación, se presentan las especificaciones y parámetros definidos para mantener una estructura coherente y consistente a lo largo del proyecto .

## 4.1.1. General Style Guidelines.

#### **Brand Overview**

Vitalita es una plataforma web orientada al seguimiento y organización del cuidado de adultos mayores. Su propósito es centralizar información relevante del paciente, permitiendo que el enfermero registre y consulte datos importantes, mientras que los familiares pueden visualizar el estado del adulto mayor de forma clara y ordenada.

La identidad visual de Vitalita busca transmitir cercanía, seguridad y cuidado humano, manteniendo una estética limpia y profesional relacionada con el ámbito de la salud digital.

#### **Brand Name**

El nombre Vitalita se relaciona con el concepto de “vitalidad”, haciendo referencia al bienestar, la salud y el seguimiento constante del adulto mayor. El nombre refuerza la idea de una plataforma enfocada en cuidar y monitorear aspectos importantes de la vida diaria del paciente.

#### **Typography**

La aplicación puede utilizar una tipografía sans serif moderna y legible, adecuada para

interfaces web y contenido médico.

- Inter para textos generales, botones, formularios, etiquetas y contenido informativo.

- Inter Semi Bold / Bold para títulos, encabezados y secciones principales.

Esta elección permite mantener una lectura clara, especialmente en información sensible como signos vitales, notas médicas, resultados y recordatorios.

#### **Colors**

La paleta visual de Vitalita debe estar asociada a salud, confianza y claridad.

|Color|Código HEX|Significado|
|---|---|---|
|Verde teal primario|#0F766E|Salud, confianza y acción principal|
|Verde teal secundario|#14B8A6|Apoyo visual, botones y elementos destacados|
|Verde menta claro|#ECFDF5|Fondo suave, bienestar y tranquilidad|
|Azul informativo|#E0F2FE|Información médica y datos relevantes|
|Naranja|#F97316|Alertas, recordatorios y eventos próximos|
|Blanco|#FFFFFF|Limpieza visual y claridad|
|Gris claro|#F8FAFC|Fondos secundarios y separación de secciones|
|Texto principal|#111827|Lectura principal|
|Texto secundario|#475569|Descripciones y contenido de apoyo|



#### **Visual Style**

El estilo visual de Vitalita se basa en:

- interfaces limpias y ordenadas;

- uso de tarjetas para separar información del paciente;

- colores suaves asociados al cuidado y salud;

- bordes redondeados para generar una sensación amigable;

- jerarquía visual clara para diferenciar datos importantes;

- paneles informativos para signos vitales, notas, exámenes y calendario;

- uso de color naranja para destacar recordatorios o alertas importantes.

## 4.1.2. Web Style Guidelines.

La aplicación web de Vitalita debe estar diseñada bajo una lógica responsive, adaptándose correctamente a escritorio, tablet y dispositivos móviles. La estructura visual debe permitir que el enfermero/cuidador y el familiar encuentren rápidamente la información del paciente.

La interfaz principal considera:

- un menú tipo sandwich con las opciones principales;

- una vista Home con el perfil del paciente;

- visualización de signos vitales como ritmo cardíaco, temperatura y otros datos de salud;

- sección de notas del paciente;

- sección de exámenes médicos y resultados;

- calendario general;

- sección de familiares;

- panel derecho con notificaciones y recordatorios;

- perfil profesional del enfermero/cuidador.

El diseño debe mantener una navegación simple, evitando saturar la pantalla con demasiada información. Debido a que se trata de una aplicación relacionada con salud, la legibilidad y la claridad son más importantes que la decoración visual excesiva.

El enfermero/cuidador puede registrar y gestionar información del paciente, mientras que el familiar tiene una experiencia principalmente de consulta. Por ello, la interfaz debe diferenciar claramente entre acciones editables y contenido solo visualizable.

## 4.2. Information Architecture.

La **Information Architecture** de Vitalita organiza los contenidos y funcionalidades de la aplicación para que cada usuario pueda acceder de manera rápida y comprensible a la información que necesita.

La arquitectura de información se basa en dos perfiles principales:

- **Enfermero/cuidador** : usuario operativo que registra, consulta y organiza información del paciente.

- **Familiar** : usuario de consulta que visualiza la información del adulto mayor, pero no puede modificar datos críticos como el calendario o los recordatorios.

El adulto mayor es el centro de la información, pero no actúa como usuario activo dentro del sistema.

## 4.2.1. Organization Systems.

Vitalita utiliza una organización jerárquica combinada con organización por tareas y roles.

#### **Organización por rol**

#### **Enfermero/cuidador:**

El enfermero tiene asignado un único paciente. Desde la plataforma puede visualizar el perfil del paciente, registrar notas, guardar exámenes médicos o resultados, gestionar el calendario y revisar los familiares asociados.

#### **Familiar:**

El familiar puede visualizar la información del paciente, revisar notas, consultar exámenes y resultados, observar el calendario y ver el perfil profesional del enfermero. Sin embargo, no puede editar el calendario ni agregar recordatorios.

#### **Organización de la aplicación web**

Las secciones principales son:

- **Home** : muestra el perfil del paciente y sus signos de salud.

- **Notas del paciente:** contiene sucesos, medicamentos tomados y observaciones.

- **Exámenes médicos y resultados:** almacena tomografías, exámenes, análisis y resultados médicos.

- **Calendario general:** muestra citas médicas, asistencias y recordatorios.

- **Familiares:** permite visualizar los familiares asociados al paciente.

- **Perfil del enfermero:** muestra nombre, foto, correo, estudios, certificaciones y titulaciones.

## 4.2.2. Labeling Systems.

Los sistemas de etiquetado de Vitalita buscan que la interfaz sea clara, comprensible y fácil de usar para usuarios no técnicos.

#### **1. Etiquetas textuales**

Las etiquetas principales deben ser simples y directas:

- “Home”

- “Notas del paciente”

- “Exámenes médicos y resultados”

- “Calendario general”

- “Familiares”

- “Perfil del enfermero”

- “Agregar recordatorio”

- “Ver resultado”

- “Registrar nota”

#### **2. Etiquetas de encabezado**

Ejemplos de encabezados dentro del sistema:

- Perfil del paciente

- Signos de salud

- Notas recientes

- Exámenes médicos

- Calendario de citas

- Familiares asociados

- Perfil profesional del enfermero

#### **3. Etiquetas icónicas**

Se pueden utilizar íconos relacionados con:

- casa para Home;

- nota o documento para notas del paciente;

- carpeta médica para exámenes y resultados;

- calendario para citas y recordatorios;

- grupo de personas para familiares;

- campana para notificaciones;

- usuario profesional para perfil del enfermero.

#### **4. Tooltips**

Ejemplos de mensajes de ayuda:

- “Información general del paciente”

- “Última nota registrada”

- “Resultado médico almacenado”

- “Cita médica próxima”

- “Solo disponible para visualización”

- “El familiar no puede editar este calendario”

## 4.2.3. SEO Tags and Meta Tags.

| **Etiqueta** | **Contenido** |
|---|---|
| `title` | Vitalita - Seguimiento digital para el cuidado de adultos mayores |
| `description` | Plataforma web para enfermeros, cuidadores y familiares que centraliza signos de salud, notas, exámenes, calendario y recordatorios del adulto mayor. |
| `keywords` | cuidado de adultos mayores, enfermero, cuidador, seguimiento médico, signos vitales, familiares, recordatorios médicos, historial clínico |
| `viewport` | width=device-width, initial-scale=1.0 |
| `author` | Vitalita |
| `copyright` | © 2026 Vitalita |

## 4.2.4. Searching Systems.

El sistema de búsqueda de Vitalita debe permitir localizar información relevante del paciente de manera rápida y ordenada.

#### **Búsqueda por categoría**

Permite filtrar información según el tipo de contenido:

- notas del paciente;

- exámenes médicos;

- resultados;

- citas médicas;

- familiares;

- recordatorios.

#### **Búsqueda por fecha**

Permite ubicar registros según una fecha específica, especialmente en:

- notas diarias;

- citas médicas;

- asistencias médicas;

- resultados almacenados;

- recordatorios.

#### **Búsqueda por palabra clave**

Permite encontrar información usando términos específicos como:

- nombre de medicamento;

- tipo de examen;

- síntoma;

- observación registrada;

- nombre de familiar;

- cita médica.

Debido a que el enfermero tiene un solo paciente asignado, no es necesario implementar una búsqueda de múltiples pacientes dentro del flujo principal.

## 4.2.5. Navigation Systems.

Vitalita cuenta con un sistema de navegación basado en un **menú tipo sandwich** , diseñado para facilitar el acceso a las secciones principales de la plataforma.

Las opciones del menú son:

1. **Home**

2. **Notas del paciente**

3. **Exámenes médicos y resultados**

4. **Calendario general**

5. **Familiares**

Además, la aplicación cuenta con un panel derecho donde se muestran notificaciones y recordatorios importantes.

#### **Navegación del enfermero/cuidador**

El flujo principal del enfermero es:

**Inicio de sesión → Home → Notas del paciente → Exámenes médicos y resultados → Calendario general → Familiares**

El enfermero puede registrar notas, guardar exámenes, agregar citas médicas y crear recordatorios. Sin embargo, solo tiene un paciente asignado, por lo que no puede agregar más pacientes.

#### **Navegación del familiar**

El flujo principal del familiar es:

**Inicio de sesión → Home → Notas del paciente → Exámenes médicos y resultados → Calendario general → Familiares → Perfil del enfermero**

El familiar puede visualizar la información del paciente, consultar notas, revisar exámenes y observar el calendario. Sin embargo, no puede editar el calendario ni agregar recordatorios.

En conclusión, el sistema de navegación de Vitalita está diseñado para diferenciar claramente entre el rol operativo del enfermero y el rol consultivo del familiar, permitiendo una experiencia ordenada, segura y fácil de comprender.

## 4.3 Landing Page UI Design

Esta propuesta de Interfaz de Usuario (UI) para la Landing Page de Vitalita traduce las decisiones estratégicas de negocio y usabilidad en un entorno visual cohesivo, accesible y orientado a la conversión. La arquitectura de información se estructura de forma jerárquica y secuencial para guiarnos progresivamente desde la propuesta de valor principal hasta los puntos de conversión y soporte legal.

El diseño visual adopta una paleta de colores centrada en tonos azules y celestes (código #69A7D6 como color dominante de fondo y gradiente), seleccionados estratégicamente para transmitir serenidad, confianza clínica y seguridad en el entorno de la salud geriátrica. La composición prioriza la escaneabilidad mediante patrones F y Z de lectura, garantizando la reducción de la fricción cognitiva tanto para el personal de salud como para los familiares que acceden a la plataforma.

## 4.3.1 Landing Page Wireframe

En la etapa de wireframing (diseño de baja/media fidelidad) para _Desktop Web Browser_ y _Mobile Web Browser_ , se establecieron las bases estructurales y de comportamiento del sitio:

- **Principios de Diseño y Arquitectura de Información:** Se definió un sistema de cuadrícula ( _grid system_ ) flexible de 12 columnas en Desktop y 4 columnas en Mobile. La navegación superior ( _Navbar_ ) organiza los bloques temáticos de manera jerárquica con enlaces ancla ( _anchor links_ ), permitiendo una exploración fluida. La distribución de bloques prioriza una narrativa lógica: captura de atención en el _Hero Section_ (H1 + CTAs), diferenciación operacional ( _Problema vs. Solución_ ), especialización funcional ( _Módulos de Cuidadoras y Familias_ ), y cierre comercial con precios y FAQ.

- **Diseño Inclusivo y Accesibilidad:** Se planificó una escala tipográfica con jerarquías claras (H1, H2, H3 y cuerpo) manteniendo un tamaño mínimo de fuente de 16px para párrafos, asegurando legibilidad para personas de mayor edad o con fatiga visual. Las áreas de toque ( _touch targets_ ) de los botones se diseñaron con un mínimo de 48px de alto para facilitar la interacción tanto en dispositivos móviles como mediante navegación por teclado o puntero.
## 4.4. Web Applications UX/UI Design.

En esta sección se presenta la propuesta de diseño UX/UI de las aplicaciones web de Vitalita, describiendo la estructura visual, los elementos de interfaz y los patrones de interacción que guían la experiencia de los usuarios.

El diseño está orientado a los dos segmentos principales del sistema: enfermeras o cuidadores de adultos mayores y familiares, priorizando una interacción clara, eficiente y alineada con sus necesidades de seguimiento y cuidado. Asimismo, se asegura la coherencia con los Style Guidelines y la Information Architecture, garantizando una experiencia intuitiva, organizada y consistente en toda la plataforma.

## 4.4.1. Web Applications Wireframes.

![Wireframe Protito 1](../assets/images/figures/Wireframe1-prototipo.png)

![Wireframe Protito 2](../assets/images/figures/Wireframe2-prototipo.png)

![Wireframe Protito 3](../assets/images/figures/Wireframe3-prototipo.png)

![Wireframe Protito 4](../assets/images/figures/Wireframe4-prototipo.png)

![Wireframe Protito 5](../assets/images/figures/Wireframe5-prototipo.png)

## 4.4.2. Web Applications Wireflow Diagrams.


## 4.4.2. Web Applications Mock-ups.
![Mockup Protito 1](../assets/images/figures/Mockup-prototipo1.png)

![Mockup Protito 2](../assets/images/figures/Mockup-prototipo2.png)

![Mockup Protito 3](../assets/images/figures/Mockup-prototipo3.png)

![Mockup Protito 4](../assets/images/figures/Mockup-prototipo4.png)

![Mockup Protito 5](../assets/images/figures/Mockup-prototipo5.png)


## 4.4.3. Web Applications User Flow Diagrams.
## 4.5. Web Applications Prototyping.

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

El diagrama de componentes profundiza en cada contenedor, detallando los módulos internos que lo conforman, sus responsabilidades y la forma en que interactúan entre sí.

#### Vitalita API

La siguiente vista presenta la organización general de **Vitalita API**, donde los componentes se agrupan según los bounded contexts definidos para el dominio de Vitalita.

![Vitalita API Components Overview](../assets/images/diagrams/C3_API_Overview.png)

Cada bounded context mantiene una estructura interna organizada en cuatro capas:

- **Interface:** contiene los controllers encargados de exponer los endpoints REST.
- **Application:** coordina los casos de uso mediante command services y query services.
- **Domain:** contiene los aggregates, entidades y reglas de negocio propias del contexto.
- **Infrastructure:** implementa la persistencia mediante Entity Framework Core y los adaptadores hacia servicios externos.

Esta separación permite mantener responsabilidades claras dentro de la API y evita que los controllers accedan directamente a la base de datos o contengan lógica de negocio.

Los bounded contexts tampoco dependen directamente de los modelos internos de otros contextos. Para las consultas se utilizan **interfaces publicadas**; por ejemplo, Dashboard and Analytics consume `Profile Read Contract` y `Care Read Contract`, mientras que Profiles Management consulta `Plan Entitlement Contract` para verificar si el plan contratado permite registrar otro adulto mayor.

Para las reacciones entre módulos se emplean **eventos de dominio in-process** mediante MediatR. De esta forma, eventos como `AppointmentScheduled` pueden generar un recordatorio y `FamilyAccessInvited` puede iniciar el envío de una invitación, manteniendo desacoplados los contextos involucrados.

#### Web Application

La siguiente vista muestra la estructura interna de la **Web Application**, desarrollada con Vue 3 y responsable de proporcionar la interfaz utilizada por cuidadoras y familiares.

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

## 4.7. Software Object-Oriented Design

### 4.7.1. Class Diagrams

#### Identity and Access Management

![Identity and Access Management Class Diagram](../assets/images/diagrams/class-diagram-1.png)

Este bounded context administra las cuentas y el acceso de los usuarios de Vitalita. `User` actúa como Aggregate Root y concentra las credenciales, rol y estado de la cuenta, mientras que `Email` se representa como un Value Object. Las interfaces `IUserRepository`, `ITokenService` e `IPasswordHasher` abstraen la persistencia, generación de tokens y protección de contraseñas necesarias para el proceso de autenticación.

#### Profiles Management

![Profiles Management Class Diagram](../assets/images/diagrams/class-diagram-2.png)

Este bounded context administra la información de cuidadoras, familiares y adultos mayores. `OlderAdult` representa el perfil principal del paciente, mientras que `FamilyAccess` controla la autorización de los familiares para consultar su información. El modelo permite que una cuidadora gestione varios adultos mayores y que cada adulto mayor pueda tener múltiples familiares autorizados.

#### Service Execution and Monitoring

![Service Execution and Monitoring Class Diagram](../assets/images/diagrams/class-diagram-3.png)

Este bounded context concentra el seguimiento diario del adulto mayor, incluyendo reportes, signos vitales, medicamentos, citas médicas, exámenes y actividades de cuidado. Las entidades representan los principales registros clínicos y operativos, mientras que `ICareRecordRepository` abstrae su persistencia dentro del sistema.

#### Resource and Asset Management

![Resource and Asset Management Class Diagram](../assets/images/diagrams/class-diagram-4.png)

Este bounded context administra los archivos relacionados con el seguimiento clínico de Vitalita, como evidencias fotográficas de exámenes, documentos y reportes de emergencia en PDF. `ClinicalAsset` representa los archivos almacenados, mientras que `ExamEvidence` los vincula con los exámenes y `EmergencyReport` representa los informes generados para situaciones de emergencia.

#### Dashboard and Analytics

![Dashboard and Analytics Class Diagram](../assets/images/diagrams/class-diagram-5.png)

Este bounded context proporciona al familiar autorizado una vista consolidada del seguimiento del adulto mayor. `FamilyDashboard` resume la información más relevante, mientras que `PatientHistory` organiza cronológicamente los registros mediante `HistoryEntry`. La interfaz `IDashboardRepository` abstrae las consultas necesarias para obtener el panel y el historial del paciente.

#### Service Design and Planning

![Service Design and Planning Class Diagram](../assets/images/diagrams/class-diagram-6.png)

Este bounded context administra los recordatorios y notificaciones de Vitalita. `Reminder` representa actividades programadas como citas, medicamentos o terapias, mientras que `Notification` gestiona los avisos enviados a los usuarios ante actualizaciones relevantes. Las interfaces abstraen la persistencia y el mecanismo utilizado para enviar las notificaciones.

#### Subscriptions and Payment Management

![Subscriptions and Payment Management Class Diagram](../assets/images/diagrams/class-diagram-7.png)

Este bounded context administra los planes, suscripciones y pagos de Vitalita. `Plan` define las características de cada modalidad del servicio, `Subscription` representa la contratación realizada por el usuario y `Payment` registra las transacciones asociadas. Las interfaces abstraen la persistencia de las suscripciones y la integración con las pasarelas de pago externas.

## 4.8. Database Design

### 4.8.1. Database Diagrams

#### Identity and Access Management

![Identity and Access Management Database Diagram](../assets/images/diagrams/database-diagram-1.png)

El diseño de base de datos de este bounded context se centra en la tabla `users`, encargada de almacenar las cuentas de los usuarios de Vitalita. La dirección de correo electrónico se mantiene como valor único, mientras que la contraseña se almacena únicamente mediante su hash. Las columnas `role` y `status` restringen los valores permitidos para el tipo de usuario y el estado de la cuenta.

#### Profiles Management

![Profiles Management Database Diagram](../assets/images/diagrams/database-diagram-2.png)

Este bounded context persiste la información de cuidadoras, familiares y adultos mayores. La tabla `older_adults` se relaciona con la cuidadora responsable, mientras que `family_access` permite asociar múltiples familiares autorizados a un adulto mayor y controlar el estado de dicho acceso.

#### Service Execution and Monitoring

![Service Execution and Monitoring Database Diagram](../assets/images/diagrams/database-diagram-3.png)

Este bounded context almacena los principales registros del seguimiento diario del adulto mayor, incluyendo reportes, signos vitales, medicamentos, administraciones, citas, exámenes y actividades de cuidado. Las relaciones permiten asociar los signos vitales con un reporte diario y registrar múltiples administraciones para cada medicamento.

#### Resource and Asset Management

![Resource and Asset Management Database Diagram](../assets/images/diagrams/database-diagram-4.png)

Este bounded context almacena los metadatos de archivos clínicos de Vitalita. `clinical_assets` centraliza la información de los archivos almacenados, `exam_evidence` relaciona evidencias fotográficas con exámenes médicos y `emergency_reports` registra los informes PDF generados para situaciones de emergencia.

#### Dashboard and Analytics

![Dashboard and Analytics Database Diagram](../assets/images/diagrams/database-diagram-5.png)

Este bounded context consolida información proveniente de otros módulos para mostrar al familiar autorizado el estado actual y el historial del adulto mayor. Debido a su naturaleza orientada a consultas, se propone utilizar vistas o proyecciones de lectura en lugar de nuevas tablas que dupliquen la información clínica existente.

#### Service Design and Planning

![Service Design and Planning Database Diagram](../assets/images/diagrams/database-diagram-6.png)

Este bounded context persiste la programación de recordatorios y las notificaciones enviadas a los usuarios. La tabla `reminders` almacena los eventos programados relacionados con citas, medicamentos, terapias u otros registros, mientras que `notifications` registra los mensajes generados y su estado de entrega y lectura.

#### Subscriptions and Payment Management

![Subscriptions and Payment Management Database Diagram](../assets/images/diagrams/database-diagram-7.png)

Este bounded context persiste los planes disponibles, las suscripciones contratadas por los usuarios y los pagos asociados. `plans` define las características y límites de cada modalidad del servicio, `subscriptions` registra la relación entre un usuario y un plan, y `payments` mantiene el historial de transacciones realizadas mediante los diferentes medios de pago contemplados por Vitalita.
