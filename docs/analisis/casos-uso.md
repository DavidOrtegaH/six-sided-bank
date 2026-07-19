# Casos de uso

---

## Actores

- Cliente
- Administrador
  
---

## CU-001 - Crear cuenta bancaria

### Descripción
La entidad bancaria "Six-Sided Bank" necesita que los clientes puedan abrir una cuenta en su sistema bancario para que puedan hacer uso de los servicios del banco.

### Actor
Cliente.

### Objetivos
El cliente puede abrir una nueva cuenta bancaria.

### Precondiciones
- El cliente debe existir.
- El cliente debe ser mayor de edad.
- El cliente debe ser humano.

### Flujo principal
1. El cliente solicita abrir una cuenta.
2. El cliente rellena formularios con todos los datos necesarios.
3. El sistema genera un número de cuenta único.
4. La cuenta es creada con un saldo inicial de 0€.
5. La aplicación informa al usuario que la cuenta se creó correctamente.

### Postcondiciones
- El cliente posee una cuenta en el sistema bancario.
- El cliente puede iniciar sesión en su cuenta del banco.

## CU-002 - Iniciar sesión

### Descripción
Los clientes y los administradores de Six-Sided-Bank que poseen una cuenta necesitan poder hacer login en la misma.

### Actores
Cliente y administrador.

### Objetivos
El cliente y el administrador pueden hacer login en su porpia cuenta.

### Precondiciones
- El cliente o administrador debe existir.
- El cliente o administrador debe ser humano.
- La cuenta no tiene que estar bloqueada o cerrada.

### Flujo principal
1. El cliente o administrador solicita iniciar sesión.
2. El cliente rellena formularios con nombre y contraseña.
3. El sistema valida el login.
4. La sesión se inicia correctamente.

### Postcondiciones
- El cliente o administrador tiene la sesión iniciada en su cuenta.


## CU-003 - Cerrar sesión

### Descripción
La entidad bancaria "Six-Sided Bank" deberá permitir a aquellos con la sesión iniciada hacer logout.

### Actores
Cliente y administrador.

### Objetivos
Los administradores y clientes son capaces de cerrar sesión en su cuenta.

### Precondiciones
- El cliente o administrador debe existir.
- El cliente o administrador debe ser humano.
- El cliente o administrador ha de tener la sesión iniciada.

### Flujo principal
1. El cliente o administrador pide cerrar sesión.
2. El sistema hace logout en esa cuenta.

### Postcondiciones
- El cliente o administrador tiene la sesión de su cuenta cerrada.
- El cliente o administrador no puede operar hasta que no inicie sesión nuevamente.

--- 
## CU-004 - Consultar datos de cuenta bancaria

### Descripción
El usuario necesita acceder los datos de su cuenta bancaria.

### Actor
Cliente.

### Objetivos
- El cliente tiene acceso a los datos de su cuenta bancaria.

### Precondiciones
- El cliente debe haber iniciado sesión.

### Flujo principal
1. El cliente pide conocer sus datos bancarios.
2. El sistema busca los datos de la cuenta de ese cliente en específico.
3. El sistema muestra los datos al cliente.

### Postcondiciones
- El cliente conoce sus datos bancarios.

---

## CU-005 - Enviar dinero

### Descripción
Los clientes tienen que poder mandar dinero a otras cuentas bancarias.

### Actor
Cliente.

### Objetivos
- El cliente puede transferir dinero de su cuenta bancaria a la cuenta de otro cliente.
- El dinero se resta de la cuenta del cliente que está enviando dinero.
- El dinero es sumado al saldo de la cuenta bancaria del cliente al que el dinero le es ingresado por parte del cliente emisor.

### Precondiciones
- Ambas cuentas estan activas.
- Las cuentas son distintas.
- El cliente emisor debe tener saldo en su cuenta igual o superior a la cantidad de dinero enviada.


### Flujo principal
1. El cliente emisor selecciona la opción de hacer transferencia.
2. El cliente emisor escribe la cantidad de dinero que desea mandar.
3. El cliente emisor indica el número de cuenta del cliente receptor.
4. El sistema valida la operación.
5. El dinero se resta de la cuenta del cliente lo está enviando.
6. El saldo de la cuenta del cliente receptor aumenta en la cantidad exacta enviada.
7. El sistema confirma que la tranferencia ha sido exitosa.


### Postcondiciones
- El cliente emisor tiene su saldo reducido en razón de la cantidad transferida
- El cliente receptor ve aumentado el dinero de su cuenta en la cantidad exacta que le ha sido enviada.
- Transferencia completada

---
## CU-006 - Consultar movimientos

### Descripción
Los clientes quieren consultar los movimientos bancarios, ya sean ingresos o pagos, relacionados con su cuenta bancaria.

### Actor
Cliente.

### Objetivos
- El cliente puede revisar el historial de transacciones relacionadas con su cuenta.

### Precondiciones
- La cuenta de el cliente debe existir.
- El cliente debe haber iniciado sesión.

### Flujo principal
1. El cliente exige ver el historial de movimientos de su cuenta.
2. El sistema recopila la lista de movimientos en los que su cuenta participó.
3. El sistema muestra la lista resultado al cliente.

### Postcondiciones
- El cliente visualiza los movimientos efectuados relacionados con su cuenta.

---
## CU-006 - Consultar la lista de clientes

### Descripción
Los administradores necesitan acceder a la lista de clientes para revisar los datos de los susodichos.

### Actor
Administrador.

### Objetivos
- El administrador es capaz de ver la lista de clientes.
- EL administrador puede conocer los datos de los clientes listados.

### Precondiciones
- El administrador debe haber iniciado sesión.
- Las cuenta de los clientes deben existir.

### Flujo principal
1. El administrador solicita la lista de clientes del banco.
2. El sistema confecciona la lista de clientes del banco recopilando todos los datos necesarios.
3. El sistema muestra la lista de clientes del banco al administrador.

### Postcondiciones
- La lista de clientes con sus datos es mostrada para la consulta del administrador.

---

## CU-007 - Bloquear cuenta

### Descripción
Los administradores necesitan poder bloquear las cuentas de los clientes por razones legales como procesos judiciales que exigan que una persona en particular tenga todas sus cuentas bloqueadas.

### Actor
Administrador.

### Objetivos
- El administrador es capaz de bloquearle la cuenta a un cliente.

### Precondiciones
- El administrador debe haber iniciado sesión.
- La cuenta de el cliente debe existir.
- La cuenta de el cliente no debe de estar ya bloqueada.

### Flujo principal
1. El administrador pide bloquear una cuenta.
2. El administrador introduce el número de la cuenta que ha de ser bloqueada.
3. El sistema encuentra la cuenta a a bloquear.
4. El sistema verifica que la cuenta no esté previamente bloqueada.
5. El sistema bloquea la cuenta del cliente
6. El sistema muestra al administrador que el bloqueo se realizó correctamente.

### Postcondiciones
- La cuenta del cliente está bloqueda, no puede iniciar sesión ni operar con ella.


---

## CU-008 - Borrar cuenta de clientes

### Descripción
Los administradores han de poder eliminar las cuentas de uno o varios clientes en caso de que la situación lo requiera.

### Actor
Administrador.

### Objetivos
- El administrador tiene la capacidad de borrar la/s cuenta/s de tipo cliente.
- El borrado de las cuentas ha de ser definitivo.

### Precondiciones
- El administrador debe haber iniciado sesión.
- Las cuenta de los clientes deben existir.

### Flujo principal
1. El administrador solicita borrar una o varias cuentas.
2. El administrador introduce el número o los números de la cuentas a borrar.
3. El administrador indica a que número de cuenta enviar el dinero que hubiera en las cuentas.
4. El sistema verifica que las cuenta a borrar existan.
5. El sistema recopila las cuentas que han de borrarse.
6. Se cancelan todas las operaciones pendientes de todas las cuentas a borrar.
7. El dinero que hubiera se tranfiere a la cuenta que señaló el administrador.
8. El sistema marca como borrada la cuenta en la base de datos.
9. Sí el cliente no tiene más cuentas también se marca como borrado en la base de datos.
10. El sistema muestra al administrador que el borrado se efectuó con éxito.

### Postcondiciones
- La cuenta del cliente se borró.
- La cuenta del cliente no aparece en la información del cliente.
- Sí el cliente no tenía más cuentas es borrado también.
- El dinero que había en las cuentas borradas se sumó al saldo de la cuenta elegida por el administrador.

