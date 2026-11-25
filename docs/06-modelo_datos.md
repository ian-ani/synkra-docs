# 6. Modelo de datos

Este apartado describirá cómo se organizará y almacenará la información utilizada por Synkra.

En el análisis inicial se han identificado varios tipos de información necesarios para el funcionamiento de la aplicación:

- Los profesores y sus datos identificativos.
- Los calendarios escolares.
- Las solicitudes de días moscosos.
- Los días moscosos ya disfrutados y los restantes.
- Los turnos de trabajo del profesorado.
- Los grupos de alumnos del profesorado.
- Los roles y permisos de los usuarios.

## 6.1. Diseño de la base de datos

Para almacenar la información de Synkra se utiliza **MySQL** como sistema gestor de bases de datos relacional. Durante el desarrollo se emplea XAMPP para gestionar el servicio de base de datos y phpMyAdmin para facilitar su administración.

La aplicación, desarrollada con Spring Boot, se comunica con MySQL para almacenar, consultar y modificar la información necesaria para su funcionamiento.

La base de datos se organizará mediante tablas relacionadas entre sí. Su estructura se definirá teniendo en cuenta las necesidades de la aplicación y las relaciones entre los distintos tipos de información.

## 6.2. Diagrama entidad-relación

```mermaid
erDiagram
    profesor {
        int id PK
        string dni UK
        string nombre
        string apellidos
        string email UK
        string contrasenya
        string rol
        string telefono
        string direccion
        string cp
        string localidad
        string cuerpo
        string especialidad
        string departamento
    }

    sesion_horario {
        int id PK
        string cod_grupo
        int id_profe FK
        string dia_semana
        time hora_inicio
        time hora_fin
    }

    moscoso_solicitudes {
        int id PK
        int id_profesor FK
        date fecha
        string estado
        string tipo
    }

    grupos_alumnado {
        string cod_grupo PK
        string nombre_grupo
        int id_profesor FK
    }

    bloqueos_calendario {
        int id PK
        date fecha_inicio
        date fecha_fin
        string tipo
    }

    profesor ||--o{ sesion_horario : "imparte"
    profesor ||--o{ moscoso_solicitudes : "solicita"
    profesor ||--o{ grupos_alumnado : "tutorea"
    sesion_horario }o--|| grupos_alumnado : "pertenece"
```

## 6.3. Diccionario de datos

Se documentará la estructura de las tablas de la base de datos, indicando para cada campo:

- Nombre del campo.
- Tipo de dato.
- Clave primaria y claves ajenas, cuando corresponda.
- Restricciones aplicables.

*//TODO aqui es poner lo que tenemos en Spring Boot en los modelos*

## 6.4. Relaciones y funcionamiento

**Pendiente de completar.**