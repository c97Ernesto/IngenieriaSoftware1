### Problema 1: Alquiler de mobiliario.
Suponga que trabaja en una consultora la cual ha sido recientemente contactada por una empresa de alquiler de mobiliario para eventos para la realización de una app.
De las diferentes entrevistas se ha obtenido la siguiente información:

El gerente nos dijo que resulta fundamental tener una aplicación móvil que nos permita manejar la agenda de la empresa, sabiendo qué disponibilidad tenemos y permitiendo que nuestros clientes alquilen a través de la app. Para esta primera versión de la app, el gerente nos pidió que sea posible dar de alta los diferentes mobiliarios, así como la posibilidad de que los usuarios puedan realizar una reserva de alquiler desde sus dispositivos. Para el detalle de cómo se realiza la carga de los muebles, el gerente nos sugirió hablar con el encargado del departamento de mobiliario. El encargado de mobiliario nos comentó que de cada mueble se debe cargar código de inventario, tipo de mueble, fecha de creación, fecha de último mantenimiento, estado (libre, de baja, alquilado) y el precio de alquiler. Además, no pueden existir códigos repetidos y por
el contrato de la franquicia, el precio debe cargarse en dólares. Para que el encargado pueda dar de alta el mobiliario debe autenticarse en el sistema. El registro de los usuarios de carga no debe modelarse.

El encargado del departamento de alquileres no comentó acerca de las reservas de los alquileres. Por una política comercial de la marca una reserva tiene que incluir como mínimo 3 muebles. La reserva debe tener una fecha, lugar del evento, cantidad de días y mobiliario junto a su cantidad. Para realizar una reserva se debe abonar el 20% del total del alquiler. El pago de la reserva se realiza únicamente con tarjeta de crédito validando número de tarjeta y fondos a través de un servicio del banco. Luego de efectuado el pago, se emite un número de reserva único que será luego utilizado por el
cliente para hacer efectivo el alquiler.

**ROL DE USUARIOS:**

- Encargado de mobiliario.
- Clientes

**HISTORIAS DE USUARIOS:**

- Cargar Mueble.
- Realizar reserva.
- Realizar Pago.

___

#### Frente
- ID: Cargar Mueble

- TITULO: Como encargado quiero dar de alta un mueble para alquilarlo.

- REGLAS DE NEGOCIO:
	- No debe existir previamente el código del mueble a cargar.
	
**Dorso**
- Criterios de aceptación (Cargar Mueble):

- _Escenario 1: Carga de Mueble exitosa_
	- DADO que el código de inventario "123123" no se encuentra en el sistema, 
	- CUANDO el encargado ingresa: "123123", "mesa", "1/1/2000", "1/1/2020", "libre", "20", y selecciona "Cargar Mueble".
	- ENTONCES el sistema realiza la carga del mueble.
	
- _Escenario 2: Carga de Mueble fallida por código existente_
	- DADO que el código de inventario "123123" se encuentra en el 	sistema, 
	- CUANDO el encargado ingresa: "123123", "mesa pin pong", "1/1/2001", "1/1/2020", "libre", "30", y selecciona "Cargar Mueble".
	- ENTONCES el sistema informa que el Código de Mueble ingresado ya 	existe.

___
	
#### Frente
- ID: Realizar reserva

- TITULO: Como cliente quiero realizar una reserva para el alquiler de muebles.

- REGLAS DE NEGOCIO:
	- Una reserva tiene que incluir como mínimo 3 muebles

**Dorso**
- Criterios de aceptación (Realizar reserva):

- _Escenario 1: Se realiza la reserva con éxito_
	- DADO que el usuario quiere hacer la reserva de 4 muebles, superando el mínimo pedido,
	- CUANDO el usuario ingresa "2/2/2022", "Mi casa", "2", "4"
	- ENTONCES el sistema aprueba la reserva y redirige al usuario a realizar el pago con tarjeta de crédito.
	
- _Escenario 2: Falla la reserva por cantidad mínima de muebles no superada_
	- DADO que el usuario quiere hacer una reserva de 2 muebles, no superando el mínimo de 3,
	- CUANDO el usuario ingresa "2/2/2022", "Mi casa", "2", "2"
	- ENTONCES el sistema informa que la cantidad mínima de muebles no fue superada.
	
___

#### Frente
- ID: Realizar Pago.

- TITULO: Como cliente quiero realizar el pago con tarjeta de crédito para reservar los muebles.

- REGLAS DE NEGOCIO:
	- Validar tarjeta de crédito.
	- Abonar el 20% del total de los muebles.
	
**Dorso**
- Criterios de aceptación (Realizar Pago):

- _Escenario 1: Pago realizado con éxito_
	- DADO que el cliente hizo una reserva exitosa, la conexión con el banco funciona correctamente e ingreso una tarjeta de crédito con número "234234" válida con fondos suficientes, y además abona el 20% del total de los muebles.
	- CUANDO el cliente ingresa el número de tarjeta "234234" y selecciona "pagar",
	- ENTONCES el sistema informa que el pago se hizo correctamente.
	
- _Escenario 2: Pago fallido por no tener targeta de crédito válida_
	- DADO que el cliente hizo una reserva exitosa, la conexión con el banco funciona correctamente , ingresó una número de tarjeta "23423" inválido, y además abona el 20% del total de los muebles.
	- CUANDO el cliente ingresa el número de tarjeta "23423" y selecciona "pagar",
	- ENTONCES el sistema informa que el número ingresado no corresponde a una tarjeta de crédito válida.
	
- _Escenario 3: Pago fallido por no abonar el 20% del total de los muebles_
	- DADO que el cliente hizo una reserva exitosa, la conexión con el banco funciona correctamente ingresó una número de tarjeta "23423" válido con fondos suficiente, pero no abonó 20% del total de los muebles. 
	- CUANDO el cliente ingresa el número de tarjeta "234234" y selecciona "pagar",
	- ENTONCES el sistema informa que no se abonó el 20% de los muebles.
	
- _Escenario 4: Pago fallido por no tener fondos suficiente_
	- DADO que el cliente hizo una reserva exitosa, la conexión con el banco funciona correctamente e ingresó una número de tarjeta "23423" válido con fondos insufiecientes, abonando el 20% del total de los muebles.
	- CUANDO el cliente ingresa el número de tarjeta "234234" y selecciona "pagar",
	- ENTONCES el sistema informa que la tarjeta de crédito no tiene fondos suficientes.
	
