###Problema 5: Casa de Fotografía 

**ROL DE USUARIOS:**

- Persona
- Cliente
- Empleado

**HISTORIAS DE USUARIOS:**
	
- Registrar Persona.
- Subir fotos
- Realizar pago
- Registrar retiro	


####Frente
- ID: **Registrar Persona**

- TITULO: Como persona quiero registrarme en el sistema para subir fotos

- REGLAS DE NEGOCIO:
	- email único

####Dorso
- Criterios de aceptación (Registrar Persona):

- _Escenario 1: Registro exitoso._
	- DADA la persona con "romero@gmail.com" con email único,
	- CUANDO la persona ingresa: "romero@gmail.com", "Sergio", "Romero", "Avellaneda", "chiquitoRomero", "1234"
	- ENTONCES el sistema informa que la persona fue registrada correctamente
	
- _Escenario 2: Registro fallido por email existente._ 
	- DADA la persona con "seb@gmail.com" con email ya existente en el sistema,
	- CUANDO la persona ingresa: "seb@gmail.com", "Sebastían", "Bataglia", "La Boca", "bataglia", "1234"
	- ENTONCES el sistema informa que el mail registrado ya existe.

___

####Frente
- ID: **Subir fotos.**

- TITULO: Como usuario quiero subir fotos para poder pagarlas

- REGLAS DE NEGOCIO: 
	- Haberse registrado en el sitio.
	- Máximo de 50 fotos.
	
####Dorso
- Criterios de aceptación (Subir fotos):

- _Escenario 1: Fotos subidas con éxito._
	- DADO que el usuario subió un máximo de fotos menor al permitido
	- CUANDO el usuario selecciona en "Subir fotos",
	- ENTONCES el sistema informa que las fotos fueron subidas con éxito.
	
- _Escenario 2: Fallo al subir fotos por superar la cantidad máxima permitida._
	- DADO que el usuario quiere ingresar una cantidad de fotos mayor a la permitida
	- CUANDO el usuario quiere ingresar la foto número 51,
	- ENTONCES el sistema informa que ya se subió la cantidad máxima permitida.
	
- _Escenario 3: Fallo al subir formato de imagen incorrecto._ 
	- DADO que el usuario quiere ingresar una imagen con formato incorrecto,
	- CUANDO el usuario selecciona "Subir foto",
	- ENTONCES el sistema informa que la imagen seleccionada no tiene el formato correcto.
___

####Frente
- ID: **Realizar pago.**

- TITULO: Como usuario quiero hacer el pago de las imágenes para retirarlas

- REGLAS DE NEGOCIO:
	- Tarjeta de crédito.
	- Validación a través de banco.

####Dorso
- Criterios de aceptación (Realizar Pago):

- _Escenario 1: Pago realizado con éxito._
	- DADO que el usuario intenta pagar con tarjeta de crédito, los datos corresponden a la tarjeta y la misma fue valida a traveś del sistema del banco,
	- CUANDO el usuario ingresa: "123123", "123", "Edwin Cardona" y selecciona "Pagar",
	- ENTONCES el sistema informa que el pago se ha realizado con éxito.
	
- _Escenario 2: Pago fallido por datos de tarjeta incorrectos._ 
	- DADO que el usuario intenta pagar con tarjeta de crédio, pero los datos no corresponden a la tarjeta
	- CUANDO el usuario ingresa: "234234", "234", "Felipe Melo" y selecciona "Pagar",
	- ENTONCES el sistema informa que los datos de la tarjeta son inválidos.
	
- _Escenario 2: Pago fallido por problemas con el sisteam del banco._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
___

####Frente
- ID: **Registrar retiro.**

- TITULO: Como empleado quiero registrar el retiro de las fotos

- REGLAS DE NEGOCIO: 
	- Registrar código único.
	
####Dorso
- Criterios de aceptación (Registrar retiro):
- _Escenario 1: Registro de retiro exitoso._
	- DADO que el empleado registra el código único de retiro de imágenes 
	- CUANDO el empleado registra el código "0303456" y la fecha de retiro "07/07/2007"
	- ENTONCES el sistema informa que el registro del retiro fue realizado con éxito.
	
- _Escenario 2: Registro de retiro fallido por código inválido._ 
	- DADO que el empleado registra un código único de retiro de imágenes inválido
	- CUANDO el empleado registra el código "030345" y la fecha de retiro "08/08/2008"
	- ENTONCES el sistema informa que el código único de retiro ingresado es incorrecto.
	
- _Escenario 3:._ 
	- DADO 
	- CUANDO
	- ENTONCES
