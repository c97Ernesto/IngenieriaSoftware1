### Problema 9: Pago electrónico.

Se desea modelar un sistema de pago electrónico de impuestos y servicios en efectivo.

Cuando un cliente llega para realizar un pago, el empleado o el gerente de la sucursal ingresa el código de pago electrónico y el sistema se conecta con la central de cobro para recuperar los datos de la factura (empresa, nro de cliente, 1era fecha de vencimiento, 2da fecha de vencimiento, recargo, y monto original). Una vez recuperados los datos, el sistema debe verificar los vencimientos para determinar el monto a cobrar. Teniendo esto en cuenta, cuando el 2do vencimiento está vencido se debe informar que la factura no se puede cobrar por dicho motivo. Cuando el 1er vencimiento está vencido hay que aplicar el recargo al monto original. Si la factura no está vencida, se cobra el monto original.

Una vez al día, el gerente de la sucursal debe registrar en la central de cobros los pagos que hicieron los clientes. Para esto el sistema requiere la clave maestra y de ser correcta, recupera las transacciones de los impuestos y servicios cobrados en el día, se conecta a la central de cobro y se las envía. Cuando la central confirma la recepción exitosa, el sistema las registra como enviadas. Este último paso es importante porque no deben enviarse dos veces las transacciones. Si el gerente intenta enviar una segunda vez, el sistema no debe permitirlo. 

Finalmente el Gerente puede ver las estadísticas de los impuestos y servicios cobrados. Para esto, se ingresa la clave maestra, un rango de fechas sobre las cuales debe calcularse las estadísticas y el sistema debe mostrar los montos y la cantidad de cobros realizados, agrupando por empresa. 

Tenga en cuenta que cada vez que el sistema debe conectarse a la central, debe enviarle un token (código que identifica al sistema). Una vez que la central valida el token, el sistema envía el requerimiento para recuperar los datos de la factura o el requerimiento para registrar los pagos del día según corresponda.

**ROL DE USUARIOS:**

- Empleado
- Gerente

 

**HISTORIAS DE USUARIOS:**

- Conectar a la Central.

- Recuperar Factura.

- Calcular Cobro.



#### Frente
- ID: **Conectar a la Central.**

- TITULO: Como Empleado o Gerente quiero conectarme con la Central de Cobros para recuperar datos o registrar pagos.

**Dorso**

- Criterios de aceptación (Conectar a la Central):
- _Escenario 1: Conexión con la Central Exitosa para la recuperación de datos de una factura._
	- DADO que el código de factura es correcto
	- CUANDO el Empleado o Gerente selecciona "Conectarse a la Central"
	- ENTONCES el sistema se conecta con la central de cobros.
	
- _Escenario 2: Conexión con la Central Exitosa para la recuperación de los cobros del día._ 
	- DADO que el token único del sistema es correcto y hay conexión con la Central de Cobros,
	- CUANDO el Gerente selecciona "Obtener cobros".
	- ENTONCES el sistema se conecta con la central de cobros y envía los cobros del día.

	
- _Escenario 3: Conexión con la Central Fallida por token vencido._ 
	- DADO que el token único del sistema está vencido,
	- CUANDO el Empleado o Gerente selecciona "Conectarse a la Central"
	- ENTONCES el sistema informa que el token está vencido.

- _Escenario 4: Conexión con la Central Fallida por no haber conexión_
	- DADO que el token único del sistema es correcto pero no hay conexión con la Central,
	- CUANDO el Empleado o Gerente selecciona "Conectarse a la Central".
	- ENTONCES el sistema informa que no hay conexión con la central.
	
___

#### Frente
- ID: **Recuperar Factura.**

- TITULO: Como Empleado quiero recuperar los datos de una factura para cobrarla.

- REGLAS DE NEGOCIO: 
	- Conexión con la Central


**Dorso**

- Criterios de aceptación (Recuperar Datos):

- _Escenario 1: Recuperación Exitosa de los datos._
	- DADO que Código de Pago Electrónico es correcto y hay conexión con la Central de Cobros
	- CUANDO el Empleado ingresa: "0303456" y se conecta a la Central de Cobros.
	- ENTONCES el sistema recupera los datos de la factura.
	
- _Escenario 2:Recuperación Fallida de los datos por Código de Pago Electrónico inválido._ 
	- DADO que el Código de Pago Electrónico es incorrecto,
	- CUANDO  el empleado ingresa: "123123".
	- ENTONCES el sistema informa que el código no corresponde a una factura válida.
	
- _Escenario 3:Recuperación Fallida de los datos por no haber conexión con la Central._ 
	- DADO que el Código de Pago Electrónico es correcto, pero no es posible establecer conexión con la Central,
	- CUANDO  el empleado ingresa: "123123" e intenta conectarse a la Central de Cobros,
	- ENTONCES el sistema informa que no e posiblete suceso.

___

#### Frente
- ID: **Calcular Cobro.**

- TITULO: Como Empleado quiero calcular el cobro de las facturas para cobrarlas.

- REGLAS DE NEGOCIO: 
	
 - Verificar los vencimientos para determinar el monto a cobrar.
	
**Dorso**

- Criterios de aceptación (Calcular Cobro):

- _Escenario 1: Cobro Exitoso._
	- DADO que la factura no está vencida,
	- CUANDO el Empleado selecciona "Calcular Monto".
	- ENTONCES el sistema informa el monto original de la factura
	
- _Escenario 2: Cobro Exitoso del 1er vencimiento._ 
	- DADO que la factura tiene el 1er vencimiento vencido,
	- CUANDO el empleado selecciona "Calcular Monto".
	- ENTONCES el sistema aplica e informa un recargo al monto original.
	
- _Escenario 3: Cobro Fallido por 2do vencimiento vencido._ 
	- DADO que la factura tiene el 2do vencimiento vencido
	- CUANDO el empleado selecciona la opción de "Calcular Monto".
	- ENTONCES el sistema informa que la factura no se puede cobrar por dicho motivo.


___

#### Frente
- ID: **Registrar Pagos.**

- TITULO: Como Gerente quiero Registrar los Pagos que se hicieron en el día para enviarlos a la Central.

- REGLAS DE NEGOCIO: 
	- No deben enviarse dos veces las transacciones.

**Dorso**

- Criterios de aceptación (Registrar Pagos):

- _Escenario 1: Registro de Pagos Exitoso._
	- DADO que hay conexión con la central, la clave maestra ""086"" es correcta y no se han enviado los pagos del día,
	- CUANDO el empleado ingresa la clave "086" y selecciona la opción de "Registrar Pagos".
	- ENTONCES el sistema redirige al Gerente a Conectar con la Central
	
- _Escenario 2: Registro de Pagos Fallido porque ya se han envíados los pagos del día._ 
	- DADO que hay conexión con la centra, la clave maestra "999" es correcta, pero ya se ha envia el registro de los pagos del día,
	- CUANDO el empleado ingresa la clave "999" y selecciona "Registrar Pagos".
	- ENTONCES el sistema informa que ya se han registrado los pagos del día.
	
- _Escenario 2: Registro de Pagos Fallido por clave maestra incorrecta._ 
	- DADO que hay conexión con la central
	- CUANDO
	- ENTONCES

___



#### Frente
- ID: **Ver estadísticas.**

- TITULO: Como Empleado quiero ingresar clave maestra para ver las estadísticas de los servicios e impuestos cobrados.

- REGLAS DE NEGOCIO: 
	- 

	
**Dorso**

- Criterios de aceptación (Ver estadísticas):

- _Escenario 1: Visualización exitosa de las estadísticas._
	- DADO que el empleado
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Error al visualizar las estadísticas por clave incorrecta._ 
	- DADA 
	- CUANDO
	- ENTONCES
	
___

#### Frente
- ID: **Recuperar Datos.**
 
- TITULO: Como Empleado o Gerente quiero Verificar el código de un pago ele


**Dorso**

- Criterios de aceptación ():

- _Escenario 1: Recuperación exitosa de los datos de la factura._
	- DADO que el código de pago electrónico "111" es correcto y hay conexión con la central de cobros,
	- CUANDO el Empleado o Gerente ingresa: "111" y selecciona "Recuperar Datos".
	- ENTONCES el sistema se conecta con la central y recupera los datos de la factura.
	
- _Escenario 2: Recuperaión fallida de datos por código de factura incorrecto._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Recuperación fallida de datos por no haber conexión con la Central de Cobros._ 
	- DADO 
	- CUANDO
	- ENTONCES

___


#### Frente
- ID: **Calcular Monto.**

- TITULO: Como Gerente o Empleado quiero calcular el monto de la factura para cobrarla

- REGLAS DE NEGOCIO:
	- 1er fecha de vencimiento.
	- 2da fecha de vencimiento.

**Dorso**

- Criterios de aceptación ():

- _Escenario 1: Cobro exitoso de factura._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Cobro exitoso de factura con 1er vencimiento._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Cobro fallido de factura con 2do vencimiento._ 
	- DADO 
	- CUANDO
	- ENTONCES
___

#### Frente
- ID: **Registrar Cobros.**

- TITULO: 

- REGLAS DE NEGOCIO:
	- Clave maetra para la recuperación de las transacciones y servicios cobrados.

**Dorso**

- Criterios de aceptación ():

- _Escenario 1: Registro de cobros exitoso._
	- DADO que hay conexión con la central, la clave maestra es correcta y no se han enviado los cobros del día.
	- CUANDO el Gerente ingresa la clave "0303456" y selecciona "Registrar envío de cobros"
	- ENTONCES el sistema se conecta con la central y envía los cobros generados en el día
	
- _Escenario 2: Registros de cobros fallido por no haber conexión con la central._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Registro de cobros fallido por querer enviar por 2nda vez los cobros._ 
	- DADO 
	- CUANDO
	- ENTONCES

