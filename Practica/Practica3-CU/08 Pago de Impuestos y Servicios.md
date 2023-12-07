## Problema 08: Pago de Impuestos y Servicios.

Se desea modelar un sistema de pago electrónico de impuestos y servicios en efectivo.

Cuando un cliente llega para realizar un pago, el empleado o el gerente de la sucursal ingresa el código de pago electrónico y el sistema se conecta con la central de cobro para recuperar los datos de la factura (empresa, nro de cliente, 1era fecha de vencimiento, 2da fecha de vencimiento, recargo, y monto original).

Una vez recuperados los datos, el sistema debe verificar los vencimientos para determinar el monto a cobrar. Teniendo esto en cuenta, cuando el 2do vencimiento está vencido se debe informar que la factura no se puede cobrar por dicho motivo. Cuando el 1er vencimiento está vencido hay que aplicar el recargo al monto original. Si la factura no está vencida, se cobra el monto original.

Una vez al día, el gerente de la sucursal debe registrar en la central de cobros los pagos que hicieron los clientes. Para esto el sistema requiere la clave maestra y de ser correcta, recupera las transacciones de los impuestos y servicios cobrados en el día, se conecta a la central de cobro y se las envía. Cuando la central confirma la recepción exitosa, el sistema las registra como enviadas. Este último paso es importante porque no deben enviarse dos veces las transacciones. Si el gerente intenta enviar una segunda vez, el sistema no debe permitirlo.

Finalmente el Gerente puede ver las estadísticas de los impuestos y servicios cobrados. Para esto, se ingresa la clave maestra, un rango de fechas sobre las cuales debe calcularse las estadísticas y el sistema debe mostrar los montos y la cantidad de cobros realizados, agrupando por empresa. 

Tenga en cuenta que cada vez que el sistema debe conectarse a la central, debe enviarle un token (código que identifica al sistema). Una vez que la central valida el token, el sistema envía el requerimiento para recuperar los datos de la factura o el requerimiento para registrar los pagos del día según corresponda.

![ejercicio8](./drawios/ejercicio08_P3.drawio.png)

**Actores:**

- Empleado

- Gerente

- Servidor de la Central de Cobro

**Casos de Usos**

- Realizar Pago.

- Recuperar Datos de Factura.

- Registrar Cobros.

- Enviar Transacciones.

- Ver Estadísticas.
___

#### Nombre del caso de uso:

- Realizar Pago.

**Descripción:** 

- Este Caso de Uso describe el evento en el que el Empleado o Gerente hace el cobro de una factura.

**Actores:** 

- Empleado.

**Precondiciones:**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Empleado o Gerente selecciona la opción de "Cobrar"
	
	- Paso 3: el Empleado ingresa el código

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita el código de pago electrónico
	
	- Paso 4: el sistema ejecuta el CU "Recuperar Datos de Factura"
	
	- Paso 5: el sistema verifica la fecha de vencimiento
	
	- Paso 6: el sistema calcula el monto a cobrar según el vencimiento
	
	- Paso 7: el sistema cobra el monto solicitado

**Curso Alterno:**

- Paso alternativo 4: Error al recuperar los datos de la factura. Se informa y finaliza el CU.

- Paso alternativo 6: No hay monto a cobrar por fecha de 2do vencimiento. Se notifica y finalica el CU.

**Postcondición:**

- 

___

#### Nombre del caso de uso:

- Recuperar Datos.

**Descripción:** 

- Este Caso de Uso describe el evento en el que se recuperan los datos de una factura de la Central de Cobros.

**Actores:** 

- Servidor de la Central de Cobro.

**Precondiciones:**

- Haber ejecutado el CU "Realizar Pago".

**Curso Normal:**

- **Acción del Actor:**

	- Paso 2: el Servidor Externo acepta la conexión y solicita	el token
	
	- Paso 4: el Servidor verifica el token y retorna el resultado
	
	- Paso 6: el Servidor acepta la solicitud y colicita los datos de la factura
	
	- Paso 8: el Servidor verifica los datos de la factura y retorna el resultado

- **Acciones del Sistema:**

	- Paso 1: el sistema establece conexión con el Servidor Externo
	
	- Paso 3: el sistema envía el token al Servidor Externo
	
	- Paso 5: el sistema recibe el estado del token y solicita el envío de los datos de la factura
	
	- Paso 7: el sistema envía los datos de la factura
	
	- Paso 9: el sistema recibe los datos y finaliza la conexión con el Servidor de la Central de Cobros.

**Curso Alterno:**

- Paso alternativo 1: No hay conexión con el Servidor. Se informa y finaliza el CU.

- Paso alternativo 5: El token es incorrecto, se informa y finaliza el CU.

**Postcondición:**

- Se recuperan los datos de una factura.

___

#### Nombre del caso de uso:

- Registrar Cobros

**Descripción:**

- Este Caso de Uso describe el evento en el que el Gerente de la surcursal regristra los cobros del día.

**Actores:** 

- Gerente

**Precondiciones:**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Gerente selecciona la opción de "Registrar Cobros"
	
	- Paso 3: el Gerente ingresa la clave maestra

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita la clave maestra.
	
	- Paso 4: el sistema verifica la clave ingresada
	
	- Paso 5: el sistema recupera las transacciones del día
	
	- Paso 6: el sistema ejecuta el CU "Enviar Transacciones"
	
	- Paso 7: el sistema registra como enviadas las transacciones del día

**Curso Alterno:**

- Paso alternativo 4: la clave maestra es incorrecta. Se notifica y finaliza el CU.

- Paso alternativo 6: No se pueden enviar las transacciones del día, se informa y finaliza el CU.


**Postcondición:**

- Se registran los pagos y transacciones.

___

#### Nombre del caso de uso:

- Enviar Transacciones.

**Descripción:** 

- Este CU describe el evento en el que La Central de Cobros recibe las transacciones del día.

**Actores:** 

- Central de Cobros.

**Precondiciones:**

- Haber ejecutado el CU "Registrar Cobros".

**Curso Normal:**

- **Acción del Actor:**

	- Paso 2: La Central de Cobro acepta la conexión y solicita le token
	
	- Paso 4: la Central verifica el token recibido y retorna el resultado
	
	- Paso 7: la Central recibe las transacciones y confirma la recepción

- **Acciones del Sistema:**

	- Paso 1: El sistema establece conexión con la Central de Cobro
	
	- Paso 3: el sistema envía el token
	
	- Paso 5: el sistema recibe que el token es correcto
	
	- Paso 6: el sistema envía las transacciones del día
	
	- Paso 8: el sistema recibe la confirmación de la recepción de las transacciones y finaliza la coneción con la Central de Cobro.

**Curso Alterno:**

- Paso alternativo 1: No hay conexión con la Central de cobro, se informa y finaliza el CU.

- Paso alternativo 5: El token se enceuntra vencido. Se informa y finaliza el CU.

- Paso alternativo 8: Se recibe el rechazo de la recepción de las transacciones del día porque ya ha sido efectuado. Se notifica y fin de CU.


**Postcondición:**

- Se registran las transacciones en la Central de Cobros. 


___

#### Nombre del caso de uso:

- Ver Estadísticas.

**Descripción:** 

- Este Caso de Uso describe el evento en el que el Gerente visualiza los impuestos y servicios cobrados.

**Actores:**

- Gerente

**Precondiciones:**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Gerente selecciona la opción de "Visualizar Estadísticas"
	
	- Paso 3: el Gerente ingresa la clave maestra
	
	- Paso 6: el Gerente ingresa las fechas

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita la clave maestra
	
	- Paso 4: el sistema verifica la clave maestra
	
	- Paso 5: el sistema solicita el rango de fechas
	
	- Paso 7: el sistema valida el rango de fechas ingresado
	
	- Paso 8: el sistema informa los montos y la cantidad de cobros realizados agrupando por empresa.

**Curso Alterno:**

- Paso alternativo 4: La clave maestra ingresada es incorrecta, se informa y finaliza el CU.

- Paso alternativo 7: No hay cobros realizados en esas fechas, se informa y finaliza el CU.

**Postcondición:**

- Se visualizan los cobros realizados en el rango de fechas indicados.


___

**Nombre del caso de uso:**

- 

**Descripción:** 

**Actores:** 

**Precondiciones:**

**Curso Normal:**

- **Acción del Actor:**

	-
	
	-

- **Acciones del Sistema:**

	-
	
	-

**Curso Alterno:**

**Postcondición:**

___

