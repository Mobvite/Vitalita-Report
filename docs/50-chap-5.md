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

### 5.1.3. Source Code Style Guide & Conventions

Todos los nombres utilizados en código, incluyendo archivos, clases, componentes, métodos, variables, servicios y endpoints, se redactarán en **inglés**. El objetivo es mantener consistencia entre los integrantes y facilitar la lectura del código.

#### HTML

- Las etiquetas y atributos se escribirán en minúsculas.
- La estructura deberá utilizar elementos semánticos cuando corresponda (`header`, `nav`, `main`, `section`, `footer`).
- Los atributos se escribirán entre comillas.
- Se evitarán estructuras excesivamente anidadas.
- Se incorporarán atributos ARIA cuando sean necesarios para mejorar la accesibilidad.
- Los nombres de archivos HTML utilizarán minúsculas y `kebab-case`.

#### CSS

- Las clases utilizarán `kebab-case`.
- Se evitarán estilos inline.
- Se organizarán los estilos por secciones o componentes.
- Se priorizará responsive design mediante media queries y unidades relativas.
- Los estilos reutilizables deberán evitar duplicación innecesaria.

Ejemplo:

```css
.feature-card {}
.pricing-section {}
.language-selector {}
```

#### JavaScript

- Variables y funciones utilizarán `camelCase`.
- Clases utilizarán `PascalCase`.
- Se utilizarán `const` y `let` en lugar de `var`.
- Se utilizarán funciones pequeñas y con una responsabilidad clara.
- Se evitará código duplicado.
- Se utilizarán nombres descriptivos en inglés.

Ejemplo:

```javascript
const selectedLanguage = 'en';
function updateNavigation() {}
```

#### Vue 3

- Los componentes utilizarán `PascalCase`.
- Los archivos `.vue` utilizarán nombres descriptivos.
- La lógica reutilizable se separará en composables cuando corresponda.
- Los stores mantendrán responsabilidades específicas.
- La comunicación con el backend se centralizará mediante servicios o un API Client.

Ejemplos:

```text
FamilyDashboard.vue
OlderAdultProfile.vue
SubscriptionPlans.vue
useAuthentication.js
```

#### C# and ASP.NET Core

- Clases, interfaces, métodos y propiedades utilizarán `PascalCase`.
- Variables locales y parámetros utilizarán `camelCase`.
- Las interfaces iniciarán con el prefijo `I`.
- Los campos privados utilizarán `_camelCase`.
- Los métodos asíncronos utilizarán el sufijo `Async`.
- Los Controllers no contendrán lógica de negocio ni accederán directamente al `DbContext`.
- La lógica de negocio permanecerá en las capas Application y Domain.

Ejemplos:

```csharp
public interface IOlderAdultRepository
public class OlderAdultsController
public async Task<OlderAdultDto> GetByIdAsync(...)
```

#### REST API

- Los recursos se nombrarán mediante sustantivos en plural.
- Las rutas utilizarán minúsculas.
- Se utilizarán correctamente los verbos HTTP (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`).
- Las respuestas JSON utilizarán propiedades en `camelCase`.
- Se utilizarán códigos HTTP acordes con el resultado de cada operación.

Ejemplos:

```text
GET /api/older-adults
POST /api/daily-reports
GET /api/subscriptions
```

#### SQL and Database

- Los nombres serán descriptivos y estarán en inglés.
- Cada bounded context mantendrá ownership lógico sobre sus tablas.
- Se definirán explícitamente primary keys, foreign keys y constraints.
- Las migraciones serán gestionadas mediante Entity Framework Core cuando el backend entre al alcance de implementación.

---

### 5.1.4. Software Deployment Configuration

Para AV1, el despliegue se concentra en la primera versión de la **Landing Page**, que será publicada mediante **GitHub Pages**. Este servicio permite desplegar sitios web estáticos directamente desde un repositorio de GitHub.

#### Landing Page Deployment

Procedimiento planificado:

1. Verificar que la versión aprobada de la Landing Page se encuentre integrada en la rama `main`.
2. Acceder al repositorio correspondiente en GitHub.
3. Ingresar a `Settings > Pages`.
4. Configurar la rama y carpeta desde la que se realizará el despliegue.
5. Guardar la configuración y esperar la publicación automática del sitio.
6. Validar la URL pública desde navegadores de escritorio y dispositivos móviles.
7. Comprobar navegación, responsive design, internacionalización y accesibilidad básica.

**Deployment Platform:** GitHub Pages

**Production URL:** `[PENDIENTE DE IMPLEMENTACIÓN]`

Los futuros despliegues de Web Application y Vitalita API serán documentados en los sprints en los que dichos productos ingresen al alcance de implementación.

## 5.2. Landing Page, Services & Applications Implementation

Esta sección registra el avance de implementación de Vitalita por Sprint. Para AV1, el Sprint 1 tiene como principal incremento de producto la primera versión implementada y desplegada de la Landing Page.

### 5.2.1. Sprint 1

El Sprint 1 se enfoca en implementar una Landing Page responsive y accesible que comunique la propuesta de valor de Vitalita a sus dos segmentos objetivo: personas cuidadoras o profesionales de enfermería y familiares de adultos mayores.

La Landing Page debe presentar la solución, sus principales funcionalidades, los planes disponibles, información sobre Mobvite y los call-to-action que posteriormente dirigirán a los usuarios hacia la Web Application.

#### 5.2.1.1. Sprint Planning 1

La reunión de planificación del Sprint 1 se realizó de manera virtual mediante Zoom el 18 de septiembre de 2026 a las 12:00 PM. Durante la sesión, el equipo acordó priorizar las User Stories vinculadas directamente al Landing Page, debido a que este producto forma parte del alcance de implementación y despliegue correspondiente al primer hito del proyecto.

| **Sprint #** | **Sprint 1** |
| --- | --- |
| **Date** | 2026-09-18 |
| **Time** | 12:00 PM |
| **Location** | Reunión virtual mediante Zoom |
| **Prepared By** | Espinoza Lopez, Paul Alejandro Angel |
| **Attendees** | Espinoza Lopez, Paul Alejandro Angel / Navarro Chang, Alicia Avril / Roque Tello, Jack Eddie / Videla Ventura, Jorge Joseph / Yanac Flores, Gabriel Stefano |
| **Sprint 1 Goal** | Our focus is on delivering the first responsive version of the Vitalita Landing Page. We believe it provides caregivers, nurses and family members with a clear understanding of Vitalita's value proposition, main features and available plans. This will be confirmed when visitors can understand the purpose of the product, review its main capabilities and subscription alternatives, and access the registration or login flow from the deployed Landing Page. |
| **Sprint 1 Velocity** | 10 Story Points |
| **Sum of Story Points** | 10 Story Points |

Las User Stories priorizadas para el Sprint 1 son:

| **User Story** | **Título** | **Story Points** | **Estado** |
| --- | --- | ---: | --- |
| US01 | Conocer la propuesta de valor de Vitalita | 3 | Done |
| US02 | Consultar las funcionalidades principales | 3 | Done |
| US03 | Consultar los planes del servicio | 2 | Done |
| US04 | Acceder a la experiencia web de Vitalita | 2 | Done |
| **Total** |  | **10 SP** | **Completed** |

#### 5.2.1.2. Aspect Leaders and Collaborators

Para organizar el trabajo del Sprint 1 se definieron líderes y colaboradores para los principales aspectos de la Landing Page. La asignación permite distribuir responsabilidades sin impedir que los demás integrantes colaboren en revisión, integración y pruebas.

| **Team Member** | **GitHub Username** | **Value Proposition & Hero** | **Features** | **Plans** | **Access & CTA** | **Responsive, i18n & a11y** |
| --- | --- | :---: | :---: | :---: | :---: | :---: |
| Espinoza Lopez, Paul Alejandro Angel | `R3memo` | C | **L** | C | C | C |
| Navarro Chang, Alicia Avril | `Alice-keys` | C | C | **L** | C | C |
| Roque Tello, Jack Eddie | `UPC-Skylar` | **L** | C | C | C | C |
| Videla Ventura, Jorge Joseph | `JorgeVidVen` | C | C | C | **L** | C |
| Yanac Flores, Gabriel Stefano | `u20241d945` | C | C | C | C | **L** |

**L:** Leader  
**C:** Collaborator

#### 5.2.1.3. Sprint Backlog 1

El Sprint Backlog 1 reúne las User Stories y tareas necesarias para implementar la primera versión del Landing Page de Vitalita. Se priorizaron las funcionalidades que permiten comunicar el propósito de la solución, explicar sus principales capacidades, presentar sus planes y proporcionar los accesos hacia el registro e inicio de sesión.

**Trello Board:** https://trello.com/b/DgEMr8w7/vitalita

> **[PENDIENTE DE IMPLEMENTACIÓN: insertar captura actualizada del Sprint 1 en Trello.]**

| **Story ID** | **Story Title** | **Task ID** | **Task Title** | **Task Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| --- | --- | --- | --- | --- | ---: | --- | --- |
| US01 | Conocer la propuesta de valor de Vitalita | T01 | Header & Navigation | Implementar la navegación principal del Landing Page. | 1 | `UPC-Skylar` | Done |
| US01 | Conocer la propuesta de valor de Vitalita | T02 | Hero & Value Proposition | Implementar la sección principal y comunicar claramente el propósito de Vitalita. | 2 | `UPC-Skylar` | Done |
| US01 | Conocer la propuesta de valor de Vitalita | T03 | Target Segments | Presentar el valor de Vitalita para cuidadoras, enfermeras y familiares. | 1 | `R3memo` | Done |
| US02 | Consultar las funcionalidades principales | T04 | Features Section | Implementar la sección con las principales funcionalidades del producto. | 2 | `R3memo` | Done |
| US03 | Consultar los planes del servicio | T05 | Plans Section | Implementar los planes y diferenciar la modalidad freemium de las alternativas de pago. | 2 | `Alice-keys` | Done |
| US04 | Acceder a la experiencia web de Vitalita | T06 | Registration CTA | Implementar el llamado a la acción dirigido al registro de nuevos usuarios. | 1 | `JorgeVidVen` | Done |
| US04 | Acceder a la experiencia web de Vitalita | T07 | Login CTA | Implementar el acceso para usuarios que ya cuentan con una cuenta. | 1 | `JorgeVidVen` | Done |
| US01–US04 | Landing Page Quality | T08 | Responsive Design | Verificar la correcta visualización en desktop y dispositivos móviles. | 2 | `u20241d945` | Done |
| US01–US04 | Landing Page Quality | T09 | Internationalization | Incorporar soporte para los idiomas definidos para la experiencia web. | 2 | `u20241d945` | Done |
| US01–US04 | Landing Page Quality | T10 | Accessibility | Incorporar atributos y ajustes básicos de accesibilidad para la navegación del Landing Page. | 2 | `u20241d945` | Done |
| US01–US04 | Landing Page Deployment | T11 | GitHub Pages Deployment | Configurar y publicar la primera versión del Landing Page mediante GitHub Pages. | 1 | `Alice-keys` | Done |

Las cuatro User Stories comprometidas para el Sprint 1 se consideran completadas debido a que sus criterios correspondientes fueron cubiertos en la primera versión del Landing Page. Las evidencias visuales, commits y URL de despliegue se documentan en las siguientes secciones del Sprint Review.
