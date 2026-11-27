# 8. Desarrollo e implementación

## 8.1. Preparación del entorno de desarrollo

- Instalación y configuración de las herramientas.
- Configuración del proyecto.
- Preparación de la base de datos.
- Dependencias necesarias.

## 8.2. Estructura del proyecto

Para garantizar una correcta separación de responsabilidades y facilitar el mantenimiento, cada uno de los módulos de **Synkra** se organiza de forma independiente siguiendo los patrones arquitectónicos propios de su tecnología.

### 8.2.1. API (Spring Boot / Java)

```console
api/
├── ApiApplication.java   # Entrypoint de la API
├── config/
│   ├── DataInitializer.java   # Crea un director
│   └── OpenApiConfig.java   # Token JWT
├── controller/
│   ├── AuthController.java   # Controlador para el inicio de sesión
│   ├── BloqueCalendarioController.java   # Controlador para la gestión del bloqueo de calendario
│   ├── GrupoAlumnadoController.java   # Controlador para la gestión del grupo de alumnado
│   ├── ProfesorController.java   # Controlador para la gestión del profesor
│   └── SesionHorarioController.java   # Controlador de la sesión de horario del profesor
├── domain/
│   ├── BloqueoCalendario.java   # Entidad de bloqueo_calendario
│   ├── GrupoAlumnado.java   # Entidad grupo_alumnado
│   ├── Profesor.java   # Entidad profesores
│   ├── SesionHorario.java   # Entidad horarios
│   └── Solicitud.java   # Entidad solicitudes (por completar)
├── enums/
│   ├── Estado.java   # Estado de la solicitud
│   ├── Rol.java   # Roles de usuarios
│   └── Tipo.java   # Tipo de días bloqueados
├── exception/
├── repository/
│   ├── BloqueoCalendarioRepository.java
│   ├── GrupoAlumnadoRepository.java
│   ├── ProfesorRepository.java
│   └── SesionHorarioRepository.java
├── security/
│   ├── JwtAuthFilter.java   # Marca si el usuario es autenticado o no
│   ├── JwtService.java   # Crea y valida los tokens JWT
│   ├── ProfesorUserDetailsService.java   # Busca y carga un usuario
│   └── SecurityConfig.java   # Configuración central de seguridad
└── service/  # CRUDs
    ├── BloqueoCalendarioService.java
    ├── BloqueoCalendarioServiceImpl.java
    ├── GrupoAlumnadoService.java
    ├── GrupoAlumnadoServiceImpl.java
    ├── ProfesorService.java
    ├── ProfesorServiceImpl.java
    ├── SesionHorarioService.java
    └── SesionHorarioServiceImpl.java
```

*Nota: Este módulo sigue un diseño en capas tradicional de Spring Boot, separando claramente los controladores REST, la lógica de negocio (servicios), el acceso a datos (repositorios) y las entidades de dominio.*

### 8.2.2. Escritorio (C# / .NET)

```console
desktop/
├── Converters/
│   └── Converters.cs  # Conversores y formateos
├── Models/
│   ├── DiaCalendario.cs  # Entidad de bloqueo_calendario
│   └── TipoDia.cs  # Tipo de días bloqueados
├── Services/
│   ├── ApiClient.cs  # DTOs y peticiones a la API
│   ├── ApiExceptions.cs  # Excepciones resultantes de la API
│   ├── AuthService.cs  # Inicio y cierre de sesión
│   └── SesionUsuario.cs  # Sesión del usuario y sus permisos
├── ViewModels/
│   └── MainViewModel.cs  # Lógica de la pantalla principal (calendario de bloqueo)
└── Views/
    ├── EditarProfesorView.xaml   # Diseño de la pantalla de edición del profesor
    ├── EditarProfesorView.xaml.cs   # Lógica de la pantalla de edición del profesor
    ├── LoginView.xaml   # Diseño de la pantalla de login
    ├── LoginView.xaml.cs   # Lógica de la pantalla de login
    ├── ProfesoresView.xaml  # Diseño del listado de profesores
    └── ProfesoresView.xaml.cs  # Lógica del listado de profesores
```

*Nota: El desarrollo de escritorio se apoya en el patrón [MVVM](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93modelo_de_vista), desacoplando la interfaz de usuario (Views) de la lógica de presentación (ViewModels) y la gestión de datos.*

### 8.2.3. Móvil y web (Flutter)

```console
mobile/
├── main.dart  # Definición de tema e idioma, entrypoint de la app
├── models/
│   ├── bloqueo.dart  # Entidad de bloqueo_calendario
│   ├── profesor.dart  # Entidad profesores
│   └── sesion_horario.dart  # Entidad horarios
├── pages/
│   ├── auth_gate.dart  # Comprueba el token guardado contra la API, direcciona a Home o login
│   ├── calendar_screen.dart  # Pantalla de calendario escolar
│   ├── home_screen.dart  # Pantalla principal de la aplicación (una vez el usuario ha logueado)
│   ├── login_screen.dart  # Pantalla de inicio de sesión
│   ├── school_info_screen.dart  # Pantalla con información del centro escolar
│   ├── solicitud_calendar_screen.dart  # Pantalla de calendario que permite solicitar días moscosos
│   ├── solicitud_screen.dart  # Base para la pantalla de solicitud, está sin empezar
│   └── user_screen.dart  # Pantalla con informacion del usuario: nombre, sesiones, etc
├── services/
│   ├── api_client.dart  # Inicio de sesión y endpoints para peticiones a la API
│   ├── api_config.dart  # Configuración de la API (dirección, puerto)
│   ├── auth_service.dart  # Inicio y cierre de sesión 
│   └── token_storage.dart  # Guarda el token JWT
├── utils/
│   └── utils.dart  # Datos de prueba para el calendario
└── widget/
    ├── horario_semanal.dart  # Sesiones de horario de un profesor (perfil)
    ├── nav_bar.dart  # Barra de navegación inferior
    ├── password_change_box.dart  # Caja para el cambio de contraseña (perfil)
    └── password_widget.dart  # Diseño del input de contraseña
```

*Nota: La estructura de Flutter agrupa los componentes de forma modular por responsabilidades (pages, services, models y widgets), facilitando la reutilización de código entre la versión móvil y web.*

## 8.3. Implementación de las funcionalidades

Para cada funcionalidad importante:

- Qué hace.
- Cómo se ha implementado.
- Qué archivos intervienen.
- Capturas de pantalla del resultado.
- Explicación de las partes relevantes del código.

## 8.4. Código fuente

- Fragmentos de código representativos.
- Explicación de las funciones, clases o métodos principales.
- Explicación de la conexión con la base de datos.
- Gestión de errores y excepciones, cuando proceda.

## 8.5. Librerías y dependencias

### 8.5.1. Dependencias utilizadas

El detalle completo de las librerías empleadas en cada uno de los módulos del ecosistema Synkra (API, programa de escritorio y aplicación móvil/web), junto con sus respectivas versiones, funciones y justificación técnica, se encuentra recogido en el apartado [7.3. Frameworks y librerías](./07-arquitectura.md/#73-frameworks-y-librerías).

### 8.5.2. Archivos de configuración de dependencias

La gestión y declaración de las dependencias de cada subsistema se realiza a través de los correspondientes archivos de configuración de sus gestores de paquetes:

- **API (Backend - Spring Boot):** Las dependencias se encuentran declaradas en el archivo `pom.xml`, dentro del bloque `<dependencies>`, gestionadas mediante **Maven**.
- **Programa de escritorio:** Su configuración se gestiona a través del archivo de proyecto `CalendarioApp.csproj` (C# / .NET). *Nota: Actualmente el proyecto de escritorio no requiere dependencias externas adicionales a las librerías base del framework.*
- **Aplicación web y móvil (Flutter):** Las dependencias de terceros se especifican en el archivo `pubspec.yaml`, bajo la sección correspondiente de `dependencies`.

## 8.6. Repositorio del proyecto

### 8.6.1. Estructura de repositorios e historial de *commits*

Con el fin de mantener una correcta separación de responsabilidades y modularidad en el desarrollo, el código fuente del proyecto se ha distribuido en cuatro repositorios independientes (tres correspondientes a los distintos módulos del sistema y uno exclusivo para la documentación):

| Función | Enlace al repositorio | Historial de trabajo |
|---------|-----------------------|------------------------|
| Programa de escritorio | [Código fuente](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-desktop) | [Historial](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-desktop/activity)
| Aplicación móvil y web | [Código fuente](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-mobile) | [Historial](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-mobile/activity)
| API | [Código fuente](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-api) | [Historial](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-api/activity)
| Documentación | [Código fuente](https://github.com/ian-ani/synkra-docs) | [Historial](https://github.com/ian-ani/synkra-docs/activity)
| Gestión de tareas | [Tablero del proyecto](https://github.com/users/Mokey09/projects/4) | - |

Adicionalmente, se puede acceder de forma directa a los repositorios principales (escritorio, móvil y API) desde los accesos directos ubicados en la esquina inferior derecha de la interfaz de la documentación web.

### 8.6.2. Control de versiones y ramas del proyecto

Para el desarrollo de Synkra se ha seguido una estrategia de ramificación basada en características, lo que permite aislar el desarrollo de cada funcionalidad antes de unificarla en el código común. 

Las ramas de trabajo principales son las siguientes:

* **`main`**: Rama principal que contiene las versiones estables y definitivas para la entrega de los hitos del proyecto.
* **`develop`**: Rama de integración donde se unifican de forma continua las distintas tareas y módulos desarrollados por el equipo.
* **Ramas de características (*feature*)**: Empleadas de forma temporal para el desarrollo modular de componentes específicos (como `calendarScreen`, `conectar-api`, `LoginScreen`, `solicitud-moscosos`, `tema-oscuro`, entre otras).

Para consultar el estado actualizado, el grafo de commits o la evolución en tiempo real de estas ramas, se puede emplear cualquier cliente de control de versiones como **SourceTree**, revisar directamente los repositorios en el **tablero de GitHub** (ver apartado anterior), o utilizar los comandos nativos de Git (por ejemplo, `git branch -a` o `git log --graph --oneline --all --decorate`).
