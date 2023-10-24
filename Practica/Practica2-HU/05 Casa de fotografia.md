### Problema 5: Casa de Fotografía.

**ROL DE USUARIOS:**

- Persona
- Usuario
- Empleado

**HISTORIAS DE USUARIOS:**
	
- Subir Fotos.
- Calcular Pago.
- Realizar Pago.
- Registrar Retiro.
- Registrar Persona.
- Iniciar Sesión.
- Cerrar Sesión.

___

#### Frente
- ID: **Subir fotos.**

- TITULO: Como usuario quiero subir fotos para poder pagarlas

- REGLAS DE NEGOCIO: 
	- Máximo de 50 fotos.
	
#### Dorso
- Criterios de aceptación (Subir fotos):

- _Escenario 1: Fotos subidas con Éxito._
	- DADO que el usuario lleva cargado una cantidad de fotos menor al máximo permitido,
	- CUANDO el usuario selecciona en "Subir foto",
	- ENTONCES el sistema informa que la foto fue subida con éxito.
	
- _Escenario 2: Fallo al subir fotos por llegar a la cantidad máxima permitida._
	- DADO que el Usuario llegó a la carga máximo de imágenes permitidas,
	- CUANDO el usuario quiere ingresar la imagen número 51,
	- ENTONCES el sistema informa que no puede subir más imágenes por cargar el máximo permitido.
	
___

#### Frente
- ID: **Calcular Pago.**

- TITULO: Como Usuario quiero calcular el costo de las fotos subidas para obtener el código de retiro.

- REGLAS DE NEGOCIO: 
	- Cargar imágenes


**Dorso**

- Criterios de aceptación ():

- _Escenario 1: Calculo Exitoso._
	- DADO que se hizo la correspondiente carga de imágenes,
	- CUANDO el usuario selecciona la opción de "Calcular Costo",
	- ENTONCES el sistema calcula el monto de las imágenes cargas y redirige al usuario al Pago con Tarjeta
	
- _Escenario 2: Calculo Fallido por no haber imágenes._ 
	- DADO que no se cargó ninguna imagen,
	- CUANDO el usuario selecciona la opción de "Calcular Costo"
	- ENTONCES el sistema informa que no hay imágenes cargadas.
	
___

#### Frente
- ID: **Realizar Pago.**

- TITULO: Como usuario quiero hacer el pago de las imágenes para retirarlas

- REGLAS DE NEGOCIO:
	- Pagar con tarjeta.

#### Dorso
- Criterios de aceptación (Realizar Pago):

- _Escenario 1: Pago realizado con éxito._
	- DADO que la conexión con el banco es exitosa, y el número de tarjeta pertenece a una tarjeta válida,
	- CUANDO el usuario ingresa: "123123", "123", "Edwin Cardona" y selecciona "Pagar".
	- ENTONCES el sistema informa que el pago se ha realizado con éxito.
	
- _Escenario 2: Pago Fallido por número de tarjeta la tarjeta incorrectos._ 
	- DADO que la conexión con el banco es exitosa, pero el número de la tarjeta es inválido,
	- CUANDO el usuario ingresa: "234234", "234", "Felipe Melo" y selecciona "Pagar".
	- ENTONCES el sistema informa que el número de la tarjeta es inválido.
	
- _Escenario 2: Pago Fallido por problemas con conexión del banco._ 
	- DADO que falló la cionexión con el banco,
	- CUANDO el usuario ingresa: "0303456", "132", "Ramos Mejía" y selecciona "Pagar".
	- ENTONCES el sistema informa que falló la conexión con el banco.
	
___

#### Frente
- ID: **Registrar retiro.**

- TITULO: Como empleado quiero registrar el retiro para entrgar las fotos.

- REGLAS DE NEGOCIO: 
	- Registrar código único.
	
**Dorso**

- Criterios de aceptación (Registrar retiro):

- _Escenario 1: Registro de retiro exitoso._
	- DADO que el empleado registra el código único de retiro de imágenes 
	- CUANDO el empleado registra el código "0303456" y la fecha de retiro "07/07/2007", y selecciona la opción de "Registrar Retiro".
	- ENTONCES el sistema informa que el registro del retiro fue realizado con éxito y registra la fecha 07/07/2007.
	
- _Escenario 2: Registro de retiro fallido por código inválido._ 
	- DADO que el empleado registra un código único de retiro de imágenes inválido
	- CUANDO el empleado registra el código "030345" y la fecha de retiro "08/08/2008", y selecciona la opción de "Registrar Retiro".
	- ENTONCES el sistema informa que el código único de retiro ingresado es incorrecto.
	

#### Frente
- ID: **Registrar Persona**

- TITULO: Como persona quiero registrarme en el sistema para subir fotos.

- REGLAS DE NEGOCIO:
	- Email único.

**Dorso**

- Criterios de aceptación (Registrar Persona):

- _Escenario 1: Registro exitoso._
	- DADO el mail "romero@gmail.com" que no se encuentra registrado en el sistema,
	- CUANDO la persona ingresa: "romero@gmail.com", "Sergio", "Romero", "Avellaneda", "chiquitoRomero", "1234", y selecciona la opción de "Registrarse".
	- ENTONCES el sistema informa que la persona fue registrada correctamente.
	
- _Escenario 2: Registro fallido por email existente._ 
	- DADO que el mail "seb@gmail.com" se encuentra registrado en el sistema,
	- CUANDO la persona ingresa: "seb@gmail.com", "Sebastían", "Bataglia", "La Boca", "bataglia", "1234", y selecciona la opción de "Registrarse".
	- ENTONCES el sistema informa que el mail ingresado ya existe.

___

#### Frente
- ID: **Iniciar Sesión.**

- TITULO: 

- REGLAS DE NEGOCIO: 
	- 


**Dorso**

- Criterios de aceptación ():

- _Escenario 1:._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: ._ 
	- DADO 
	- CUANDO
	- ENTONCES

___

#### Frente
- ID: **Cerrar Sesión.**

- TITULO: 

- REGLAS DE NEGOCIO: 
	- 


**Dorso**

- Criterios de aceptación ():

- _Escenario 1:._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: ._ 
	- DADO 
	- CUANDO
	- ENTONCES

