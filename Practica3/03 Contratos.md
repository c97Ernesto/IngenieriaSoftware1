## Problema 03: Contratos.

**Actores:**

- Empleado de mesa

- Empleado de rendiciones

- Servidor externo


**Casos de Usos**

- Confeccionar minuta

- Aprobar minuta

- Verificar CUIT

___

**Nombre del caso de uso:**

- Confeccionar minuta

**Descripción:**

- Este Caso de Uso describe el evento en el que el Empleado de mesa confecciona una minuta

**Actores:** 

- Empleado de mesa

**Precondiciones:**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El empleado selecciona la opción de "Generar minuta"
	
	- Paso 3: el empleado ingresa los datos requeridos por el sistema
	
	- Paso 5: el empleado ingresa el monto y los meses

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita los datos de la persona a contratar
	
	- Paso 4: el sistema solicita el monto del contrato y la duración en meses
	
	- Paso 6: el sistema verifica que el monto del contrato sea menor a $25000
	
	- Paso 7: el sistema verifica que la duración del contrato sea menor a 6 meses
	
	- Paso 8: el sistema registra la minuta y le asocia un número único.

**Curso Alterno:**

- Paso alternativo 6: el monto del contrato es mayor a 25000. Se notifica y se vuelve al paso 4

- Paso alternativo 7: la duración del contrato no es menor a 6 meses. Se notifica y se vuelve al paso 4

**Postcondición:**

- Se registra y confecciona una minuta.
___

**Nombre del caso de uso:**

- Aprobar minuta.

**Descripción:**

- Este Caso de Uso describe el evento en el que el Empleado de rendiciones aprueba una minuta.

**Actores:** 

- Empleado de rendiciones.

**Precondiciones:**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El empleado de rendiciones selecciona "Aprobar minuta"
	
	- Paso 3: el empleado ingrese el número de

- **Acciones del Sistema:**

	- Paso 2: El sistema solicita que se ingrese un número de minuta
	
	- Paso 4: el sistema valida el número de minuta
	
	- Paso 5: el sistema verifica que la persona a contratar no tenga más de 3 contratos vigentes
	
	- Paso 6: el sistema ejecuta el Caso de Uso "Verificar CUIT"
	
	- Paso 7: el sistema aprueba la minuta y la registra como aprobada.
	
	- 

**Curso Alterno:**

**Postcondición:**

- Se aprueba una minuta.

___

**Nombre del caso de uso:**

- Verificar CUIT

**Descripción:**

- Este Caso de Uso desribe el evento en el que se verifica el CUIT en la AFIP 

**Actores:** 

- Servidor externo

- Empleado de rendiciones

**Precondiciones:**

- Haber ejecutado el Caso de Uso "Aprobar minuta"

**Curso Normal:**

- **Acción del Actor:**

	- Paso 2: el empleado ingresa el número de CUIT
	
	- Paso : el servidor externo acepta la conexión
	
	- Paso : el servidor externo valida el token único
	
	- Paso : el servidor externo valida el cuil

- **Acciones del Sistema:**

	- Paso 1: El sistema pide el número del CUIT
	
	- Paso : el sistema establece conexión con el servidor externo
	
	- Paso : el sistema envía el token único (ya se encuentra en el sistema)
	
	- Paso : el sistema recibe la validación de que el CUIL es correcto

**Curso Alterno:**

- Paso alternativo 

**Postcondición:**

___
