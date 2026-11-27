# 3. Análisis de requisitos

## 3.1. Requisitos funcionales

Los requisitos funcionales iniciales identificados son los siguientes:

| Requisito | Usuario |
|-----------|---------|
| Consultar los días disponibles para solicitar | Profesorado |
| Realizar una solicitud de día moscoso | Profesorado |
| Consultar el estado de las solicitudes realizadas | Profesorado |
| Consultar los días moscosos restantes durante el curso | Profesorado |
| Consultar el motivo de rechazo de una solicitud | Profesorado |
| Revisar las solicitudes recibidas | Equipo directivo |
| Aprobar solicitudes | Equipo directivo |
| Rechazar solicitudes e indicar el motivo | Equipo directivo |
| Importar calendarios escolares | Gestores y equipo directivo |
| Bloquear rangos de fechas | Gestores y equipo directivo |
| Gestionar sesiones y grupos | Gestores y equipo directivo |

El equipo directivo también forma parte del profesorado, por lo que podrá realizar las acciones correspondientes a ese perfil.

## 3.2. Requisitos no funcionales

### 3.2.1. Seguridad

- Las contraseñas se almacenan de forma segura mediante funciones hash y el uso de un *salt*, dificultando su recuperación mediante tablas arcoíris y ataques basados en contraseñas precalculadas.
- La autenticación de los usuarios se realiza mediante tokens <abbr title="JSON Web Token">JWT</abbr>.
- Los permisos de acceso dependen del rol asignado a cada usuario.
- Los usuarios no pueden acceder a operaciones o información a la que no hayan sido autorizados.
- Los usuarios no autenticados no tienen acceso a ningún recurso de la <abbr title="Application Programming Interface">API</abbr>.

Ver apartado [10. Seguridad](./10-seguridad.md#10-seguridad) para más información.

### 3.2.2. Rendimiento

**Pendiente de determinar.**

### 3.2.3. Usabilidad

- La interfaz es intuitiva y fácil de utilizar.
- Las opciones están organizadas según el perfil del usuario.
- Los formularios muestran mensajes claros cuando se produce un error.
- El usuario puede consultar fácilmente el estado de sus solicitudes.

### 3.2.4. Compatibilidad

- La aplicación del profesorado funciona en dispositivos Android y navegadores web compatibles.
- La aplicación de escritorio funciona en sistemas Windows.
- Ambas aplicaciones se pueden comunicar con la misma <abbr title="Application Programming Interface">API</abbr>.

### 3.2.5. Disponibilidad

- El profesorado puede consultar la disponibilidad de días moscosos y realizar solicitudes cuando el servicio está operativo.
- La <abbr title="Application Programming Interface">API</abbr> y la base de datos estarán funcionando para permitir las operaciones de cada aplicación.
- Los calendarios permiten identificar los días en los que se pueden realizar solicitudes y aquellos que están bloqueados.

## 3.3. Usuarios y roles

Se han identificado los siguientes perfiles:

| Perfil | Permisos y acciones permitidas |
|--------|--------------------------------|
| Profesorado | Consultar disponibilidad, solicitar días moscosos, consultar el estado de las solicitudes, conocer los días restantes, cambiar la contraseña de usuario y ver el calendario escolar |
| Equipo directivo | Revisar, aprobar y rechazar solicitudes; también puede utilizar las funciones disponibles para el profesorado y los gestores |
| Gestores | Importar calendarios escolares y realizar las tareas de gestión que se determinen |
