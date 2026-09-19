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