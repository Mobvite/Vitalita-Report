# Capítulo V: Product Implementation, Validation & Deployment

En este capítulo se documenta la configuración del entorno de trabajo, las prácticas de control de versiones, las convenciones de desarrollo y las evidencias de implementación correspondientes al ciclo de construcción de Vitalita. Para AV1, el alcance de implementación se concentra en la primera versión de la Landing Page, mientras que los Web Services y la Web Application serán incorporados progresivamente en los siguientes sprints.

## 5.1. Software Configuration Management

La gestión de configuración de software de Vitalita establece las herramientas, convenciones y prácticas que utilizará el equipo para mantener consistencia durante el desarrollo del producto. Esto incluye el entorno de trabajo, el control de versiones, las convenciones de código y la estrategia de despliegue.

### 5.1.1. Software Development Environment Configuration

El equipo utiliza un conjunto de herramientas especializadas para cubrir las actividades de gestión, diseño, documentación, desarrollo, pruebas y despliegue del proyecto.

#### Project Management

**Trello (SaaS/Application):** herramienta utilizada para planificar y dar seguimiento a las actividades del proyecto mediante un tablero Kanban. En el tablero se organizan las tareas correspondientes a cada Sprint y se registra su avance.

**Trello Board:** [https://trello.com/b/DgEMr8w7/vitalita](https://trello.com/b/DgEMr8w7/vitalita)

**WhatsApp (SaaS/Application):** medio de comunicación utilizado por el equipo para realizar coordinaciones rápidas, resolver dudas y mantener comunicación durante el desarrollo del proyecto.

#### Requirements Management and Documentation

**GitHub (SaaS):** plataforma utilizada para alojar los repositorios del proyecto, gestionar el control de versiones, mantener el Project Report y evidenciar la colaboración de los integrantes mediante commits.

**GitHub Organization:** [https://github.com/Mobvite](https://github.com/Mobvite)

**Markdown:** lenguaje de marcado utilizado para elaborar el Project Report mediante archivos `.md`, facilitando su versionamiento y mantenimiento dentro del repositorio.

#### Product UX/UI Design

**Figma (SaaS/Application):** herramienta utilizada para desarrollar los wireframes, mock-ups y prototipos de la Landing Page y de la Web Application.

**UXPressia (SaaS):** plataforma empleada para elaborar artefactos de UX como User Personas, Empathy Maps, User Journey Maps e Impact Mapping.

**Miro (SaaS):** herramienta colaborativa utilizada para desarrollar los diagramas de Big Picture EventStorming y Design-Level EventStorming.

**Structurizr (SaaS/Application):** herramienta utilizada para modelar la arquitectura de Vitalita mediante C4 Model y Structurizr DSL.

#### Software Development

**WebStorm (Application):** IDE utilizado principalmente para el desarrollo de la Landing Page y la Web Application con HTML, CSS, JavaScript y Vue 3.

**Rider (Application):** IDE utilizado para el desarrollo del backend con C#, ASP.NET Core y Entity Framework Core.

**Git (Application):** sistema de control de versiones distribuido utilizado localmente por cada integrante y sincronizado con los repositorios alojados en GitHub.

**MySQL (Database Management System):** sistema de gestión de base de datos relacional seleccionado para la persistencia de Vitalita.

#### Software Testing

**Google Chrome (Application):** navegador utilizado para realizar pruebas funcionales, responsive design, accesibilidad y validación visual de la Landing Page mediante Chrome DevTools.

En los siguientes sprints, los Web Services serán probados y documentados mediante OpenAPI/Swagger una vez que el backend ingrese al alcance de implementación.

#### Software Deployment

**GitHub Pages (SaaS):** servicio seleccionado para publicar la Landing Page durante AV1 directamente desde el repositorio de GitHub.