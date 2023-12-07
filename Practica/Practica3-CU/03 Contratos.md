## Problema 3: Contratos.

Suponga que trabaja en un grupo en el área de sistemas de una organización y está por comenzar unnuevo proyecto para desarrollar un sistema que depende del departamento contable.

El sistema deberá administrar los contratos realizado con terceros. En una de las reuniones con el jefe de
departamento nos dijo que él no usará el sistema pero que recibirá listados del personal contratado ya que
deberá firmarlos para elevarlos a las autoridades. 
Para obtener más información generamos una reunión con el empleado de mesa de entradas. Nos contó que el problema que tienen actualmente es que realizan todas las minutas a mano por lo cual deseanautomatizar esta tarea. Las minutas son el paso previo a un contrato. Para confeccionar una minuta, el empleado de mesa de entradas debe ingresar nombre y número de CUIT de una persona a contratar, tipo de contrato, fecha de comienzo, duración y monto, a lo que el sistema le asociará un número de minuta automáticamente. Nos recomendó leer la reglamentación vigente acerca de contratos de la que obtuvimos que los montos de los mismos no pueden superar los $25.000 y que la duración debe ser como máximo de 6 meses.

Una vez confeccionada la minuta por parte del empleado de mesa de entradas, la misma queda pendiente de aprobación. El que puede aprobar una minuta es el empleado de rendiciones. Realizamos una reunión con él y nos contó que su tarea consiste en evaluar las minutas para determinar su aprobación. También nos dijo que en otro trabajo que tiene usan un sistema llamado MiMiNuTa al que nos puede dar acceso para ver como hacen esa tarea. Después del análisis de este sistema, se concluyó que para aprobar una minuta necesitaría ingresar un número de minuta y que el sistema muestre los datos de la misma para
poder aprobarla. Nos dijo que no puede aprobar la minuta si la persona a contratar tiene 3 contratos vigentes (minutas aprobadas) ni tampoco si el CUIT de la persona a contratar está inhabilitado por la AFIP. 

Actualmente se comunica telefónicamente con la AFIP para realizar esta verificación, pero sabe que ésta provee un servicio para aplicaciones que permite hacer la verificación en línea. Esto último nos obligó a generar una reunión con el administrador de servidores de la AFIP. Nos dijo que para poder conectarnos con un servidor de la AFIP, el sistema debe mandar un token (código que identificará de manera única a nuestra aplicación) y CUIT, si el token es correcto, el servidor responde si el CUIT está habilitado o no. Por último el empleado de rendiciones será el responsable de imprimir los listados con las minutas
aprobadas, es decir, un listado con el personal contratado para poder dárselo al jefe de departamento para que lo firme.

![ejercicio3](./drawios/ejercicio03_P3.drawio.png)

___

**Actores:**

- Empleado de mesa
- Empleado de rendiciones
- Servidor externo

**Casos de Usos**

- Confeccionar minuta
- Aprobar minuta
- Verificar CUIT

___
	
#### Nombre del caso de uso:

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

	- Paso 2: el sistema solicita los datos de la persona: nombre y CUIT
	
	- Paso 4: el sistema solicita el monto del contrato y la duración en meses
	
	- Paso 6: el sistema verifica que el monto del contrato sea menor a $25000
	
	- Paso 7: el sistema verifica que la duración del contrato sea menor a 6 meses
	
	- Paso 8: el sistema registra la minuta y le asocia un número único.

**Curso Alterno:**

- Paso alternativo 6: el monto del contrato es mayor a 25000. Se notifica y se vuelve al paso 4

- Paso alternativo 7: la duración del contrato no es menor a 6 meses. Se notifica y se vuelve al paso 4

**Postcondición:**

- Se confecciona una minuta.
___

#### Nombre del caso de uso:

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
	
	- Paso 3: el empleado ingrese el número de minuta

- **Acciones del Sistema:**

	- Paso 2: El sistema solicita que se ingrese un número de minuta
	
	- Paso 4: el sistema valida el número de minuta
	
	- Paso 5: el sistema verifica que la persona a contratar no tenga más de 3 contratos vigentes
	
	- Paso 6: el sistema ejecuta el Caso de Uso "Verificar CUIT"
	
	- Paso 7: el sistema aprueba la minuta y la registra como aprobada.
	
	- 

**Curso Alterno:**

- Paso alternativo 4: Número de minuta incorrecto. Se notifica y termina CU.

- Paso alternativo 5: La persona posee más de 3 contratos vigente. Se notifica y termina el CU.

- Paso alternativo 6:

**Postcondición:**

- Se aprueba una minuta.

___

**Nombre del caso de uso:**

- Verificar CUIT

**Descripción:**

- Este Caso de Uso desribe el evento en el que se verifica el CUIT en la AFIP.

**Actores:** 

- Servidor de AFIP

**Precondiciones:**

- Haber ejecutado el Caso de Uso "Aprobar minuta"

**Curso Normal:**

- **Acción del Actor:**
	
	- Paso 2: el servidor acepta la conección y valida el token
	
	- Paso 3: el servidor solicita el número de CUIT
	
	- Paso 5: el servidor valida el número de CUIT
	
	- Paso 6: el servidor retorna el estado del CUIT
	
- **Acciones del Sistema:**

	- Paso 1: El sistema solicita la conección con el Servidor de AFIP y envía el token único
	
	- Paso 4: el sistema envía el número de CUIT
	
	- Paso 7: el sistema recibe que el CUIT está habilitado
	
	- Paso 8: se cierra la conección con el servidor externo.

**Curso Alterno:**

- Paso alternativo 1: No se establece conección. Se notifica y termina CU.

- Paso alternativo 2: el token es incorrecto. Se informa y finaliza el CU.

- Paso alternativo 7: El CUIT no está habilitado. Se notifica y termina el CU

**Postcondición:**

- Se verifica que el CUIT se encuentre habilitado.

___

**Nombre del caso**

- Listar Minutas

**Descripción**

- Este Caso de Uso especifica el evento en el cual el Empleado de rendiciones imprime un listado con las minutas aprobadas.

**Actores**

- Empleado de Rendiciones

**Precondiciones**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El empleado de rendiciones selecciona la opción de: "Imprimir Minutas"
	

- **Acciones del Sistema:**

	- Paso 2: el sistema imprime un listado con las minutas aprobadas.
	

**Curso Alterno:**

- Paso alternativo 2: no hay minutas aprobadas. Se informa y termina el CU.

**Postcondición:**

- Se listan minutas aprobadas.

___
