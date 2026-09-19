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

### 5.1.2. Source Code Management

El proyecto utiliza **Git** como sistema de control de versiones y **GitHub** como plataforma de alojamiento y colaboración. Los repositorios se encuentran dentro de la organización pública de Mobvite.

**GitHub Organization:** [https://github.com/Mobvite](https://github.com/Mobvite)

> **PENDIENTE:** agregar en esta sección la URL exacta del repo de Landing Page una vez que su estructura definitiva haya sido confirmada.

#### Team GitHub Accounts

| Team Member | GitHub Username |
| --- | --- |
| Espinoza Lopez, Paul Alexandro Angel | `R3memo` |
| Navarro Chang, Alicia Avril | `Alice-keys` |
| Roque Tello, Jack Eddie | `UPC-Skylar` |
| Videla Ventura, Jorge Joseph | `JorgeVidVen` |
| Yanac Flores, Gabriel Stefano | `u20241d945` |

#### GitFlow

Se aplicará **GitFlow** para mantener una separación entre las versiones estables, la integración del trabajo y el desarrollo de nuevas funcionalidades.

**Ramas principales:**

- `main`: contiene las versiones estables y listas para producción.
- `develop`: rama de integración en la que se incorporan las funcionalidades terminadas antes de preparar una versión estable.

**Ramas de soporte:**

- `feature/<feature-name>`: utilizada para desarrollar una nueva funcionalidad a partir de `develop`.
- `release/vX.Y.Z`: utilizada para preparar una nueva versión antes de integrarla en `main`.
- `hotfix/<fix-name>`: utilizada para corregir errores críticos detectados en producción.

Ejemplos:

```text
feature/landing-hero
feature/landing-features
feature/landing-pricing
feature/landing-i18n
release/v0.1.0
hotfix/mobile-navigation
```

#### Semantic Versioning

Las versiones del producto seguirán **Semantic Versioning 2.0.0** mediante el formato:

```text
MAJOR.MINOR.PATCH
```

- **MAJOR:** cambios incompatibles con versiones anteriores.
- **MINOR:** incorporación de funcionalidades compatibles.
- **PATCH:** correcciones y ajustes menores.

#### Conventional Commits

Los mensajes de commit seguirán **Conventional Commits**, utilizando descripciones breves en inglés que permitan identificar fácilmente el propósito de cada cambio.

Formato:

```text
<type>(<scope>): <description>
```

Tipos principales:

- `feat`: incorporación de una nueva funcionalidad.
- `fix`: corrección de un error.
- `docs`: cambios en documentación.
- `style`: cambios de formato que no modifican la lógica.
- `refactor`: reestructuración interna del código.
- `test`: incorporación o modificación de pruebas.
- `chore`: tareas de mantenimiento o configuración.

Ejemplos:

```text
feat(landing): add responsive hero section
feat(landing): add language selector
fix(landing): correct mobile navigation
docs(report): add sprint 1 planning
chore(deploy): configure github pages
```

---