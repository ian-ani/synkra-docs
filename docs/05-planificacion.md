# 5. Planificación y seguimiento

## 5.1. Fases del proyecto

### 5.1.1. Primera etapa

Esta fase se centra en establecer los cimientos del proyecto, validar la arquitectura cliente-servidor y desarrollar un producto mínimo viable funcional:

- **Análisis y planificación:** Formación del equipo de trabajo, definición del alcance del problema, capacitación en las tecnologías seleccionadas y estructuración del plan inicial.
- **Diseño e implementación base:** Modelado de datos, diseño de interfaces y desarrollo de las funcionalidades principales en las distintas plataformas del ecosistema (<abbr title="Application Programming Interface">API</abbr> <abbr title="Representational State Transfer">REST</abbr>, aplicación de escritorio, aplicación móvil y entorno web).
- **Consolidación y entrega parcial:** Redacción de la documentación técnica correspondiente y presentación de la primera etapa evaluable del proyecto.

### 5.2.2. Segunda etapa

**Pendiente de completar.**

## 5.2. Tareas previstas

Las tareas previstas se pueden encontrar en el tablero del proyecto: [enlace al tablero](https://github.com/users/Mokey09/projects/4).

## 5.3. Calendario de desarrollo

| Parte del proyecto | Fecha límite | Tareas realizadas |
|--------------------|-------|-------------------|
| General | 04-10-2026 | Formación del equipo, [definición del problema](./01-presentacion.md/#15-problema-que-pretende-resolver) y planificación inicial |
| API | 18-10-2026 | Diseño del modelo [Entidad-Relación (E-R)](./06-modelo_datos.md/#62-diagrama-entidad-relación) y creación de las entidades en Spring Boot |
| API | 01-11-2026 | Implementación de la lógica y los *endpoints* para el bloqueo de calendarios |
| Programa escritorio | 03-11-2026 | Diseño de los [*mockups*](./04-diseno.md/#42-diseño-de-la-interfaz) y desarrollo de la interfaz base del programa |
| API | 15-11-2026 | Gestión de perfiles, sesiones y grupos; [integración del inicio de sesión](./10-seguridad.md/#101-sistema-de-autenticación), [roles y seguridad](./10-seguridad.md/#103-control-de-permisos), inclusión de Swagger |
| Aplicación móvil | 15-11-2026 | Diseño del logo, [*mockups*](./04-diseno.md/#42-diseño-de-la-interfaz) y vistas de *splash*, inicio de sesión, perfil de usuario y calendario escolar |
| Programa escritorio | 21-11-2026 | Integración con la API e implementación funcional de las pantallas de inicio de sesión y bloqueo
| Aplicación móvil | 29-11-2026 | Integración con la API, desarrollo de las vistas diseñadas e implementación de los días bloqueados |
| Documentación | 03-12-2026 | Redacción y consolidación de la documentación técnica del primer trimestre |
| **PRIMER FINAL** | **04-12-2026** | **Presentación y entrega parcial del estado actual del proyecto** |

*Nota: Las fechas indicadas corresponden a la planificación estimada y pueden sufrir ligeras variaciones en función de la evolución real del desarrollo.*

## 5.4. Herramientas de organización y seguimiento

Para organizar y realizar el seguimiento del desarrollo de Synkra estamos utilizando **GitHub Projects**, junto con el sistema de tableros **Kanban** que incorpora la propia plataforma.

Esta herramienta nos permite organizar las tareas del proyecto en un tablero visual, consultar su estado y realizar un seguimiento del trabajo pendiente y del que ya se ha completado.

Mediante Kanban podemos visualizar y gestionar las tareas a lo largo de las distintas etapas del desarrollo, facilitando la organización y coordinación del trabajo.

## 5.5. Registro de tareas realizadas

Dicho registro también se está haciendo mediante **GitHub Projects** y **Kanban**. Además, todos los días nos ponemos al día con lo que hemos hecho cada uno, qué vamos a hacer, qué dudas tenemos, ideas propuestas, etcétera.

[Enlace al tablero](https://github.com/users/Mokey09/projects/4) con el registro de tareas a realizar y realizadas.

## 5.6. Problemas y cambios en la planificación

Durante el desarrollo del proyecto se han identificado las siguientes desviaciones y ajustes menores sobre la planificación inicial:

- **Dependencia del backend (API):** Se produjo un ligero retraso en el desarrollo de la aplicación móvil y el programa de escritorio, ya que fue necesario priorizar y avanzar primero en la implementación de la API para asegurar que el núcleo y los endpoints estuvieran listos antes de integrarlos en las interfaces de cliente.
- **Inclusión de Swagger:** La integración de la documentación interactiva de la API estaba prevista inicialmente para el 1 de noviembre de 2026. Debido a un despiste grupal en la planificación inicial, su incorporación se pospuso y se completó finalmente en el siguiente sprint del módulo de la API, el 15 de noviembre de 2026.
