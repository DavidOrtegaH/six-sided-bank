# Requisitos funcionales

## Gestión de cuentas

#### RF-001. 
El sistema deberá permitir a un cliente abrir una nueva cuenta bancaria.

#### RF-002. 
El sistema deberá generar automáticamente un número de cuenta único para cada cuenta creada.

#### RF-003. 
El sistema deberá crear las nuevas cuentas con un saldo inicial de 0 €.

---

## Autenticación

#### RF-004.
El sistema deberá permitir a clientes y administradores iniciar sesión mediante credenciales válidas.

#### RF-005.
El sistema deberá impedir el acceso a cuentas bloqueadas o eliminadas.

#### RF-006. 
El sistema deberá permitir cerrar la sesión iniciada.

## Consulta de información

#### RF-007. 
El sistema deberá permitir a un cliente consultar los datos de sus cuentas bancarias.

#### RF-008. 
El sistema deberá mostrar únicamente la información perteneciente al cliente autenticado.

#### RF-009. 
El sistema deberá permitir consultar el historial de movimientos de una cuenta bancaria.

#### RF-010. 
El historial deberá incluir todos los ingresos y transferencias relacionados con la cuenta.

---

## Transferencias

#### RF-011. 
El sistema deberá permitir realizar transferencias entre cuentas activas.

#### RF-012. 
El sistema deberá comprobar que las cuentas origen y destino sean distintas.

#### RF-013. 
El sistema deberá comprobar que la cuenta emisora dispone de saldo suficiente.

#### RF-014. 
El sistema deberá confirmar el éxito de la transferencia al finalizar la operación.

---

## Administración

#### RF-015. 
El sistema deberá permitir al administrador consultar la lista de clientes registrados.

#### RF-016. 
El sistema deberá permitir al administrador consultar los datos de cualquier cliente.

#### RF-017. 
El sistema deberá permitir bloquear cuentas de clientes.

#### RF-018. 
El sistema deberá permitir desbloquear cuentas previamente bloqueadas.

#### RF-019. 
El sistema deberá permitir eliminar cuentas de clientes.

#### RF-020. 
Antes de eliminar una cuenta, el sistema deberá cancelar todas las operaciones pendientes.

#### RF-021. 
Antes de eliminar una cuenta, el sistema deberá transferir el saldo restante a otra cuenta indicada por el administrador.

#### RF-022. 
Si un cliente no posee más cuentas, el sistema deberá marcar también dicho cliente como eliminado.
  
## Auditoría

#### RF-023. 
El sistema deberá registrar todas las operaciones relevantes (inicio de sesión, transferencias, bloqueos, eliminaciones y restauraciones de cuentas).

---

# Requisitos no funcionales
## Seguridad

#### RNF-001. 
El sistema deberá aplicar control de acceso basado en roles (CLIENTE y ADMINISTRADOR).

#### RNF-002. 
Las contraseñas deberán almacenarse cifradas.

#### RNF-003. 
Las sesiones deberán finalizar correctamente tras el cierre de sesión.

---

## Integridad de datos

#### RNF-004. 
Todas las transferencias deberán ejecutarse como una única transacción atómica.

#### RNF-005. 
El sistema deberá garantizar la consistencia de los saldos bancarios.

#### RNF-005.
El sistema solo usa euros (€) como divisa para simplificar

---

## Rendimiento

#### RNF-007. 
Las consultas de saldo y datos de cuenta deberán responder en menos de 2 segundos en condiciones normales.

#### RNF-008. 
Las operaciones de transferencia deberán completarse en menos de 40 segundos sin comprometer la consistencia de los datos.

---

## Mantenibilidad

#### RNF-009. 
La aplicación deberá desarrollarse siguiendo una arquitectura hexagonal.

#### RNF-010. 
La lógica de negocio deberá estar desacoplada de la infraestructura.

#### RNF-011. 
Los componentes deberán seguir el principio de responsabilidad única (SRP).

---

## Escalabilidad

#### RNF-012. 
La arquitectura deberá permitir sustituir la base de datos o los mecanismos de persistencia sin modificar el dominio.

---

## Fiabilidad

#### RNF-013. 
Ante un fallo durante una transferencia, la operación deberá revertirse completamente para evitar inconsistencias.