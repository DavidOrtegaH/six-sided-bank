# Modelo de Datos

## Objetivo

Este documento describe el modelo de datos del dominio de Six Sided Bank.

El objetivo es representar las entidades principales del sistema, sus atributos y las relaciones existentes entre ellas, independientemente de la tecnología de persistencia utilizada.

---

# Entidades

## Client

Representa a un cliente registrado en la aplicación.

### Atributos

| Atributo | Descripción |
|----------|-------------|
| id | Identificador único del cliente. |
| DNI | Documento Nacional de Identidad |
| firstName | Nombre del usuario. |
| lastName | Apellidos del usuario. |
| email | Dirección de correo electrónico. |
| password | Contraseña cifrada. |
| createdAt | Fecha de creación de la cuenta. |
| enabled | Indica si la cuenta está activa. |

### Relaciones

- Un cliente puede tener una cuenta bancaria.

---

## Account

Representa una cuenta bancaria perteneciente a un cliente.

### Atributos

| Atributo | Descripción |
|----------|-------------|
| id | Identificador único. |
| iban | Número IBAN de la cuenta. |
| balance | Saldo disponible. |
| accountType | Tipo de cuenta. |
| status | Estado de la cuenta. |
| createdAt | Fecha de apertura. |

### Relaciones

- Pertenece a un único usuario.
- Puede contener múltiples transacciones.

---

## Transaction

Representa un movimiento económico realizado sobre una cuenta bancaria.

### Atributos

| Atributo | Descripción |
|----------|-------------|
| id | Identificador único. |
| amount | Importe del movimiento. |
| type | Tipo de operación. |
| concept | Concepto de la operación. |
| operationDate | Fecha de la operación. |
| balanceAfterOperation | Saldo resultante. |

### Relaciones

- Pertenece a una cuenta bancaria.

---

## Administrator

Representa a un administrador del banco.

### Atributos

| Atributo | Descripción |
|----------|-------------|
| id | Identificador único del administrador. |
| DNI | Documento Nacional de Identidad |
| firstName | Nombre del administrador. |
| lastName | Apellidos del administrador. |
| email | Dirección de correo electrónico. |
| password | Contraseña cifrada. |
| enabled | Indica si la cuenta está activa. |
| createdAt | Fecha de creación de la cuenta. |

---

# Relaciones

## Cliente - Account

**1 : 1**

Un usuario puede poseer una cuenta bancaria.

Cada cuenta pertenece exclusivamente a un usuario.

---

## Account - Transaction

**1 : N**

Una cuenta bancaria puede registrar múltiples transacciones.

Cada transacción pertenece únicamente a una cuenta.

---

# Restricciones del dominio

- El correo electrónico debe ser único.
- El DNI es único.
- Cada cliente solo puede tener una cuenta, asociada a su DNI.
- El IBAN debe ser único.
- Las contraseñas nunca se almacenarán en texto plano.
- El saldo de una cuenta no puede incumplir las reglas de negocio establecidas para su tipo.
- No pueden existir transacciones con importe igual a cero.
- Todas las operaciones deben quedar registradas.