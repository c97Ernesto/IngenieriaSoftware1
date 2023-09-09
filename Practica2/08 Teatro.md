###Problema 6: Biblioteca

**ROL DE USUARIOS:**

- Usuario.
- Vendedor.
- Empleado.

**HISTORIAS DE USUARIOS:**

- Seleccionar opción.
- Realizar pago.
- Comprar entrada.
- Retirar entradas.
- Verificar código.

####Frente
- ID: **Seleccionar opción.**

- TITULO: Como usuario quiero seleccionar una opción para comprar una entrada.

- REGLAS DE NEGOCIO: 
	- El pago se realiza con tarjeta de crédito.


####Dorso
- Criterios de aceptación (Seleccionar opción):
- _Escenario 1: Selección exitosa._
	- DADO que se encuentran lugares disponibles
	- CUANDO el usuario ingresa: "123123", 5,
	- ENTONCES el sistema lo redirecciona al pago.
	
- _Escenario 2: Selección fallida por DNI incorrecto._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Selección fallida porque la grilla no muestra lugares disponibles._ 
	- DADO 
	- CUANDO
	- ENTONCES

___


####Frente
- ID: **Realizar pago.**

- TITULO: Como usuario quiero realizar el pago para poder comprar entradas.

- REGLAS DE NEGOCIO: 
	- Tener tarjeta de crédito
	
	
####Dorso
- Criterios de aceptación (Realizar Pago):
- _Escenario 1: Pago realizado con éxito._
	- DADO que la autorización del banco fue ralizada con éxito.
	- CUANDO el usuario ingresa "234234", "03/03/03", "234",
	- ENTONCES el sistema informa que el pago fue ralizado con éxito y emite un código de compra.
	
- _Escenario 2: Pago fallido por nro de tarjeta incorrecto._ 
	- DADA 
	- CUANDO
	- ENTONCES

- _Escenario 3: Pago fallido por tarjeta vencida._ 
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Pago fallido por código de seguridad incorrecto._ 
	- DADA 
	- CUANDO
	- ENTONCES
___

####Frente
- ID: **Comprar entrada.**

- TITULO: Como vendedor quiero solicitar los datos para poder imprimir las entradas

- REGLAS DE NEGOCIO: 
	
####Dorso
- Criterios de aceptación (Comprar entrada):
- _Escenario 1: Compra exitosa._
	- DADO que el vendedor le pide los datos de la función al cliente
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Compra fallida por datos de tarjeta incorrectos._ 
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 3: Compra fallida por datos incorrectos._ 
	- DADA 
	- CUANDO
	- ENTONCES

___

####Frente
- ID: **.**

- TITULO:

- REGLAS DE NEGOCIO: 

	
####Dorso
- Criterios de aceptación ():
- _Escenario 1: ._
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADA 
	- CUANDO
	- ENTONCES

___
