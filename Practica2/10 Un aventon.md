### Problema 10: Un aventón.

**ROL DE USUARIOS:**

- Persona.
- Usuario


**HISTORIAS DE USUARIOS:**

- Registrar Persona.
- Dar de alta viaje.
- Postular viaje.
- Calificar usuario

#### Frente
- ID: **Registrar Persona.**

- TITULO: 

- REGLAS DE NEGOCIO: 
	- No puede haber dos correos electrónicos iguales.


#### Dorso
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
- ID: **Dar de alta viaje.**

- TITULO: Como usuario quiero dar de alta un viaje para que otros usuarios se postulen.

- REGLAS DE NEGOCIO: 
	- No se pueden superponer los viajes de una misma persona.
	- Un usuario que adeuda calificaciones tampoco podrá publicar un viaje.
	
#### Dorso
- Criterios de aceptación (Dar de alta viaje):
- _Escenario 1: Alta exitoso._
	- DADO que el usuario "JuanCa@gmail.com" que no adeuda calificaciones, quiere publicar un viaje el día "23/12/23" a las "12:12". 
	- CUANDO el usuario ingresa: "23/12/23", "12:12", "Corsa", y selecciona "Publicar viaje",
	- ENTONCES el sistema informa que el viaje se publicó exitosamente.
	
- _Escenario 2: Alta fallido por superponerse con otro viaje._ 
	- DADO que el usuario "Lalo@gmail.com" que no adeuda calificaciones, quiere publicar un viaje el día "01/01/24" a las "13:13" pero éste se le superpone con otro viaje.
	- CUANDO el usuario ingresa: "01/01/24", "13:13",
	- ENTONCES el sistema informa que ya tenía un viaje programado para esa fecha y hora.

- _Escenario 3: Alta fallido por adeudar calificaciones._ 
	- DADO que el usuario "Lalo@gmail.com" que adeuda calificaciones, quiere publicar un viaje el día "01/01/24" a las "13:13".
	- CUANDO el usuario ingresa: "01/01/24", "13:13",
	- ENTONCES el sistema informa que no puede publicar viaje porque adeuda calificaciones.

___

#### Frente
- ID: **Postular viaje.**

- TITULO: Como usuario quiero postularme a un viaje para poder viajar.

- REGLAS DE NEGOCIO: 
	- Decisión del chofer si viaja el usuario o no.

	
#### Dorso
- Criterios de aceptación ():
- _Escenario 1: Postulación exitosa._
	- DADO que el usuario "cabj@gmail.com" quiere postularse a un viaje,
	- CUANDO el usuario selecciona la publicación,
	- ENTONCES el sistema informa que ha sido aceptado.
	
- _Escenario 2: Postulación fallida porque ha sido rechazada._ 
	- DADO que el usuario "ciro@gmail.com" quiere postularse a un viaje,
	- CUANDO el usuario selecciona la publicación, 
	- ENTONCES el sistema informa que su postulación a sido rechazada

___

#### Frente
- ID: **Calificar usuario.**

- TITULO: Como usuario quiero calificar a un usuario ...

- REGLAS DE NEGOCIO: 
	- Piloto califica a los copilotos.
	- Copilotos califican al piloto.
	
#### Dorso
- Criterios de aceptación ():
- _Escenario 1: ._
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADA 
	- CUANDO
	- ENTONCES


