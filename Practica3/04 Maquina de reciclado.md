##Problema 4: Máquina de reciclado.

**Actores:**

- Persona

- Operador

**Casos de Usos**

- Reciclar material.

- Solicitar listado.

- Actualizar montos

___

**Nombre del caso de uso:**

- Reciclar material

**Descripción:** 

- Este Caso de Uso describe el evento en el que una persona recicla un material

**Actores:** 

- Persona

**Precondiciones:**

- No hay

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: La Persona selecciona la opción "Reciclar"

- **Acciones del Sistema:**

	- Paso 2: el sistema detecta el tipo de material
	
	- Paso 3: el sistema registra el peso del material
	
	- Paso 4: el sistema registra el material reciclado

**Curso Alterno:**

- Paso alternativo 2: el sistema no detecta el material. Se notifica. Se aborta el proceso y retorna el producto.

**Postcondición:**

- Se imprime recibo con el monto que se le debe pagar a la persona

___

**Nombre del caso de uso:**

- Solicitar listado

**Descripción:** 

- Este Caso de Uso describe el evento en el que el Operador solicita un listado de los tipos de materiales reciclados.

**Actores:** 

- Operador

**Precondiciones:**

- No hay

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El operador selecciona la opción de "Solicitar Listado"
	
	- Paso 3: el operador ingresa las fechas
	

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita las fechas de un periodo determinado
	
	- Paso 4: el sistema verifica que las fechas ingresadas sean válidas
	
	- Paso 5: el sistema imprime el listado detallando además el total abonado por los materiales

**Curso Alterno:**

- Paso alternativo 4: las fechas ingresadas no son válidas. Se notifica y se retorna al paso 2.

**Postcondición:**

- Se imprime listado con los tipos de materiales reciclados en el rango de las fechas ingresadas

___

**Nombre del caso de uso:**

- Actualizar montos

**Descripción:** 

- Este Caso de Uso describe el evento en el que el operador actualiza los montos a pagar por kilo de cada tipo de material.

**Actores:** 

- Operador

**Precondiciones:**

- No hay 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El operador selecciona "Actualizar Montos"
	
	- Paso 3: el operador selecciona el tipo de material que quiere actualizar
	
	- Paso 5: el operador ingresa el nuevo monto del material
	
	- Paso 7: el operador selecciona que quiere actualizar el nuevo monto

- **Acciones del Sistema:**

	- Paso 2: El sistema muestra los tipos de materiales reciclables
	
	- Paso 4: el sistema solicita el nuevo monto del material
	
	- Paso 6: el sistema informa si desea actualizar el nuevo monto
	
	- Paso 8: el sistema registra el nuevo monto del material
	

**Curso Alterno:**

- Paso alternativo 7: el operador selecciona la opción de que no quiere actualizar el monto. Fin de Caso de Uso

**Postcondición:**

- Se actualiza el precio por kilo del material



