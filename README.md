# Backend JWT

API REST hecha con Node.js, Express y MongoDB para la clase de Ingenieria de Software. Tiene registro y login de usuarios con JWT y un CRUD de tareas donde cada usuario solo puede ver, modificar y eliminar sus propias tareas.

## Instalacion

```
npm install
```

Despues crear un archivo .env en la raiz con las variables de .env.example:

```
PORT=5000
MONGO_DB=cadena de conexion de mongodb
JWT_SECRET=clave secreta
NODE_ENV=development
```

## Ejecucion

```
npm run server
```

o sin nodemon:

```
npm start
```

El servidor corre en http://localhost:5000

## Endpoints

Usuarios
- POST /api/users - registrar usuario (nombre, email, password)
- POST /api/users/login - login, regresa el token
- GET /api/users/datos - datos del usuario del token (requiere token)

Tareas (todas requieren token)
- GET /api/tareas - lista las tareas del usuario
- POST /api/tareas - crea una tarea (descripcion)
- PUT /api/tareas/:id - modifica una tarea propia
- DELETE /api/tareas/:id - elimina una tarea propia

Para las rutas protegidas hay que mandar el header:

```
Authorization: Bearer <token>
```
