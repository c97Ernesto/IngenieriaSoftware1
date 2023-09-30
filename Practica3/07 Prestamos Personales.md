##Problema 7: Préstamos Personales.

**Actores:**

- Cliente

- Empleado

- Servidor Externo


**Casos de Usos**

- Solicitar Préstamo via web

- Verificar Cliente

- Adelantar cuotas

- Cancelar Préstamo

- Iniciar Sesión

- Cerrar Sesión
___

**Nombre del caso de uso:**

- Solicitar Préstamo vía web

**Descripción:** 

- Este Caso de Uso describe el evento en el que un cliente solicita un préstamo personal a través de la web.

**Actores:** 

- Cliente

**Precondiciones:**

- El Cliente debe tener una sesión iniciada

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: el Cliente selecciona la opción de "Solicitar Préstamo"
	
	- Paso 4: el cliente ingresa el motivo y la cuenta
	
	- Paso 7: el cliente ingresa el monto del préstamo

- **Acciones del Sistema:**

	- Paso 2: el Sistema verifica la cantidad de préstamos del Cliente
	
	- Paso 3: el sistema solicita el motivo y la cuenta de dónde se descontará
	
	- Paso 5: el sistema verifica la cuenta
	
	- Paso 6: el sistema solicita el monto
	
	- Paso 8: el sistema verifica el monto
	
	- Paso 9: el sistema ejecuta el CU "Verificar Cliente"

	
	
	- Paso  : el sistema registra el préstamo correspondiente, genera un identificador del préstamo, un código de verificación y un comprobante con los datos del préstamo. 

**Curso Alterno:**

**Postcondición:**

___

**Nombre del caso de uso:**

- Verificar Cliente

**Descripción:** 

**Actores:**

- Servidor externo

**Precondiciones:**

- Haber ejecutado el Caso de Uso "Solicitar Préstamo".

**Curso Normal:**

- **Acción del Actor:**

	- Paso 2: el servidor externo verifica el código
	

	

	

- **Acciones del Sistema:**

	- Paso 1: El Sistema envía el código de seguridad
	

	


**Curso Alterno:**

**Postcondición:**

- 

___

**Nombre del caso de uso:**

- Adelantar cuotas 

**Descripción:** 



**Actores:** 

- Cliente

**Precondiciones:**

- El cliente debe tener una sesión iniciada

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Cliente selecciona la opción de "Adelantar cuotas"
	
	- Paso 3: el cliente selecciona el préstamo que desea pagar
	
	- Paso 6: el cliente ingresa la cantidad de coutas que desea adelantar
	
	- Paso 8: el cliente selecciona la cuenta

- **Acciones del Sistema:**

	- Paso 2: El sistema muestra un listado de los préstamos a pagar
	
	- Paso 4: el sistema verifica la cantidad de meses desde que se otorgó el préstamo
	
	- Paso 5: el sistema solicita la cantidad de cuotas a pagar
	
	- Paso 7: el sistema muestra las cuentas del cliente
	
	- Paso 9: el sistema verifica el saldo de la cuenta 
	
	- Paso 10: se registra el pago de las cuotas y se descuenta saldo del cliente

**Curso Alterno:**

- Paso alternativo 4: La cantidad de meses desde otorgado el préstamo no supera los 6 meses. Se notifica y se termina el CU

- Paso alternativo 9: La cuenta no posee fondos suficientes. Se notifica y se retorna al paso 7.

**Postcondición:**

- Se adelantan cuotas del préstamo

___

**Nombre del caso de uso:**

- Cancelar préstamo

**Descripción:** 

**Actores:** 

- Empleado

**Precondiciones:**

- Ninguna

**Curso Normal:**

- **Acción del Actor:**

El mismo Cliente es el que realiza la cancelación del préstamo

	- Paso 1: El Empleado selecciona la opción de "Cancelar Préstamo"
	
	- 

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita el DNI del cliente.
	
	- 

**Curso Alterno:**

**Postcondición:**

___

**Nombre del caso de uso:**

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

**Nombre del caso de uso:**

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
