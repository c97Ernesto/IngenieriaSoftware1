###Problema 3: Contratos
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
- Verificar CUIT/Contactar con servidor de AFIP?.
- Evaluar Minuta .
- Aprobar Minuta. ?
___

####Frente
- ID: **Confeccionar Minuta.**

- TITULO: Como Empleado de Mesa quiero confeccionar una minuta para generar un contraro

- REGLAS DE NEGOCIO:
	- Los montos de los mismos no pueden superar los $25.000 y que la duración debe ser como máximo de 6 meses.

####Dorso
- Criterios de aceptación (Confeccionar Minuta):

- _Escenario 1: Minuta confeccionada con éxito._
	- DADO que la duración del contrato es menor a 7 meses y el monto es menor a 25000,
	- CUANDO el Empleado de Mesa ingresa: "Lalo Landa", "123123", "Hacienda", "2/7/2023", 6, "24999" y presiona "Confeccionar Minuta".
	- ENTONCES el sisteama le asociará un número a la minuta confeccionada.
	
- _Escenario 2: Fallo en la confección de la minuta por cantidad de meses mayor al máximo._ 
	- DADO que la duración del contrato es mayor a 6 meses y el monto es menor a 25000,
	- CUANDO el Empleado de Mesa ingresa: "Edinson Cavani", "1231231", "Laboral", "2/7/2023", 7, "24999" y presiona "Confeccionar Minuta".
	- ENTONCES el sistema informará que la cantidad de meses supera la máxima permitida y no generará un número para asociar a la minuta.
	
- _Escenario 1: Fallo en la confección de la minuta por superar el monto máximo de contrato._
	- DADO que la duración del contrato es menor a 7 meses y pero el monto es mayor a 25000,
	- CUANDO el Empleado de Mesa ingresa: "Marcos Rojo", "23123", "Compraventa", "2/7/2015", 1, "25001" y presiona "Confeccionar Minuta".
	- ENTONCES el sistema informará que el monto de contraro supera los 25000 y no generará un número para asociar a la minuta.

___

####Frente
- ID: **Verificar CUIT.**

- TITULO: Como Empleado de Rendiciones quiero contactarme con el servicio de la AFIP para que ésta me valide el CUIT del usuario.
- TITULO: Como Empleado de Rendiciones quiero verificar si el CUIT ingresado es correcto.

- REGLAS DE NEGOCIO: 
	- El sistema le tiene que mandar un token (código que identificará de manera única a la aplicación) y el CUIT a un servidor de la AFIP.
	
####Dorso
- Criterios de aceptación (Verificar CUIT):

- _Escenario 1: CUIT verificado exitosamente._
	- DADO que el empleado administrativo envía un token correcto del sistema y un CUIT válido,
	- CUANDO el empleado adminsitrativo ingresa/envía?: "t0k3n-D3l-S1st3ma", "88-88888888-88",
	- ENTONCES ¿el servidor de AFIP responde que el CUIT está habilitado.?
	
- _Escenario 2: Fallo al verificar CUIT por ser incorrecto._ 
	- DADO que el empleado administrativo envía un token correcto del sistema pero un CUIT inválido,
	- CUANDO el empleado administrativo ingresa: "t0k3n-D3l-S1st3ma", "888-88888888-88",
	- ENTONCES ¿el servidor de AFIP responde que el CUIT no se encuentra habilitado.?
	
- _Escenario 3: Fallo al verificar CUIT por token incorrecto._ 
	- DADO que el empleado administrativo envía un token incorrecto del sistema pero un CUIT válido,
	- CUANDO el empleado administrativo ingresa: "t0k3n--S1st3ma", "77-77777777-77",
	- ENTONCES ¿el servidor de AFIP responde que el token ingresado no corresponde a un sistema válido?
	
___

####Frente
- ID: **Evaluar Minuta.**

- TITULO: Como Empleado de Rendiciones quiero evaluar las minutas para determinar su aprobación.

- REGLAS DE NEGOCIO:
	- Número de Minuta válido.

####Dorso
- Criterios de aceptación (Evaluar Minuta):

- _Escenario 1: Evaluación de la Minuta exitosa._
	- DADO el número de Minuta "789789" válido,
	- CUANDO el Empleado de Rendiciones ingresa "789789"
	- ENTONCES el sistema muestra los datos de la misma para que sea aprobada.
	
- _Escenario 2: Evaluación de la Minuta fallida por número incorrecto de la misma._ 
	- DADO el número de Minuta "78978" inválido,
	- CUANDO el Empleado de Rendiciones ingresa "78978",
	- ENTONCES el sistema informa que el número de Minuta ingresado no existe
	
___

####Frente
- ID: **Aprobar Minuta.**

- TITULO: Como Empleado de Rendiciones quiero aprobar la Minuta para su posterior firma.?

- REGLAS DE NEGOCIO: 
	- La persona a contratar no tiene que tener más de 3 minutas aprobadas
	- CUIT tiene que estar habilitado (Verificar CUIT).	
	
####Dorso
- Criterios de aceptación (Aprobar Minuta):
- _Escenario 1: Minuta aprobada con éxito._
	- DADA la evaluación correcta de la minuta, la verificación correcta del CUIT y que la persona no tiene más de 3 Minutas aprobadas,
	- CUANDO el Empleado de Rendiciones verifica los datos de la minuta, verifica el CUIT y las minutas aprobadas que tenía o no la persona,
	- ENTONCES el sistema agrega la minuta a un listado con Minutas aprobadas
	
- _Escenario 2: Aprobación fallida de la Minuta por tener más de 3 Minutas aprobadas._ 
	- DADO la evaluación correcta de la minuta, la verificación correcta del CUIT pero la persona tiene más de 3 Minutas aprobadas,
	- CUANDO el Empleado de Rendiciones verifica los datos de la Minuta, verifica el CUIT y las minutas aprobadas que superan las 3.
	- ENTONCES el sistema no apruba
	
- _Escenario 3:._ 
	- DADO 
	- CUANDO
	- ENTONCES
