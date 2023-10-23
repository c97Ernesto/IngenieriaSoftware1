### Problema 3: Contratos.
Suponga que trabaja en un grupo en el área de sistemas de una organización y está por comenzar un nuevo proyecto para desarrollar un sistema que depende del departamento contable.

El sistema deberá administrar los contratos realizado con terceros. En una de las reuniones con el jefe de departamento nos dijo que él no usará el sistema pero que recibirá listados del personal contratado ya que deberá firmarlos para elevarlos a las autoridades.

Para obtener más información generamos una reunión con el empleado de mesa de entradas. Nos contó que el problema que tienen actualmente es que realizan todas las minutas a mano por lo cual desean automatizar esta tarea. Las minutas son el paso previo a un contrato. Para confeccionar una minuta, el empleado de mesa de entradas debe ingresar nombre y número de CUIT de una persona a contratar, tipo de contrato, fecha de comienzo, duración y monto, a lo que el sistema le asociará un número de minuta automáticamente. Nos recomendó leer la reglamentación vigente acerca de contratos de la que obtuvimos que los montos de los mismos no pueden superar los $25.000 y que la duración debe ser como máximo de 6 meses.

Una vez confeccionada la minuta por parte del empleado de mesa de entradas, la misma queda pendiente de aprobación. El que puede aprobar una minuta es el empleado de rendiciones. Realizamos una reunión con él y nos contó que su tarea consiste en evaluar las minutas para determinar su aprobación. También nos dijo que en otro trabajo que tiene usan un sistema llamado MiMiNuTa al que nos puede dar acceso para ver como hacen esa tarea. Después del análisis de este sistema, se concluyó que para aprobar una minuta necesitaría ingresar un número de minuta y que el sistema muestre los datos de la misma para poder aprobarla. Nos dijo que no puede aprobar la minuta si la persona a contratar tiene 3 contratos vigentes (minutas aprobadas) ni tampoco si el CUIT de la persona a contratar está inhabilitado por la AFIP. Actualmente se comunica telefónicamente con la AFIP para realizar esta verificación, pero sabe que ésta provee un servicio para aplicaciones que permite hacer la verificación en línea. Esto último nos obligó a generar una reunión con el administrador de servidores de la AFIP. Nos dijo que para poder conectarnos con un servidor de la AFIP, el sistema debe mandar un token (código que identificará de manera única a nuestra aplicación) y CUIT, si el token es correcto, el servidor responde si el CUIT está habilitado o no.

Por último el empleado de rendiciones será el responsable de imprimir los listados con las minutas aprobadas, es decir, un listado con el personal contratado para poder dárselo al jefe de departamento para que lo firme.

**ROL DE USUARIOS:**

- Empleado de mesa de entradas.
- Empleado de rendiciones.
	

**HISTORIAS DE USUARIOS:**

- Confeccionar una Minuta.
- Verificar CUIT.
- Aprobar Minuta.

___

#### Frente
- ID: **Confeccionar Minuta.**

- TITULO: Como Empleado de Mesa quiero confeccionar una minuta para generar un contrato.

- REGLAS DE NEGOCIO:
	- Los montos de los mismos no pueden superar los $25.000. 
	- La duración debe ser como máximo de 6 meses.

**Dorso**

- Criterios de aceptación (Confeccionar Minuta):

- _Escenario 1: Minuta confeccionada con éxito._
	- DADO que la duración del contrato es menor a 7 meses y el monto es menor a 25000,
	- CUANDO el Empleado de Mesa ingresa: "Lalo Landa", "123123", "Hacienda", "2/7/2023", 6, "24999" y presiona "Confeccionar Minuta".
	- ENTONCES el sisteama le asocia un número a la minuta confeccionada.
	
- _Escenario 2: Fallo en la confección de la minuta por cantidad de meses mayor al máximo._ 
	- DADO que la duración del contrato es mayor a 6 meses y el monto es menor a 25000,
	- CUANDO el Empleado de Mesa ingresa: "Edinson Cavani", "1231231", "Laboral", "2/7/2023", 7, "24999" y presiona "Confeccionar Minuta".
	- ENTONCES el sistema que la cantidad de meses supera la máxima permitida.
	
- _Escenario 3: Fallo en la confección de la minuta por superar el monto máximo de contrato._
	- DADO que la duración del contrato es menor a 7 meses y pero el monto es mayor a 25000,
	- CUANDO el Empleado de Mesa ingresa: "Marcos Rojo", "23123", "Compraventa", "2/7/2015", 1, "25001" y presiona "Confeccionar Minuta".
	- ENTONCES el sistema informa que el monto de contraro supera los 25000.

___

#### Frente
- ID: **Verificar CUIT.**

- TITULO: Como Empleado de Rendiciones quiero contactarme con el Servidor de la AFIP para que ésta me valide el CUIT del usuario.

- REGLAS DE NEGOCIO: 
	- El sistema le tiene que mandar un token (código que identificará de manera única a la aplicación) y el CUIT a un servidor de la AFIP.
	
**Dorso**

- Criterios de aceptación (Verificar CUIT):

- _Escenario 1: CUIT verificado exitosamente._
	- DADO que el token ingresado es válido, y hay conexión con la AFIP
	- CUANDO el empleado adminsitrativo ingresa: "t0k3n-D3l-S1st3ma", "88-88888888-88", y selecciona "Verificar CUIT".
	- ENTONCES el sistema responde que el CUIT se encuentra habilitado.
	
- _Escenario 2: CUIT verificado exitosamente._
	- DADO que el token ingresado es válido, y hay conexión con la AFIP
	- CUANDO el empleado adminsitrativo ingresa: "t0k3n-D3l-S1st3ma", "88-88888888-88", y selecciona "Verificar CUIT".
	- ENTONCES el sistema responde que el CUIT no se encuentra habilitado.
	
- _Escenario 3: Fallo al verificar CUIT por token vencido._ 
	- DADO que el empleado administrativo envía un token incorrecto del sistema,
	- CUANDO el empleado administrativo ingresa: "t0k3n-D3l-S1st3ma", "888-88888888-88", y selecciona "Verificar CUIT"
	- ENTONCES el sistema responde que el token se encuentra vencido.
	
___


#### Frente
- ID: **Aprobar Minuta.**

- TITULO: Como Empleado de Rendiciones quiero aprobar la Minuta para su posterior firma.

- REGLAS DE NEGOCIO: 
	- La persona a contratar no tiene que tener más de 3 minutas aprobadas
	- CUIT tiene que estar habilitado (Verificar CUIT).	
	
**Dorso**

- Criterios de aceptación (Aprobar Minuta):

- _Escenario 1: Minuta aprobada con éxito._
	- DADO que existe el número de minuta, el cuit está habilitado y la persona no tiene más de 3 Minutas aprobadas,
	- CUANDO el Empleado de Rendiciones ingresa el número de minuta: "0303456", verifica el CUIT, y selecciona la opción de "Aprobar Minuta",
	- ENTONCES el sistema agrega la minuta a un listado con Minutas aprobadas.
	
- _Escenario 2: Aprobación fallida de la Minuta por tener más de 3 Minutas aprobadas._ 
	- DADO que existe el número de minuta, la verificación correcta del CUIT pero la persona tiene más de 3 Minutas aprobadas,
	- CUANDO el Empleado de Rendiciones ingresa el número de minuta "123132", verifica el CUIT y selecciona la opción de "Aprobar Minuta",
	- ENTONCES el sistema informa que la persona posee más de 3 minutas evaluadas.
	
- _Escenario 3: Aprobación fallida de la Minuta por CUIT inhabilitado._ 
	- DADO que existe el número de minuta, pero la verificación del CUIT arroja que este se encuentra inhabilitado,
	- CUANDO la persona ingresa: 12312, verifica el CUIT y selecciona la opción de "Aprobar minutas".
	- ENTONCES el sistema informa que el CUIT se encuentra inhabilitado.
