# Backend – Base de Datos (COrders)

## Objetivo
Diseñar una base de datos flexible que permita almacenar órdenes dinámicas creadas desde el frontend.

## Enfoque
- PostgreSQL
- Uso de JSONB
- Sin normalización de campos
- Sin interpretación de la estructura del formulario

## Modelo
Tabla principal: `orders`

| Campo | Tipo | Descripción |
|------|------|-------------|
| id | UUID | Identificador único |
| title | VARCHAR | Nombre opcional de la orden |
| schema | JSONB | Definición completa del formulario |
| created_at | TIMESTAMP | Fecha de creación |
| updated_at | TIMESTAMP | Fecha de actualización |

## Regla fundamental
Si el frontend cambia la estructura del formulario, la base de datos no requiere modificaciones.

### Uso de Docker

El uso de Docker no es obligatorio para el diseño de la base de datos.
El módulo Backend–Base de Datos fue validado utilizando PostgreSQL local y `psql`.

Docker puede emplearse opcionalmente como entorno de ejecución para estandarizar
versiones y facilitar la replicación del entorno entre distintos desarrolladores,
sin afectar el diseño ni el modelo de datos basado en JSONB.


## Ejecución local
La base de datos fue ejecutada localmente usando PostgreSQL y `psql`.
Docker es opcional y no es requerido para el rol Backend–Database.

### ¿Por qué el campo schema no se visualiza en el directorio?

El campo `schema` no se encuentra en el sistema de archivos del proyecto porque no es un archivo ni una estructura del proyecto. 
Es una columna de tipo JSONB almacenada dentro de la base de datos PostgreSQL.

Los directorios del proyecto contienen únicamente scripts SQL y documentación, mientras que los datos reales se almacenan y consultan exclusivamente mediante SQL.
