###Problema 8: Teatro

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
	- DADO que hay opciones disponibles y lugares disponibles
	- CUANDO el usuario selecciona la opción, ingresa su DNI "123123", la cantidad de lugares que desea "3", y selecciona la opción "Pagar",
	- ENTONCES el sistema lo redirecciona al pago.
	
- _Escenario 2: Selección fallida porque no hay opciones disponibles._ 
	- DADO que no hay opciones disponibles
	- CUANDO el usuario quiere seleccionar, 
	- ENTONCES el sistema informa que no hay opciones disponibles.
	
- _Escenario 2: Selección fallida porque la grilla no muestra lugares disponibles._ 
	- DADO que hay opciones disponibles, pero no hay lugares disponibles
	- CUANDO el usuario selecciona una opción, ingresa su DNI "123123"
	- ENTONCES el sistema informa que no hay lugares disponibles

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
- ID: **Comprar entrada via web.**

- TITULO: Como vendedor quiero solicitar los datos para poder imprimir las entradas

- REGLAS DE NEGOCIO: 
	- Pagar con tarjeta de crédito
	
	
####Dorso
- Criterios de aceptación (Comprar entrada):
- _Escenario 1: Compra exitosa._
	- DADO que el vendedor le pide los datos de la función al cliente
	- CUANDO 
	- ENTONCES el sistema imprime las entradas.
	
- _Escenario 2: Compra fallida por datos de tarjeta incorrectos._ 
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 3: Compra fallida por datos personales incorrectos._ 
	- DADA 
	- CUANDO
	- ENTONCES

___

####Frente
- ID: **Retirar entrada.**

- TITULO: Como empleado quiero registrar el retiro de las entradas reservadas previamente para que puedan ver la obra

- REGLAS DE NEGOCIO: 
	- Poseer entradas reservadas y que no estén caducadas.
	
####Dorso
- Criterios de aceptación (Retirar entrada):
- _Escenario 1: Retiro exitoso._
	- DADO que el empleado solicita nombre y dni del espectador ,
	- CUANDO el empleado ingresa: "Juan Carlos", "567567",
	- ENTONCES el sistema informa que la persona posee entradas válidas.
	
- _Escenario 2: Retiro fallido porque la persona no posee entradas reservadas._ 
	- DADO que el empleado solicita nombre y DNI del espectador,
	- CUANDO el empleado ingresa: "Roberto Carlos", "234423",
	- ENTONCES el sistema informa que la persona no posee entradas.

- _Escenario 2: Retiro fallido porque la persona posee entradas caducadas._ 
	- DADO que el empleado solicita nombre y DNI del espectador,
	- CUANDO el empleado ingresa: "Roberto Carlos", "234423",
	- ENTONCES el sistema informa que la persona posee entradas caducadas.
___

####Frente
- ID: **Verificar Código.**

- TITULO: Como Vendedor quiero verificar el código de compra para imprimir las entradas correspondientes.

- REGLAS DE NEGOCIO: 
	- Persona llega con código de compra.
	
####Dorso
- Criterios de aceptación (Verificar Código):
- _Escenario 1: Verificación exitosa._
	- DADO que el empleado le pide el código de verificación a la persona,
	- CUANDO éste ingresa "0303456",
	- ENTONCES el sistema informa que el código es correcto y se imprimen las entradas correspondientes.
	
- _Escenario 2: Verificación fallida por código incorrecto._ 
	- DADO que el empleado le pide el código de verificación a la persona,
	- CUANDO éste ingresa "8989",
	- ENTONCES el sistema informa que el código ingresado es incorrecto.

___
