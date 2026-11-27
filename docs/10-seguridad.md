# 10. Seguridad

Synkra gestionará información relacionada con los profesores y sus solicitudes, por lo que será necesario proteger los datos almacenados y evitar accesos no autorizados.

Durante el análisis inicial se ha identificado la necesidad de estudiar qué información debe protegerse y qué personas podrán acceder a ella.

## 10.1. Sistema de autenticación

La autenticación se implementa mediante **Spring Security** (en combinación con Spring Boot) para proteger los extremos de la API y restringir el acceso a determinadas operaciones. Asimismo, se emplea la librería **<abbr title="Java JSON Web Token">JJWT</abbr>** para facilitar la gestión de sesiones de usuario y la autenticación basada en tokens.

El acceso al sistema se realiza mediante **correo electrónico** y **contraseña**. Los usuarios no autenticados no podrán realizar ninguna operación en la aplicación, a excepción de intentar iniciar sesión.

Para más detalles sobre los requisitos y la arquitectura, ver los apartados [3.2.1 Seguridad](./03-analisis_requisitos.md/#321-seguridad) y [7.3.3. API (Java / Spring Boot)](./07-arquitectura.md/#733-api-java--spring-boot).

## 10.2. Gestión de usuarios y contraseñas

La **administración de cuentas** y el **control de acceso** se basan en un modelo de permisos asociados a **roles**. Todo usuario registrado debe pertenecer obligatoriamente a uno de los siguientes perfiles, los cuales determinan sus privilegios sobre los recursos y operaciones del sistema:

- **Profesor:** Acceso a los recursos propios de su actividad docente. Entre sus funciones se incluye la **consulta** y **gestión de solicitudes específicas**, tales como pedir días moscosos y comprobar el estado de dicha solicitud.

- **Gestor:** Perfil enfocado en la administración logística y la configuración de recursos, con capacidad específica para **administrar el bloqueo de calendarios**.

- **Director:** Rol con **control total** sobre la plataforma. Posee de forma heredada todos los permisos del profesor y del gestor, además de la capacidad exclusiva para **gestionar operaciones avanzadas** sobre sesiones, grupos, profesorado y calendarios.

### 10.2.1. Seguridad de credenciales

Para garantizar la integridad y confidencialidad de las cuentas, las contraseñas nunca se almacenan en texto plano. En su lugar, se cifran mediante el algoritmo **BCrypt**, que combina el hash resultante con un *salt* aleatorio único por cada clave. Este mecanismo protege los datos frente a ataques por fuerza bruta y el uso de tablas arcoíris (*rainbow tables*).

## 10.3. Control de permisos

El control de acceso se rige por los roles de usuario:

| Rol | Funciones y privilegios |
|-----|---------|
| Director | Gestión avanzada de sesiones, grupos, profesorado y calendarios; hereda íntegramente las funciones del profesor y el gestor |
| Profesor | Consulta y solicitud de días moscosos y seguimiento de su estado |
| Gestor | Importación y administración del bloqueo de calendarios |

## 10.4. Protección frente a accesos no autorizados

Cualquier usuario que pretenda acceder a un recurso protegido debe estar debidamente autenticado mediante sus credenciales (correo y contraseña), además de incluir un token <abbr title="JSON Web Token">JWT</abbr> válido en las peticiones a la API.

## 10.5. Validación de datos

La validación y saneamiento de los datos de entrada se gestionan a nivel de backend mediante **Spring Boot Validation**, asegurando que la información recibida cumpla con las restricciones de formato e integridad antes de ser procesada.

Ver apartado [7.3.3. API (Java / Spring Boot)](./07-arquitectura.md/#733-api-java--spring-boot) para más información.

## 10.6. Protección de información sensible

Se garantiza que el acceso a los recursos esté estrictamente condicionado por el rol del usuario autenticado, denegando de forma automática cualquier intento de consulta por parte de entidades no autorizadas o usuarios sin sesión activa.

## 10.7. Copias de seguridad

Actualmente no se realizan copias de seguridad de los datos.

## 10.8. Cumplimiento de la normativa de protección de datos aplicable (<abbr title="Reglamento General de Protección de Datos">RGPD</abbr> y <abbr title="Ley Orgánica de Protección de Datos Personales y garantía de los derechos digitales">LOPDGDD</abbr>, cuando corresponda)

**Pendiente de análisis e implementación** cuando corresponda según el despliegue final.