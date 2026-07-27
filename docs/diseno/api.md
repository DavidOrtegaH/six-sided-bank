# API REST

## Objetivo

La API REST proporciona un punto de comunicación entre el frontend desarrollado con React y el backend desarrollado con Spring Boot.

Todas las operaciones se realizan mediante HTTP y utilizan JSON como formato de intercambio de datos.

---

# Información general

- Arquitectura: REST
- Formato de datos: JSON
- Autenticación: JWT
- Codificación: UTF-8

Base URL:

/api

---

# Convenciones

## Métodos HTTP

| Método | Uso |
|---------|-----|
| GET | Obtener recursos |
| POST | Crear recursos |
| PUT | Actualizar recursos |
| PATCH | Actualización parcial |
| DELETE | Eliminar recursos |

---

## Códigos de respuesta

| Código | Significado |
|---------|-------------|
| 200 | Operación correcta |
| 201 | Recurso creado |
| 204 | Sin contenido |
| 400 | Petición incorrecta |
| 401 | No autenticado |
| 403 | Acceso denegado |
| 404 | Recurso no encontrado |
| 409 | Conflicto |
| 500 | Error interno |

---

# Autenticación

La autenticación se realizará mediante JWT.

Las rutas protegidas requerirán la cabecera:

Authorization: Bearer <token>

---

# Recursos

La API estará organizada en los siguientes recursos:

- /auth
- /users
- /accounts
- /transactions
- /transfers

La documentación detallada de cada recurso se añadirá durante la implementación.

---

# Versionado

Actualmente la API no está versionada.

En futuras versiones podrá utilizarse:

/api/v1