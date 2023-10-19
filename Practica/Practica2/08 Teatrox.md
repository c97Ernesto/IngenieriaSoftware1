### Problema 8: Teatro.

**ROL DE USUARIOS:**
	
- Empleado
- Persona
- Usuario
- Vendedor

**HISTORIAS DE USUARIOS:**

- Mostrar Grilla.

- Reservar Entradas. 

- Comprar Entradas via Web.

- Comprar Entradas Personalmente.

- Retirar Entradas Reservadas.

- Retirar Entradas Compradas.

- Pagar con Tarjeta.


#### Frente
- ID: **Mostrar Grilla.**

- TITULO: Como usuario quiero seleccionar una opción para comprar una entrada.

- REGLAS DE NEGOCIO: 

#### Dorso
- Criterios de aceptación (Seleccionar opción):
- _Escenario 1: Muestra de funciones Exitosa._
	- DADO que hay opciones disponibles,
	- CUANDO el usuario selecciona la opción de "Mostrar Obras" 
	- ENTONCES el sistema muestra una grilla con las funciones disponibles.
	
- _Escenario 2: Muestra de funciones Fallida porque no hay opciones disponibles._ 
	- DADO que no hay opciones disponibles
	- CUANDO el usuario selecciona la opción de "Mostrar Obras" 
	- ENTONCES el sistema informa que no hay opciones disponibles.

___ 

#### Frente
- ID: **Reservar Entradas.**

- TITULO: Como Empleado quiero hacer la reserva de entradas para que puedan comprarla

- REGLAS DE NEGOCIO: 
	- Solo se podrá reservar hasta dos entradas.


#### Dorso
- Criterios de aceptación (Reservar Entradas):

- _Escenario 1: Reservación exitosa._
	- DADO que en la grilla está la función de la persona y la persona con DNI "0303456" no posee entradas,
	- CUANDO el Empleado ingresa: "Obra737", "23/12/23", "0303456", "Juan", seleccionando la obra y haciendo la reserva de 2 entradas
	- ENTONCES el sisteama informa que se reservaron las entradas correctamente y las registra en el sistema.
	
- _Escenario 2: Reservación fallida por exceder el límite de entradas._ 
	- DADO que en la grilla se encuentra la función de la persona y la persona con DNI "0303456" posee una entrada,
	- CUANDO el Empleado ingresa: "Obra737", "23/12/23", "0303456", "Juan", seleccionando la obra y haciendo la reserva de 2 entradas. 
	- ENTONCES el sistema informa que el DNI "0303456" excede el límite de entradas que puede reservar.
	
- _Escenario 3: Reservación fallida por no encontrarse la obra de la persona._ 
	- DADO que en la grilla no se encuentra la obra de la persona y la persona con "0303456" no posee entradas,
	- CUANDO el Empleado ingresa: "Manuelita", "23/12/23", "0303456", "Juan".
	- ENTONCES el sistema informa que no hay funciones con ese nombre disponibles.

	
___


#### Frente
- ID: **Comprar Entradas via Web.**

- TITULO: Como Usuario quiero elegir una obra para comprar entradas.

- REGLAS DE NEGOCIO: 
	- Tarjeta autorizada
	
	
#### Dorso
- Criterios de aceptación (Comprar Entradas via Web):

- _Escenario 1: Compra exitosa._
	- DADO que se encuentra la obra del usuario, hay suficientes lugares y el usuario tiene la tarjeta autorizada.
	- CUANDO el Usuario ingresa: "Manuelita2", "0303456", 7, elige su obra y selecciona la opción de "Pagar".
	- ENTONCES el sistema registra el pago y emite un código de compra.
	
- _Escenario 2: Compra Fallida por no haber lugares suficientes._
	- DADO que se encuentra la obra del usuario, pero no hay suficientes lugares.
	- CUANDO el Usuario ingresa: "Manuelita3", "0303456", 7, elige su obra y selecciona la opción de "Pagar".
	- ENTONCES el sistema informa no hay suficientes lugares disponibles.
	
- _Escenario 3: Compra Fallida por datos de tarjeta de crédito incorrectos._ 
	- DADO que se encuentra la obra del usuario, hay suficientes lugares, pero el usuario no tiene la tarjeta autorizada.
	- CUANDO el Usuario ingresa: "Obra737", "0303456", 7, elige su obra y selecciona la opción de "Pagar".
	- ENTONCES el sistema informa que la tarjeta no se encuentra autorizada.

- _Escenario 4: Compra Fallida por no encontrar obra._
	- DADO que no se encuentra la función del usuario, tiene la tarjeta autorizada para pagar,
	- CUANDO el Usuario ingresa: "Manuelita3", "0303456", 7
	- ENTONCES el sistema informa que no hay obra con ese nombre.
___

#### Frente
- ID: **Comprar Entradas Personalmente.**

- TITULO: Como Vendedor quiero vender entradas para 

- REGLAS DE NEGOCIO: 
	- Pagar con tarjeta de crédito

	
#### Dorso
- Criterios de aceptación ():
- _Escenario 1: Compra exitosa._
	- DADO que se encuentra la obra del usuario, hay suficientes lugares y el usuario tiene la tarjeta autorizada.
	- CUANDO el Empleado ingresa: "Manuelita2", "0303456", 7, elige la obra y selecciona la opción de "Pagar".
	- ENTONCES el sistema registra el pago e imprime las entradas.
	
- _Escenario 2: Compra Fallida por no haber lugares suficientes._
	- DADO que se encuentra la obra del usuario, pero no hay suficientes lugares.
	- CUANDO el Empleado ingresa: "Manuelita3", "0303456", 7, elige la obra y selecciona la opción de "Pagar".
	- ENTONCES el sistema informa no hay suficientes lugares disponibles.
	
- _Escenario 3: Compra Fallida por datos de tarjeta de crédito incorrectos._ 
	- DADO que se encuentra la obra del usuario, hay suficientes lugares, pero el usuario no tiene la tarjeta autorizada.
	- CUANDO el Empleado ingresa: "Obra737", "0303456", 7, elige la obra y selecciona la opción de "Pagar".
	- ENTONCES el sistema informa que la tarjeta no se encuentra autorizada.

- _Escenario 4: Compra Fallida por no encontrar obra._
	- DADO que no se encuentra la función del usuario, tiene la tarjeta autorizada para pagar,
	- CUANDO el Empleado ingresa: "Manuelita3", "0303456", 7.
	- ENTONCES el sistema informa que no hay obra con ese nombre.

___

#### Frente
- ID: **Retirar Entradas Reservadas.**

- TITULO: Como Empleado quiero vender las entradas para que puedan retirarlas.

- REGLAS DE NEGOCIO: 
	- Pagar con tarjeta de crédito
	
#### Dorso
- Criterios de aceptación (Retirar Entradas Reservadas):
- _Escenario 1: Retiro de las entradas Exitoso._
	- DADO que la persona posee entradas reservadas, no están caducadas y tiene una tarjeta autorizada, 
	- CUANDO el Empleado ingresa: "Juan", "123123" y seleccion "Pagar".
	- ENTONCES el sistema registra el pago e imprime las entradas reservadas.
	
- _Escenario 2: Retiro de las entradas Fallido por no tener entradas._ 
	- DADO que la persona no posee entradas reservadas,
	- CUANDO el Empleado ingresa: "Juan", "123123" y seleccion "Pagar".
	- ENTONCES el sistema informa que la persona no posee entradas.

- _Escenario 3: Retiro de las entradas Fallido por tener entradas caducadas._ 
	- DADO que la persona posee entradas reservadas pero las mismas se encuentan caducadas,
	- CUANDO el Empleado ingresa: "Juan", "123123" y seleccion "Pagar".
	- ENTONCES el sistema informa que las entradas posee entradas caducadas.
	
- _Escenario 4: Retiro de las entradas Fallido por tarjeta no autorizada._ 
	- DADO que la persona posee entradas reservadas, no están caducadas pero la tarjeta no está autorizada, 
	- CUANDO el Empleado ingresa: "Juan", "123123" y seleccion "Pagar".
	- ENTONCES el sistema informa que los datos de la tarjeta son incorrectos.
	
___

#### Frente
- ID: **Retirar Entradas Compradas.**

- TITULO: Como vendedor quiero verificar código para imprimir las entradas.

- REGLAS DE NEGOCIO:
	- Pagar con tarjeta de crédito
	
	
#### Dorso
- Criterios de aceptación (Comprar entrada):
- _Escenario 1: Compra Exitosa._
	- DADA la persona que llega con un código de compra válido,
	- CUANDO el Vendedor ingresa: "222", y selecciona "Imprimir"
	- ENTONCES el sistema imprime las entradas correspondientes.
	
- _Escenario 2: Compra Fallida por código de compra inválido._ 
	- DADA la persona que llega con código de compra inválido,
	- CUANDO la persona ingresa: "111", y selecciona "Imprimir"
	- ENTONCES el sistema informa que el código de compra es incorrecto.

___

#### Frente
- ID: **Pagar con Tarjeta.**

- TITULO: Como Usuario quiero pagar con tarjeta para comprar entradas.

- REGLAS DE NEGOCIO:
	
	
#### Dorso
- Criterios de aceptación (Pagar con Tarjeta):
- _Escenario 1: Pago exitoso._
	- DADO que la persona hizo la correspondiente elección de las entradas, la conexión con el banco es correcta, los datos de la tarjeta son correctos y la tarjeta tiene saldo
	- CUANDO se ingresa: "234234", "22/10/2023", "123",
	- ENTONCES el sistema autoriza la tarjeta.
	
- _Escenario 2: Pago Fallido por error en al conexión con el banco._ 
	- DADO que el usuario hizo la correspondiente elección de las entradas, pero falla la conexión con el banco.
	- CUANDO se ingresan los datos de la tarjeta,
	- ENTONCES el sistema informa que no se puede establecer la conexión con el banco.
		
- _Escenario 3: Pago Fallido por número de tarjeta incorrecto._ 
	- DADO que el usuario hizo la correspondiente elección de las entradas, la conexión con el banco es correcta, pero los datos de la tarjeta son incorrectos.
	- CUANDO se ingresa: "23423", "22/10/2023", "123",
	- ENTONCES el sistema informa que el número de tarjeta es incorrecto.

- _Escenario 4: Pago Fallido por saldo insuficiente._ 
	- DADO que el usuario hizo la correspondiente elección de las entradas, la conexión con el banco es correcta, los datos de la tarjeta son correctos, pero no posee fondos suficientes.
	- CUANDO se ingresa: "234234", "22/10/2023", "123",
	- ENTONCES el sistema informa que la tarjeta no posee saldo suficiente.
