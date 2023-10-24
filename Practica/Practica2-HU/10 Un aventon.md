### Problema 10: Un aventón.

**ROL DE USUARIOS:**

- Persona
- Usuario

**HISTORIAS DE USUARIOS:**

- Publicar Viaje.
- Agarrar Viaje.
- Elegir Candidato.
- Calificar usuario
- Registrar Persona.
- Iniciar Sesión.
- Cerrar Sesión.


#### Frente
- ID: **Publicar Viaje.**

- TITULO: Como Usuario quiero publicar un viaje para conseguir pasajeros.

- REGLAS DE NEGOCIO: 
	- No se pueden superponer los viajes de una misma persona.
	- Un usuario que adeuda calificaciones tampoco podrá publicar un viaje.
	
**Dorso**

- Criterios de aceptación (Publicar Viaje):

- _Escenario 1: Publicación Exitosa._
	- DADO que el usuario "User1@gmail.com", no adeuda calificaciones y quiere publicar un viaje el día "23/12/23" a las "12:12". 
	- CUANDO el usuario ingresa: "23/12/23", "12:12", "Corsa", y selecciona "Publicar viaje",
	- ENTONCES el sistema informa que el viaje se publicó exitosamente.
	
- _Escenario 2: Publicación Fallida por superposición con otro viaje._ 
	- DADO que el usuario "User2@gmail.com", no adeuda calificaciones y quiere publicar un viaje el día "01/01/24" a las "13:13" pero éste se le superpone con otro viaje.
	- CUANDO el usuario ingresa: "23/12/23", "12:12", "Aveo", y selecciona "Publicar viaje",
	- ENTONCES el sistema informa que ya tenía un viaje programado para esa fecha y hora.

- _Escenario 3: Publicación Fallida por adeudar calificaciones._ 
	- DADO que el usuario "User2@gmail.com" adeuda calificaciones y quiere publicar un viaje el día "01/01/24" a las "13:13".
	- CUANDO el usuario ingresa: "23/12/23", "12:12", "205", y selecciona "Publicar viaje",
	- ENTONCES el sistema informa que no puede publicar viaje porque adeuda calificaciones.

___

#### Frente
- ID: **Agarrar Viaje.**

- TITULO: Como usuario quiero postularme a un viaje para poder viajar.

- REGLAS DE NEGOCIO: 

	
**Dorso**

- Criterios de aceptación (Agarrar Viaje):

- _Escenario 1: Postulación exitosa._
	- DADO que hay viajes disponibles y el usuario "cabj@gmail.com" quiere postularse a un viaje,
	- CUANDO el usuario lista los viajes disponibles y selecciona el viaje que desea,
	- ENTONCES el sistema informa que la postulación se hizo con éxito.
	
- _Escenario 2: Postulación Fallida por falta de viajes._ 
	- DADO que no hay viajes disponibles, y el usuario "ciro@gmail.com" quiere postularse a un viaje,
	- CUANDO el usuario lista los viajes.
	- ENTONCES el sistema informa que no hay viajes disponibles.

___

#### Frente
- ID: **Elegir Candidato.**

- TITULO: Como Usuario quiero evaluar a otro para que viaje.

- REGLAS DE NEGOCIO: 
	- 

**Dorso**

- Criterios de aceptación (Elegir Candidato):

- _Escenario 1: Evaluación Exitosa, aceptado._
	- DADO que un Usuario se postuló para viajar, 
	- CUANDO el piloto selecciona la opción de "Aceptar".
	- ENTONCES el sistema suma al viaje al Usuario.
	
- _Escenario 2: Evaluación Exitoso, rechazado._ 
	- DADO que un usuario se postuló para viajar
	- CUANDO el piloto selecciona la opción de "Rechazar"
	- ENTONCES el sistema informa que se rechazó al Usuario

___


#### Frente
- ID: **Calificar usuario.**

- TITULO: Como usuario quiero calificar a un usuario para evaluarlo.

- REGLAS DE NEGOCIO: 

	- Un piloto califica copiloto y veceversa.
	
**Dorso**

- Criterios de aceptación (Calificar Usuario):

- _Escenario 1: Calificación Exitosa, positivamente._
	- DADO que el usuario "User1@gmail" viajó con "User2@gmail",
	- CUANDO el usuario "User1@gmail" califica positivamente al usuario "User2@gmail".
	- ENTONCES el sistema suma un punto de reputación al "User2@gmail".
	
- _Escenario 2: Calificación Exitosa, negativamente._ 
	- DADO que el usuario "User2@gmail" viajó con "User1@gmail",
	- CUANDO el usuario "User2@gmail" califica negativamente al usuario "User1@gmail".
	- ENTONCES el sistema suma un punto de reputación al "User2@gmail".

___


#### Frente
- ID: **Iniciar Sesión.**

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
- ID: **Cerrar Sesión.**

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
- ID: **Registrar Persona.**

- TITULO: 

- REGLAS DE NEGOCIO: 
	- 


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

