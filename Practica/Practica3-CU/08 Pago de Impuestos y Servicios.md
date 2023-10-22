## Problema 08: Pago de Impuestos y Servicios.

![ejercicio8](./drawios/ejercicio08_P3.drawio.png)

**Actores:**

- Empleado

- Servidor de la Central de Cobro.

**Casos de Usos**

- Realizar Pago.

- Recuperar Datos.

- Registrar Pagos

___

#### Nombre del caso de uso:

- Realizar Pago.

**Descripción:** 

- Este Caso de Uso describe el evento en el que el Empleado hace el cobro de una factura.

**Actores:** 

- Empleado

**Precondiciones:**

- Ninguna

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Empleado selecciona la opción de "Realizar Pago"
	
	- Paso 3: el empleado ingresa el código.
	
	- Paso 7: el empleado ingresa el monto de la factura

- **Acciones del Sistema:**

	- Paso 2: El sistema solicita el código de pago electrónico
	
	- Paso 3: el sistema verifica el Código de pago electrónico
	
	- Paso 4: el sistema ejecuta el CU Recuperar Datos
	
	- Paso 5: el sistema calcula el monto
	
	- Paso 6: el sistema informa y solicita el monto
	
	- Paso 8: el sistema registra el pago.

**Curso Alterno:**

- Paso alternativo 3: el código de pago electrónico es incorrecto. Se notifica y finaliza el CU.

- Paso alternativo 4: no se recuperan los datos de la factura. Se notifica y termina el CU.

- Paso alternativo 6: la factura no se puede cobrar por superar el 2do vencimiento. Se informa y finaliza el CU.

**Postcondición:**

- Se cobra una Factura 

___

#### Nombre del caso de uso:

- Recuperar Datos.

**Descripción:** 

- Este Caso de Uso describe el evento en el que se recuperan los datos de una factura mediante el código de pago electrónico.

**Actores:** 

- Servidor de la Central de Cobro.

**Precondiciones:**

- Haber ejecutado el Caso de Uso: Realizar Pago.

**Curso Normal:**

- **Acción del Actor:**

	- Paso 2: La Central acepta la conexión con el sistema
	
	- Paso 3: La central solicita el código de pago electrónico
	
	- Paso 5: la central verifica el código
	
	- Paso 6: la central retorna los datos de la factura

- **Acciones del Sistema:**

	- Paso 1: el sistema establece la conexión con la Central
	
	- Paso 4: el sistema envía el código
	
	- Paso 7: el sistema recibe los datos de la factura y cierra la conexión con el servidor

**Curso Alterno:**

- Paso alternativo 1: la central rechaza la conexión. Se informa y termina el CU.

**Postcondición:**

- Se recuperan los datos de una factura 

___

#### Nombre del caso de uso:

- Registrar Pagos

**Descripción:**

- Este Caso de Uso describe el evento en el que el Gerente registra los pagos realizados. 

**Actores:** 

- Gerente

**Precondiciones:**

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Gerente selecciona "Registrar Pagos"
	
	- Paso 3: el gerente ingresa la clave maestra

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita la clave maestra
	
	- Paso 4: el sistema verifica la clave maestra
	
	- Paso 5: el sistema recupera los cobros y transacciones del día
	
	- Paso 6: el sistema ejecuta el Caso de Uso "Enviar Cobros y Transacciones"
	
	- Paso 7: el sistema informa el el registro de los pagos y transacciones

**Curso Alterno:**

- Paso alternativo 4: la clave maestra es incorrecta. Se notifica y finaliza el CU.

- Paso alternativo 5: no se pueden recuperar los pagos y transacciones porque ya se han recuperados. Se informa y finaliza el CU.

- Paso alternativo 7: no se enviaron los pagos y transacciones. Se notifica y finaliza el CU.

**Postcondición:**

- Se registran los pagos y transacciones.

___

#### Nombre del caso de uso:

- Enviar Cobros y Transacciones

**Descripción:** 

- Este Caso de uso describe el evento en el que la Central de Cobro recibe las transacciones.

**Actores:** 

- Central de Cobro.

**Precondiciones:**

- Haber ejecutado el Caso de Uso: "Registrar Pagos"

**Curso Normal:**

- **Acción del Actor:**

	- Paso 2: la Central acepta la conexión del sistema
	
	- Paso 3: la Central solicita los datos
	
	- Paso 5: la central recibe e informa la recepción de los datos

- **Acciones del Sistema:**

	- Paso 1: El sistema establece la conexión con la Central
	
	- Paso 4: el sistema envía los datos
	
	- Paso 5: el sistema recibe la recepción de los datos por parte de la central
	
	- Paso 6: el sistema cierra la conexión con la central

**Curso Alterno:**

- Paso alternativo 1: la central rechaza la conexión. Se informa y termina el CU.

**Postcondición:**

- Los pagos y transacciones son enviados a la central. 

