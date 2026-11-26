# 9. Pruebas y validación

Este apartado demostrará que Synkra funciona correctamente y que cumple los requisitos establecidos.

## 9.1. Plan de pruebas

Se deberán definir las funcionalidades que se van a probar y los resultados esperados.

Entre las funcionalidades que deberán comprobarse se encuentran:

- Consulta de días disponibles.
- Creación de solicitudes.
- Consulta del estado de las solicitudes.
- Aprobación y rechazo de solicitudes.
- Consulta de días restantes.
- Importación de calendarios escolares.

## 9.2. Casos de prueba

**Pendiente de completar.**

Para cada caso de prueba se indicará:

- Identificador.
- Funcionalidad comprobada.
- Datos de entrada.
- Resultado esperado.
- Resultado obtenido.
- Estado de la prueba.

## 9.3. Pruebas de seguridad

Se realizaron comprobaciones para evaluar la seguridad de la aplicación, prestando especial atención a la validación de los datos introducidos, el control de acceso y la protección de la información.

- **Pruebas de inyección de código:** se realizaron pruebas introduciendo código o contenido potencialmente malicioso en los campos de entrada. Durante las comprobaciones realizadas no se consiguió ejecutar código ni alterar el funcionamiento de la aplicación mediante estas entradas.

## 9.4. Errores detectados y soluciones

Durante las pruebas de la aplicación se identificaron los siguientes errores y comportamientos inesperados:

- **Límite de caracteres en la descripción (aplicación de escritorio):** al introducir un texto superior a 250 caracteres en el campo de descripción, la aplicación se cerraba inesperadamente. Se solucionó estableciendo un límite de 250 caracteres en la interfaz WPF, impidiendo que el usuario introduzca textos que superen esa longitud.

- **Carga incorrecta de pantallas al iniciar la aplicación Flutter:** dependiendo de la velocidad de ejecución del sistema, podían mostrarse otras pantallas antes de que apareciera la pantalla de inicio de sesión. Este comportamiento todavía está pendiente de solucionar.

- **Problemas de conexión durante las pruebas en un dispositivo móvil físico:** no fue posible iniciar sesión desde la aplicación móvil debido a que el servicio todavía no se ha desplegado en un entorno accesible desde el dispositivo. Por este motivo, el móvil no puede establecer la conexión necesaria con el servidor durante las pruebas.

*Nota:* Los errores descritos corresponden a los problemas identificados durante las pruebas realizadas hasta el momento. No se descarta la existencia de otros errores o comportamientos inesperados que todavía no hayan sido detectados y que puedan aparecer durante futuras pruebas o con el uso de la aplicación.*
