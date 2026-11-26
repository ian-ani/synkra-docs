# 8. Desarrollo e implementación

## 8.1. Preparación del entorno de desarrollo

- Instalación y configuración de las herramientas.
- Configuración del proyecto.
- Preparación de la base de datos.
- Dependencias necesarias.

## 8.2. Estructura del proyecto

- Árbol de carpetas y archivos.
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