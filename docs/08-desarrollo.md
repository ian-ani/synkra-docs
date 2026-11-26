# 8. Desarrollo e implementación

## 8.1. Preparación del entorno de desarrollo

- Instalación y configuración de las herramientas.
- Configuración del proyecto.
- Preparación de la base de datos.
- Dependencias necesarias.

## 8.2. Estructura del proyecto

Para garantizar una correcta separación de responsabilidades, cada uno de los módulos de Synkra se organiza de forma independiente siguiendo los patrones arquitectónicos propios de cada tecnología (Spring Boot para el backend, C# / .NET para el escritorio y Flutter para el cliente multiplataforma).

A continuación, se detalla la estructura de directorios y archivos clave de cada subsistema:

### 8.2.1. API (Backend - Spring Boot / Java)

Estructura organizada en capas bajo el paquete principal de la aplicación:

```console
\---api
    |   ApiApplication.java
    |
    +---config
    |       DataInitializer.java
    |       OpenApiConfig.java
    |
    +---controller
    |       AuthController.java
    |       BloqueCalendarioController.java
    |       GrupoAlumnadoController.java
    |       ProfesorController.java
    |       SesionHorarioController.java
    |
    +---domain
    |       BloqueoCalendario.java
    |       GrupoAlumnado.java
    |       Profesor.java
    |       SesionHorario.java
    |       Solicitud.java
    |
    +---enums
    |       Estado.java
    |       Rol.java
    |       Tipo.java
    |
    +---exception
    +---repository
    |       BloqueoCalendarioRepository.java
    |       GrupoAlumnadoRepository.java
    |       ProfesorRepository.java
    |       SesionHorarioRepository.java
    |
    +---security
    |       JwtAuthFilter.java
    |       JwtService.java
    |       ProfesorUserDetailsService.java
    |       SecurityConfig.java
    |
    \---service
            BloqueoCalendarioService.java
            BloqueoCalendarioServiceImpl.java
            GrupoAlumnadoService.java
            GrupoAlumnadoServiceImpl.java
            ProfesorService.java
            ProfesorServiceImpl.java
            SesionHorarioService.java
            SesionHorarioServiceImpl.java
```

### 8.2.2. Programa de escritorio (C# / .NET)

```console
...
|
+---bin
|
+---Converters
|       Converters.cs
|
+---Models
|       DiaCalendario.cs
|       TipoDia.cs
|
+---obj
|
+---Services
|       ApiClient.cs
|       ApiExceptions.cs
|       AuthService.cs
|       SesionUsuario.cs
|
+---ViewModels
|       MainViewModel.cs
|
\---Views
        LoginView.xaml
        LoginView.xaml.cs
        ProfesoresView.xaml
        ProfesoresView.xaml.cs
```

### 8.2.3. Aplicación móvil y web (Flutter)

Estructura modular orientada a pantallas, servicios y componentes reutilizables:

```console
...
|
|   main.dart
|
+---models
|       bloqueo.dart
|       profesor.dart
|       sesion_horario.dart
|
+---pages
|       auth_gate.dart
|       calendar_screen.dart
|       home_screen.dart
|       login_screen.dart
|       school_info_screen.dart
|       sesion_horario.dart
|       solicitud_calendar_screen.dart
|       solicitud_screen.dart
|       user_screen.dart
|
+---services
|       api_client.dart
|       api_config.dart
|       auth_service.dart
|       token_storage.dart
|
+---utils
|       utils.dart
|
\---widget
        horario_semanal.dart
        nav_bar.dart
        password_change_box.dart
        password_widget.dart
```

- Explicación de la función de los archivos principales.
- Organización del código fuente.

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

### Dependencias utilizadas

El detalle completo de las librerías empleadas en cada uno de los módulos del ecosistema Synkra (API, programa de escritorio y aplicación móvil/web), junto con sus respectivas versiones, funciones y justificación técnica, se encuentra recogido en el apartado [7.3. Frameworks y librerías](./07-arquitectura.md/#73-frameworks-y-librerías).

### Archivos de configuración de dependencias

La gestión y declaración de las dependencias de cada subsistema se realiza a través de los correspondientes archivos de configuración de sus gestores de paquetes:

- **API (Backend - Spring Boot):** Las dependencias se encuentran declaradas en el archivo `pom.xml`, dentro del bloque `<dependencies>`, gestionadas mediante **Maven**.
- **Programa de escritorio:** Su configuración se gestiona a través del archivo de proyecto `CalendarioApp.csproj` (C# / .NET). *Nota: Actualmente el proyecto de escritorio no requiere dependencias externas adicionales a las librerías base del framework.*
- **Aplicación web y móvil (Flutter):** Las dependencias de terceros se especifican en el archivo `pubspec.yaml`, bajo la sección correspondiente de `dependencies`.

## 8.6. Repositorio del proyecto

### Estructura de repositorios e historial de *commits*

Con el fin de mantener una correcta separación de responsabilidades y modularidad en el desarrollo, el código fuente del proyecto se ha distribuido en cuatro repositorios independientes (tres correspondientes a los distintos módulos del sistema y uno exclusivo para la documentación):

| Función | Enlace al repositorio | Historial de trabajo |
|---------|-----------------------|------------------------|
| Programa de escritorio | [Código fuente](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-desktop) | [Historial de `develop`](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-desktop/commits/develop)
| Aplicación móvil y web | [Código fuente](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-mobile) | [Historial de `develop`](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-mobile/commits/develop)
| API | [Código fuente](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-api) | [Historial de `develop`](https://github.com/Mokey09/LilBrosTeam-Proyecto2DAM-api/commits/develop)
| Documentación | [Código fuente](https://github.com/ian-ani/synkra-docs) | [Historial de `main`](https://github.com/ian-ani/synkra-docs/commits/main/)
| Gestión de tareas | [Tablero del proyecto](https://github.com/users/Mokey09/projects/4) | - |

*Nota sobre las ramas: Actualmente los enlaces apuntan a la rama de integración* `develop` *en los repositorios de código. Una vez finalizado el proyecto y alcanzada su versión estable, dichos enlaces se redirigirán a la rama principal (*`main`*).*

Adicionalmente, se puede acceder de forma directa a los repositorios principales (escritorio, móvil y API) desde los accesos directos ubicados en la esquina inferior derecha de la interfaz de la documentación web.

### Control de versiones y gestión de ramas

A continuación, se muestra el flujo de trabajo y el estado de las ramas visualizado a través del cliente **SourceTree**:

**Añadir imágenes del SourceTree.**