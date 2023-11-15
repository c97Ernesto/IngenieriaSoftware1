### Problema 11: Concursos.

**ROL DE USUARIOS:**

- Docente (no registrado)

- Docente Registrado (registrado)

**HISTORIAS DE USUARIOS:**

- Registrar Docente.

- Inscribir al Curso.

___

#### Frente
- ID: **Registrar Docente.**

- TITULO: Como docente quiero registrarme en el sistema para inscribirme a un concurso.

- REGLAS DE NEGOCIO: 
	- El mail debe ser único.
	- DNI permitidos para concursar deben estar en el rango de los ńumeros: "12000000" y "55000000"


**Dorso**

- Criterios de aceptación (Registrar Docente):

- _Escenario 1: Registro exitoso._
	- DADO que el correo electrónico "docente1@gmail.com" no se encuentra registrado en el sistema y el DNI del Docente "23232323" se encuentra en el rango de "12000000" a "55000000".
	- CUANDO el docente ingresa: "23232323", "Juan", "Carlos", "docente1@gamil.com", y selecciona la opción de "Registrarse".
	- ENTONCES el sistema informa que se registró correctamente y envía una contraseña asignada automáticamente al correo electrónico registrado.
	
- _Escenario 2:Registro Fallido por correo elctrónico existente._ 
	- DADO que el correo electrónico "docente007@gmail.com" se encuentra registrado en el sistema y el DNI del Docente "54434343" se encuentra en el rango de "12000000" a "55000000".
	- CUANDO el Docente ingresa: "54434343", "Marco", "Polo", "docente007", y selecciona "Registrarse".
	- ENTONCES el sistema informa que el correo electrónico ingresado ya ha sido registrado.
	
- _Escenario 3: Registro Fallido porque el DNI no se encuentra en el rango de los DNI solicitados._
	- DADO que el correo electrónico "Docente3@gamil.com" no se encuentra en el sistema, pero el DNI "11999999" no pertene al rango de "12000000" a "55000000"
	- CUANDO el Docente ingresa: "11999999", "Doc", "Ente", "Docente3@gmail.com", y selecciona "Registrarse". 
	- ENTONCES el sistema informa que el DNI ingresado no se encuentra habilitado para participar en el concurso.
	
	
- _Escenario 4: Registro Falllido por DNI existente._ 
	- DADO que el correo electrónico "fernandoAlonso@gmail.com" no se encuentra registrado, pero el DNI "132132" pertenece a una persona ya registrada.
	- CUANDO el Docente ingresa: "213123", "Fernando", "Alonso", "fernandoAlonso@gmail.com" y selecciona "Registrarse".
	- ENTONCES el sistema informa que el DNI ingresado ya pertenece a un Docente registrado en el sistema.

___

#### Frente
- ID: **Inscribir al curso.**

- TITULO: Como Docente Registrado quiero inscribirme a un concurso para concursar.

- REGLAS DE NEGOCIO: 
	- El docente no podrá inscribirse a más de 3 concursos.


**Dorso**

- Criterios de aceptación (Inscribir a concurso):

- _Escenario 1: Inscripción exitosa._
	- DADO que se encuentran materias habilitadas a las cual inscribirse, y el docente registrado va a hacer su primera inscripción a un concurso.
	- CUANDO el docente elige el concurso "Matemáticas", y selecciona la opción de "Inscribirse",
	- ENTONCES el sistema imprime un comprobante de incripción al concurso.
	
- _Escenario 2: Inscripción fallida por estar en más de tres concursos inscriptos._ 
	- DADO que se encuentran materias habilitadas para inscribirse pero el docente ya se encuentra registrado en 3 materias.
	- CUANDO el docente elige la materia a la cual inscribirse, y selecciona la opción de "Inscribirse".
	- ENTONCES el sistema informa que ya se encuentra inscripto en tres concursos y no puede realizar más inscripciones.
	
___

#### Frente
- ID: **.**

- TITULO: 

- REGLAS DE NEGOCIO: 
	- 


**Dorso**

- Criterios de aceptación ():

- _Escenario 1:._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: ._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
___


#### Frente
- ID: **.**

- TITULO: 

- REGLAS DE NEGOCIO: 
	- 


**Dorso**

- Criterios de aceptación ():

- _Escenario 1:._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: ._ 
	- DADO 
	- CUANDO
	- ENTONCES

