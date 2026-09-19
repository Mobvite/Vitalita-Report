# Capítulo V: Product Implementation, Validation & Deployment

En este capítulo se documenta la configuración del entorno de desarrollo, la gestión del código fuente, las convenciones de implementación, el despliegue y las evidencias correspondientes al primer Sprint de Vitalita. Para AV1, el incremento implementado y desplegado corresponde a la primera versión del **Landing Page**.

---

## 5.1. Software Configuration Management

La gestión de configuración de software de Vitalita define las herramientas, convenciones y procedimientos utilizados por el equipo para organizar el trabajo, desarrollar los productos digitales, mantener la trazabilidad de los cambios y desplegar las versiones correspondientes.

### 5.1.1. Software Development Environment Configuration

Las herramientas empleadas por el equipo se organizan de acuerdo con su propósito dentro del proyecto.

#### Project Management

- **Trello (SaaS/Application):** herramienta utilizada para organizar el Product Backlog, Sprint Backlog y las tareas correspondientes a cada integrante mediante un tablero Kanban.  
  **Vitalita Board:** [https://trello.com/b/DgEMr8w7/vitalita](https://trello.com/b/DgEMr8w7/vitalita)

- **Zoom (SaaS/Application):** plataforma utilizada para realizar reuniones virtuales de planificación, coordinación y revisión del avance del equipo.

- **WhatsApp (SaaS/Application):** medio de comunicación utilizado para coordinaciones rápidas, consultas y seguimiento cotidiano entre los integrantes.

#### Product UX/UI Design & Architecture

- **Figma (SaaS/Application):** herramienta colaborativa utilizada para diseñar wireframes, mock-ups y prototipos del Landing Page y de la Web Application.

- **Miro (SaaS/Application):** herramienta utilizada para actividades colaborativas de modelado, incluyendo Big Picture EventStorming y Design-Level EventStorming.

- **Structurizr (SaaS/Application):** herramienta utilizada para documentar la arquitectura de software mediante C4 Model y Structurizr DSL.

#### Software Development

- **WebStorm (Application):** IDE utilizado principalmente para el desarrollo del Landing Page y, posteriormente, de la Web Application basada en Vue 3.

- **Rider (Application):** IDE utilizado para el desarrollo del backend de Vitalita mediante C#, ASP.NET Core y Entity Framework Core.

- **Git (Application):** sistema de control de versiones distribuido utilizado para mantener el historial de cambios del código y la documentación.

- **GitHub (SaaS):** plataforma utilizada para alojar los repositorios de la organización Mobvite, gestionar commits y mantener de forma colaborativa el código y el Project Report.  
  **Organization:** [https://github.com/Mobvite](https://github.com/Mobvite)

#### Database Management

- **MySQL 8.4 LTS:** sistema de gestión de base de datos relacional seleccionado para la persistencia de Vitalita.

- **DataGrip / MySQL Workbench:** herramientas utilizadas para consultar, visualizar y administrar la base de datos durante el desarrollo.

#### Software Testing

- **Google Chrome:** navegador utilizado para validar el comportamiento visual, navegación, responsive design y ejecución del Landing Page.

- **Chrome DevTools:** herramientas utilizadas para inspeccionar HTML/CSS, revisar el diseño responsive, detectar errores de JavaScript y validar recursos cargados por el sitio.

#### Software Documentation

- **Markdown:** formato utilizado para mantener la documentación del proyecto como Docs-as-Code dentro del repositorio `Vitalita-Report`.

- **GitHub:** plataforma utilizada también como repositorio principal de la documentación y de sus assets.

---

### 5.1.2. Source Code Management

Vitalita utiliza **Git** como sistema de control de versiones y **GitHub** como plataforma de alojamiento y colaboración.

**GitHub Organization:** [https://github.com/Mobvite](https://github.com/Mobvite)

**Project Report Repository:** [https://github.com/Mobvite/Vitalita-Report](https://github.com/Mobvite/Vitalita-Report)

**Landing Page Repository:** [https://github.com/Mobvite/langing-page](https://github.com/Mobvite/langing-page)

Para organizar la evolución del producto se adopta **GitFlow** como estrategia de referencia.

#### Main Branches

- `main`: contiene versiones estables e integradas del producto.
- `develop`: rama de integración para funcionalidades desarrolladas durante un Sprint.

#### Supporting Branches

- `feature/<feature-name>`: desarrollo de una nueva funcionalidad o sección.
- `release/vX.Y.Z`: preparación de una versión antes de su publicación.
- `hotfix/<description>`: corrección urgente sobre una versión estable.

Ejemplos:

```text
feature/landing-page-hero
feature/pricing-section
feature/about-team
release/v0.1.0
hotfix/mobile-navigation
```

#### Semantic Versioning

El equipo utiliza Semantic Versioning siguiendo el formato:

```text
MAJOR.MINOR.PATCH
```

- **MAJOR:** cambio incompatible con versiones anteriores.
- **MINOR:** incorporación de nueva funcionalidad compatible.
- **PATCH:** corrección o ajuste menor compatible.

#### Conventional Commits

Para mantener un historial legible y trazable se utilizan mensajes siguiendo Conventional Commits:

```text
<type>(optional-scope): description
```

Tipos principales:

- `feat`: nueva funcionalidad.
- `fix`: corrección de error.
- `docs`: cambios en documentación.
- `style`: cambios de formato sin modificar comportamiento.
- `refactor`: reorganización del código sin agregar funcionalidad.
- `test`: incorporación o modificación de pruebas.
- `chore`: tareas de mantenimiento o configuración.

Ejemplos:

```text
feat: add pricing carousel functionality with navigation
fix: move project files out of the .idea folder to the project root
docs: update readme and trim comments
chore: add members photos
```

---

### 5.1.3. Source Code Style Guide & Conventions

Como convención general, los nombres de clases, componentes, variables, funciones, servicios, entidades y demás elementos técnicos se escriben en **inglés**.

#### HTML

- Uso de HTML5 semántico.
- Etiquetas y atributos en minúsculas.
- Correcto anidamiento de elementos.
- Nombres de archivos en minúsculas y separados mediante guiones cuando corresponda.
- Uso de atributos `alt`, `aria-label`, `aria-expanded` y otros elementos de accesibilidad cuando sean necesarios.
- Evitar estilos inline.
- Mantener una estructura legible y correctamente indentada.

#### CSS

- Uso de `kebab-case` para nombres de clases.
- Uso de CSS Custom Properties para valores reutilizables y design tokens.
- Organización de estilos por secciones o componentes.
- Uso de Flexbox, Grid y Media Queries para responsive design.
- Evitar duplicación innecesaria de reglas.
- Evitar valores excesivamente específicos cuando una regla reutilizable resulte suficiente.

Ejemplo:

```css
.pricing-card {
  display: flex;
  flex-direction: column;
}
```

#### JavaScript

- Uso de `camelCase` para variables y funciones.
- Uso de `PascalCase` para clases cuando corresponda.
- Uso de `const` por defecto y `let` únicamente cuando una variable requiera reasignación.
- No utilizar `var`.
- Separar responsabilidades en funciones pequeñas.
- Utilizar nombres descriptivos en lugar de abreviaturas poco claras.
- Mantener la interacción con el DOM centralizada en los scripts correspondientes.

Ejemplo:

```javascript
const languageToggle = document.querySelector('#lang-toggle');

function updateLanguage(language) {
  // ...
}
```

#### Vue 3

Para la Web Application se seguirán las siguientes convenciones:

- Componentes en `PascalCase`.
- Props y variables JavaScript en `camelCase`.
- Organización por funcionalidades o dominios.
- Uso de Vue Router para navegación.
- Uso de Pinia para estado compartido.
- Consumo de la API mediante un cliente Axios centralizado.
- Evitar lógica de negocio dentro de componentes visuales.

#### C# / ASP.NET Core

- Clases, records, interfaces, métodos públicos y propiedades en `PascalCase`.
- Variables locales y parámetros en `camelCase`.
- Interfaces con prefijo `I`.
- Una responsabilidad principal por clase.
- Controllers sin reglas de negocio y sin acceso directo al `DbContext`.
- Application Services para coordinar casos de uso.
- Domain Layer para reglas e invariantes.
- Infrastructure para persistencia y adaptadores externos.
- Uso de `async/await` para operaciones de I/O.

Ejemplo:

```csharp
public interface IOlderAdultRepository
{
    Task<OlderAdult?> FindByIdAsync(Guid olderAdultId);
}
```

#### REST API

- Recursos expresados mediante sustantivos.
- Uso coherente de verbos HTTP.
- Endpoints en minúsculas.
- Respuestas HTTP acordes al resultado de la operación.
- Intercambio de información en JSON.
- Documentación mediante OpenAPI/Swagger cuando los Web Services ingresen al alcance de implementación.

---

### 5.1.4. Software Deployment Configuration

#### Landing Page

La primera versión del Landing Page de Vitalita se despliega mediante **GitHub Pages**, permitiendo publicar el sitio estático directamente desde el repositorio.

**Repository:** [https://github.com/Mobvite/langing-page](https://github.com/Mobvite/langing-page)

**Deployment URL:** [https://mobvite.github.io/langing-page/](https://mobvite.github.io/langing-page/)

El flujo de despliegue utilizado consiste en:

1. Integrar en `main` la versión aprobada del Landing Page.
2. Acceder a `Settings > Pages` dentro del repositorio.
3. Configurar la fuente utilizada por GitHub Pages.
4. Publicar el sitio.
5. Validar la URL pública.
6. Verificar la carga de HTML, CSS, JavaScript e imágenes.
7. Comprobar la experiencia en desktop y mobile.

![GitHub Pages Configuration](../assets/images/others/github-pages.png)

*Figura X. Configuración de despliegue del Landing Page mediante GitHub Pages.*

Los despliegues correspondientes a la **Web Application** y **Vitalita API** serán documentados en los Sprints en los que dichos productos ingresen al alcance de implementación.

---

## 5.2. Landing Page, Services & Applications Implementation

En esta sección se documenta la implementación progresiva de los productos de Vitalita mediante Sprints. Para AV1, el incremento implementado corresponde al Landing Page, mientras que los Web Services y la Web Application serán incorporados posteriormente.

### 5.2.1. Sprint 1

Durante el Sprint 1, el equipo se enfocó en implementar y desplegar la primera versión del **Landing Page de Vitalita**, priorizando las User Stories US01–US04 del Product Backlog.

Estas historias permiten comunicar la propuesta de valor, presentar las funcionalidades principales, mostrar los planes del servicio y proporcionar los puntos de acceso hacia la experiencia web de Vitalita.

---

#### 5.2.1.1. Sprint Planning 1

La reunión de planificación del Sprint 1 se realizó de manera virtual mediante **Zoom** el **18 de septiembre de 2026 a las 12:00 PM**. Durante la sesión, el equipo acordó priorizar las User Stories vinculadas directamente al Landing Page debido a que este producto constituye el incremento de implementación requerido para AV1.

| **Sprint #** | **Sprint 1** |
| --- | --- |
| **Date** | 2026-09-18 |
| **Time** | 12:00 PM |
| **Location** | Reunión virtual mediante Zoom |
| **Prepared By** | Espinoza Lopez, Paul Alejandro Angel |
| **Attendees** | Espinoza Lopez, Paul Alejandro Angel / Navarro Chang, Alicia Avril / Roque Tello, Jack Eddie / Videla Ventura, Jorge Joseph / Yanac Flores, Gabriel Stefano |
| **Sprint 0 Review Summary** | No aplica. Este es el primer Sprint de implementación del producto. |
| **Sprint 0 Retrospective Summary** | No aplica. Este es el primer Sprint de implementación del producto. |
| **Sprint 1 Goal** | Our focus is on delivering the first responsive version of the Vitalita Landing Page. We believe it provides caregivers, nurses and family members with a clear understanding of Vitalita's value proposition, main features and available plans. This will be confirmed when visitors can understand the purpose of the product, review its main capabilities and subscription alternatives, and access the registration or login entry points from the deployed Landing Page. |
| **Sprint 1 Velocity** | 10 Story Points |
| **Sum of Story Points** | 10 Story Points |

Las User Stories seleccionadas para Sprint 1 corresponden directamente al alcance funcional del Landing Page:

| **User Story** | **Título** | **Story Points** | **Estado** |
| --- | --- | ---: | --- |
| US01 | Conocer la propuesta de valor de Vitalita | 3 | Done |
| US02 | Consultar las funcionalidades principales | 3 | Done |
| US03 | Consultar los planes del servicio | 2 | Done |
| US04 | Acceder a la experiencia web de Vitalita | 2 | Done |
| **Total** |  | **10 SP** | **Completed** |

> **Nota de trazabilidad:** los Story Points registrados en esta sección deben mantenerse iguales a los utilizados en el Product Backlog del Capítulo III.

> **Nota sobre US04:** el Landing Page implementa los puntos de acceso visuales hacia registro e inicio de sesión. La navegación hacia las rutas definitivas de la Web Application será conectada cuando dicha aplicación ingrese al alcance de implementación.

---

#### 5.2.1.2. Aspect Leaders and Collaborators

Para distribuir el trabajo del Sprint se definieron responsables para las principales áreas del Landing Page, manteniendo la posibilidad de colaboración y revisión cruzada entre todos los integrantes.

| **Team Member** | **GitHub Username** | **Base, Hero & Navigation** | **Benefits & Segments** | **Plans** | **About & Team** | **FAQ, Legal & Integration** |
| --- | --- | :---: | :---: | :---: | :---: | :---: |
| Espinoza Lopez, Paul Alejandro Angel | `R3memo` | C | **L** | C | C | C |
| Navarro Chang, Alicia Avril | `Alice-keys` | **L** | C | C | C | **L** |
| Roque Tello, Jack Eddie | `UPC-Skylar` | C | C | C | **L** | C |
| Videla Ventura, Jorge Joseph | `JorgeVidVen` | C | C | C | C | C |
| Yanac Flores, Gabriel Stefano | `u20241d945` | C | C | **L** | C | C |

**L:** Leader  
**C:** Collaborator

La matriz debe mantenerse coherente con las tarjetas de Trello, el Sprint Backlog y las evidencias de commits del equipo.

---

#### 5.2.1.3. Sprint Backlog 1

El Sprint Backlog 1 reúne las tareas necesarias para cumplir las User Stories US01–US04 y publicar la primera versión del Landing Page.

**Trello Board:** [https://trello.com/b/DgEMr8w7/vitalita](https://trello.com/b/DgEMr8w7/vitalita)

![Sprint 1 Trello Board](../assets/images/others/trello.png)

*Figura X. Sprint 1 Board de Vitalita en Trello.*

| **Story ID** | **Story Title** | **Task ID** | **Task Title** | **Task Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| --- | --- | --- | --- | --- | ---: | --- | --- |
| US01 | Conocer la propuesta de valor de Vitalita | T01 | Base structure, Navbar & Hero | Implementar la estructura base, navegación y Hero del Landing Page. | 3 | `Alice-keys` | Done |
| US01 | Conocer la propuesta de valor de Vitalita | T02 | Benefits & Target Segments | Presentar los beneficios de Vitalita para cuidadoras, enfermeras y familiares. | 2 | `R3memo` | Done |
| US02 | Consultar las funcionalidades principales | T03 | Caregiver & Family Features | Implementar las funcionalidades principales dirigidas a ambos segmentos. | 2 | `R3memo` | Done |
| US03 | Consultar los planes del servicio | T04 | Pricing & Plans | Implementar los planes disponibles, métodos de pago mostrados y carrusel de precios. | 3 | `u20241d945` | Done |
| US04 | Acceder a la experiencia web de Vitalita | T05 | Login & Registration CTAs | Implementar los llamados a la acción para login y registro desde el Landing Page. | 1 | `Alice-keys` | Done |
| US01-US04 | Landing Page supporting content | T06 | About & Team | Implementar la presentación de Vitalita, Mobvite y los miembros del equipo. | 2 | `UPC-Skylar` | Done |
| US01-US04 | Landing Page supporting content | T07 | FAQ, Footer & Legal Pages | Implementar FAQ, footer, términos y página de privacidad. | 3 | `Alice-keys` | Done |
| US01-US04 | Landing Page quality | T08 | Responsive & Interactive Behavior | Implementar menú móvil, comportamiento responsive, navegación, carruseles y elementos interactivos. | 2 | `Alice-keys` | Done |
| US01-US04 | Landing Page quality | T09 | Language Toggle & Accessibility | Incorporar selector de idioma, HTML semántico y atributos ARIA básicos. | 2 | `Alice-keys` | Done |
| US01-US04 | Landing Page deployment | T10 | GitHub Pages Deployment | Publicar y validar el Landing Page mediante GitHub Pages. | 1 | Team | Done |

Las cuatro User Stories comprometidas para el Sprint 1 se consideran completadas dentro del alcance definido para la primera versión del Landing Page.

---

#### 5.2.1.4. Development Evidence for Sprint Review

Durante el Sprint 1 se realizaron commits relacionados con la estructura base, navegación, funcionalidades, segmentos objetivo, planes, presentación del equipo, contenido legal e integración final del Landing Page.

**Landing Page Repository:** [https://github.com/Mobvite/langing-page](https://github.com/Mobvite/langing-page)

| **Repository** | **Branch** | **Commit Id** | **Commit Message** | **Committed on (Date)** |
| --- | --- | --- | --- | --- |
| `Mobvite/langing-page` | `main` | `a36e5c9` | `chore: initialize project structure and README` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `2b4d19a` | `feat: add index.html base scaffold (head, navbar, hero, section anchors)` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `63eb48e` | `feat: add base behavior (mobile menu, scrollspy, language toggle, CTAs)` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `f31b9d1` | `feat: add benefits, caregivers, and families sections to index.html` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `6018aff` | `feat: add benefits, caregivers, and families sections styles to styles.css` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `a21dbd0` | `feat: Add pricing section with plans and payment methods` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `a4a3868` | `feat: Add pricing section styles to styles.css` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `ee198d7` | `feat: Add pricing carousel functionality with navigation` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `72901fb` | `feat: add about team section` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `b0a7827` | `chore: add members photos` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `b0790a0` | `feat: add terms and privacy pages` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `6964cc2` | `feat: add faq and footer styles, image and carousel animations` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `de59f89` | `feat: add faq accordion and pricing and team carousels` | 2026-09-18 |
| `Mobvite/langing-page` | `main` | `b44a88c` | `feat: add real images, faq and footer, fix asset paths` | 2026-09-18 |

![Development Evidence - Commits](../assets/images/others/commits.png)

*Figura X. Historial de commits del Landing Page durante Sprint 1.*

---

#### 5.2.1.5. Execution Evidence for Sprint Review

Durante Sprint 1 se obtuvo una primera versión navegable y responsive del Landing Page de Vitalita.

**Deployed Landing Page:** [https://mobvite.github.io/langing-page/](https://mobvite.github.io/langing-page/)

La versión desarrollada presenta la propuesta de valor de Vitalita, los beneficios de la solución, las funcionalidades para cuidadoras y familiares, los planes disponibles, la información de la startup y distintos elementos de navegación e interacción.

Entre las funcionalidades y secciones implementadas se encuentran:

- Navbar y Hero.
- Propuesta de valor.
- Comparación de beneficios.
- Sección para enfermeras y cuidadoras.
- Sección para familiares.
- Planes y precios.
- Carrusel de planes.
- Presentación de Vitalita y Mobvite.
- Presentación de integrantes.
- Testimonios.
- FAQ.
- Footer.
- Términos y privacidad.
- Menú responsive.
- Selector de idioma.
- CTA de registro e inicio de sesión.
- Elementos básicos de accesibilidad.

![Landing Page Evidence 1](../assets/images/others/lpevidencia1.png)

*Figura X. Evidencia de ejecución del Landing Page - vista 1.*

![Landing Page Evidence 2](../assets/images/others/lpevidencia2.png)

*Figura X. Evidencia de ejecución del Landing Page - vista 2.*

![Landing Page Evidence 3](../assets/images/others/lpevidencia3.png)

*Figura X. Evidencia de ejecución del Landing Page - vista 3.*

![Landing Page Evidence 4](../assets/images/others/lpevidencia4.png)

*Figura X. Evidencia de ejecución del Landing Page - vista 4.*

![Landing Page Evidence 5](../assets/images/others/lpevidencia5.png)

*Figura X. Evidencia de ejecución del Landing Page - vista 5.*

---

#### 5.2.1.6. Services Documentation Evidence for Sprint Review

Durante Sprint 1 no se desarrollaron Web Services ni endpoints REST debido a que el alcance de implementación de AV1 se concentró en la primera versión del Landing Page.

Por esta razón, todavía no existen servicios que requieran documentación mediante OpenAPI/Swagger.

La documentación de Web Services será incorporada cuando **Vitalita API** ingrese al alcance de implementación, incluyendo:

- endpoints disponibles;
- verbos HTTP;
- parámetros;
- schemas;
- ejemplos de requests;
- ejemplos de responses;
- códigos de estado;
- evidencia de OpenAPI/Swagger desplegado.

**Sprint 1 Status:** `Not Applicable - Web Services are outside the implementation scope of Sprint 1.`

---

#### 5.2.1.7. Software Deployment Evidence for Sprint Review

La primera versión del Landing Page fue desplegada mediante **GitHub Pages**.

**Platform:** GitHub Pages

**Repository:** [https://github.com/Mobvite/langing-page](https://github.com/Mobvite/langing-page)

**Deployment URL:** [https://mobvite.github.io/langing-page/](https://mobvite.github.io/langing-page/)

El deployment permite acceder públicamente al incremento desarrollado durante Sprint 1 y validar su ejecución fuera del entorno local.

![GitHub Pages Deployment Evidence](../assets/images/others/github-pages.png)

*Figura X. Evidencia de configuración y despliegue mediante GitHub Pages.*

El procedimiento de despliegue aplicado fue:

1. Integrar la versión aprobada en el repositorio.
2. Configurar GitHub Pages.
3. Seleccionar la fuente de publicación.
4. Publicar el sitio.
5. Acceder a la URL pública generada.
6. Validar imágenes, hojas de estilo y scripts.
7. Verificar navegación y comportamiento responsive.

---

#### 5.2.1.8. Team Collaboration Insights during Sprint

Durante Sprint 1 el equipo utilizó GitHub y Trello para distribuir, implementar e integrar las tareas correspondientes al Landing Page.

El historial del repositorio evidencia contribuciones relacionadas con estructura, contenido, estilos, interacción, planes, presentación del equipo y recursos visuales.

| **Team Member** | **GitHub Username / Author** | **Principal evidence during Sprint 1** |
| --- | --- | --- |
| Espinoza Lopez, Paul Alejandro Angel | `R3memo` | Implementación y estilos de las secciones Benefits, Caregivers y Families. |
| Navarro Chang, Alicia Avril | `Alice-keys` / `avril` | Estructura inicial, Hero, navegación, comportamiento responsive, selector de idioma, FAQ, footer, páginas legales, imágenes e integración. |
| Roque Tello, Jack Eddie | `UPC-Skylar` | Sección About/Team y fotografías de los integrantes. |
| Videla Ventura, Jorge Joseph | `JorgeVidVen` | Participación y colaboración en las actividades del Sprint según la asignación del equipo y el tablero de Trello. |
| Yanac Flores, Gabriel Stefano | `u20241d945` | Implementación de la sección Pricing, estilos y comportamiento del carrusel de planes. |

##### Landing Page Collaboration

![Landing Page Contributors](../assets/images/others/contributors.png)

*Figura X. Contributors del repositorio del Landing Page.*

##### Project Report Collaboration

![Project Report Contributors](../assets/images/others/contributors1.png)

*Figura X. Contributors del repositorio de documentación Vitalita-Report.*

##### Commit Activity

![Sprint 1 Commit Activity](../assets/images/others/commits.png)

*Figura X. Actividad de commits registrada durante Sprint 1.*

##### Trello Collaboration

![Sprint 1 Trello Board](../assets/images/others/trello.png)

*Figura X. Tablero utilizado para el seguimiento colaborativo de Sprint 1.*

Las evidencias anteriores permiten contrastar la participación registrada en GitHub con las tareas planificadas en Trello y con la distribución presentada en la matriz de Aspect Leaders and Collaborators.
