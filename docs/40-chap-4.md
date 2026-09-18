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