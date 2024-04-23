# MyStore API

API de Tienda Virtual: Conexión a PostgreSQL con Sequelize y ExpressJs.

## Tabla de Contenidos

1. [Instalación](#instalación)
2. [Uso](#uso)
3. [Documentación Adicional](#documentación-adicional)
4. [Configuración de Sequelize](#configuración-de-sequelize)
5. [Archivo package.json](#archivo-packagejson)
6. [Licencia](#licencia)

## Instalación

1. Clona este repositorio en tu máquina local.
2. Instala las dependencias con el comando `npm install`.
3. Configura las variables de entorno creando un archivo `.env` basado en el archivo `.env.example` y completando los valores necesarios.
4. Ejecuta las migraciones de la base de datos con el comando `npm run migrations:run`.
5. Inicia el servidor con el comando `npm start`.

## Uso

### Endpoints

- `GET /api/v1/resource`: Obtiene todos los recursos.
- `POST /api/v1/resource`: Crea un nuevo recurso.
- `GET /api/v1/resource/:id`: Obtiene un recurso por su ID.
- `PUT /api/v1/resource/:id`: Actualiza un recurso existente.
- `DELETE /api/v1/resource/:id`: Elimina un recurso existente.

#### Ejemplo de solicitud (POST /api/v1/resource)

```json
{
  "nombre": "Ejemplo",
  "descripcion": "Este es un ejemplo de solicitud."
}
```

#### Ejemplo de respuesta exitosa

```json
{
  "id": 1,
  "nombre": "Ejemplo",
  "descripcion": "Este es un ejemplo de solicitud.",
  "createdAt": "2024-04-01T12:00:00.000Z"
}
```

#### Ejemplo de respuesta de error

```json
{
  "statusCode": 404,
  "error": "Not Found",
  "message": "Recurso no encontrado"
}
```

## Documentación Adicional

### Entidades

- **Customers** (id, name, lastName, phone, userId, createdAt)
- **Users** (id, email, password, role, createdAt)
- **Orders** (id, customerId, createdAt)
- **Products** (id, name, image, description, price, categoryId, createdAt)
- **Categories** (id, name, image, createdAt)

### Relaciones

- **Customers 1 <-> 1 Users**
- **Users 1 <-> N Orders**
- **Orders N <-> N Products**
- **Products N <-> N Categories**

## Configuración de Sequelize

La configuración de Sequelize se encuentra en el archivo `libs/sequelize.js`. Asegúrate de actualizar este archivo con la información correcta de tu base de datos PostgreSQL.

## Archivo package.json

El archivo `package.json` incluye todas las dependencias del proyecto, scripts de npm y otra información relevante para el proyecto.

## Licencia

Este proyecto está bajo la [Licencia MIT](LICENSE).
