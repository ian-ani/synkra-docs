# 3. Análisis de requisitos

Este apartado recoge las funcionalidades que deberá ofrecer Synkra y las condiciones que deberá cumplir. Algunos requisitos todavía están pendientes de concretar, ya que dependen de las normas del centro y de las decisiones técnicas del proyecto.

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

- Seguridad.

*// TODO*

*Apartado 2.2, pero estamos con Spring Security, cifrado contraseñas, tokens, etc*

- Rendimiento.

*Por escribir*

- Usabilidad.

*Apartado 3.1*

- Compatibilidad.

*Apartado 5.1.A*

- Disponibilidad.

*Apartados 2.2 y 6.3, aspectos relacionados con el calendario y la disponibilidad de solicitudes*

## 3.3. Usuarios y roles

Se han identificado los siguientes perfiles:

| Perfil | Permisos y acciones permitidas |
|--------|--------------------------------|
| Profesorado | Consultar disponibilidad, solicitar días moscosos, consultar el estado de las solicitudes, conocer los días restantes, cambiar la contraseña de usuario y ver el calendario escolar |
| Equipo directivo | Revisar, aprobar y rechazar solicitudes; también puede utilizar las funciones disponibles para el profesorado y los gestores |
| Gestores | Importar calendarios escolares y realizar las tareas de gestión que se determinen |
