### Problema 15: Manejo de Canchas de Tenis.

Suponga que la consultora para la cual trabaja ha sido contactada para realizar un sistema para el manejo de turnos en canchas de tenis.

Luego de varias reuniones con el cliente se ha concluido que es necesario la realización de un sistema web donde las personas interesadas puedan obtener turnos en diferentes canchas de tenis de un complejo. Para esto las personas deben registrarse en la plataforma indicando nombre, apellido, mail (será utilizado como nombre de usuario), edad y domicilio. El cliente nos ha indicado que solo quiere que se registren personas mayores de edad (18 años o más). Una vez que la persona se registra con éxito el sistema genera una contraseña que será enviada al correo que ha sido ingresado.

Una vez registrada la persona puede solicitar turnos en una cancha del complejo, para esto debe iniciar sesión previamente. El cliente desea que si un usuario falla tres veces al iniciar sesión su cuenta sea bloqueada.

Para solicitar un turno, el usuario ingresa cancha, fecha y hora. Si la cancha está libre el turno se le asigna al usuario informando “Su turno ha sido registrado con éxito”, si la cancha está ocupada se le informará “Cancha ocupada, por favor seleccione otro día y horario”, dándole la posibilidad de volver a seleccionar un turno nuevo. El sistema no debe permitir
dar turno con menos de 2 días a la fecha en que se solicita.

**ROL DE USUARIOS:**

- Personas.
- Usuario 

**HISTORIAS DE USUARIOS:**

- Registrar Persona.
- Iniciar Sesión.
- Solicitar Turno.

___

#### Frente
- ID: **Registrar Persona.**

- TITULO: Como Persona quiero registrarme para poder usar el sistema

- REGLAS DE NEGOCIO
	- Solo se peuden registrar personas mayores a 18 años.


**Dorso**

- Criterios de aceptación (Registrar Persona):

- _Escenario 1: Registro exitoso._
	- DADO que el mail "usuario1@gmail.com" no se encuentra registrado en el sistema y la persona tiene 23 años siendo mayor a 18,
	- CUANDO la Persona ingresa: "Juan", "Perez", "usuario1@gmail.com", "23", "Michael Jones - 734" y selecciona "Registrarse".
	- ENTONCES el sistema genera una contraseña y la envía al correo registrado.
	
- _Escenario 2: Registro fallido por correo existente._ 
	- DADO que el mail "usuario007@gmail.com" se encuentra registrado y la persona tiene 54 años
	- CUANDO la Persona ingresa: "Jimena", "Monteverde", "usuario007@gmail.com", "54", "28 de Julio - 734" y selecciona "Registrarse".
	- ENTONCES el sistema informa que el correo ingresado ya se encuentra registrado en el sistema.
	
- _Escenario 3: Registro fallido por ser menor de edad._ 
	- DADO que el mail "usuario2@gmail.com" no se encuentra registrado, pero la persona tiene 17 años siendo menor de edad,
	- CUANDO la Persona ingresa: "Lalo", "Landa", "usuario2@gmail.com", "17", "Alsina 234" y selecciona "Registrarse".
	- ENTONCES el sistema informa que no es posible el registro por ser menor de edad

___

#### Frente
- ID: **Iniciar Sesión.**

- TITULO: Como Usuario quiero Iniciar Sesion para poder solicitar turnos

- REGLAS DE NEGOCIO: 
	- Solo tres intentos de inicio de sesión.


**Dorso**

- Criterios de aceptación (Iniciar Sesión):

- _Escenario 1: Ingreso exitoso._
	- DADO que el usuario "usuario007@gmail.com" y la contraseña "2311132" pertenecen a una cuenta registrada en el sistema, y la cantidad de intentos de inicio de sesión es igual a 3
	- CUANDO el Usuario ingresa: usuario007@gmail.com, 2311132 y selecciona "Ingresar"
	- ENTONCES el sistema registra la sesión y habilita las funciones del usuario.
	
- _Escenario 2: Ingreso fallido por datos de inicio de sesión incorrecto y cantidad de intentos igual a 3._ 
	- DADO que el mail "usuario07@gmail" y la contraseña "321312" no pertenecen a un usuario registrado en el sistema, y la cantidad de intentos de inicio de sesión es igual a 3
	- CUANDO el Usuario ingresa: usuario07@gmail.com, 321312 y selecciona "Ingresar".
	- ENTONCES el sistema informa que los datos de inicio de sesión son incorrectos y bloquea la cuenta.
	
- _Escenario 3: Ingreso fallido por datos incorrectos con cantidad de intentos igual a 2._ 
	- DADO que el mail "usuario1@gmail.com" y la contraseña "231132" no perteneces a una cuenta del sistema, y la cantidad de intentos de inicio de sesión es igual a 2
	- CUANDO el Usuario ingresa: usuario1@gmail.com, 231132, y selecciona "Ingresar",
	- ENTONCES el sistema informa que los datos ingresados no pertenecen a una cuenta del sistema e incrementa en uno la cantidad de intentos realizados por el Usuario.
	
- _Escenario 4: Ingreso fallido por cuenta bloqueada._ 
	- DADO que el mail "usuario1@gmail.com" y la contraseña "231132" pertenecen/o no, a una cuenta del sistema,
	- CUANDO el Usuario ingresa: usuario1@gmail.com, 231132, y selecciona "Ingresar",
	- ENTONCES el sistema informa que no se puede inciar sesión porque la cuenta se encuentra bloqueada.


___

#### Frente
- ID: **Solicitar Turno.**

- TITULO: Como usuario quiero solicitar un turno para reservar una cancha.

- REGLAS DE NEGOCIO:
	- Turnos con al menos dos días de anticipación.


**Dorso**

- Criterios de aceptación (Solicitar Turno):

- _Escenario 1: Reservación del turno exitosa._
	- DADO que la reserva del turno se realiza el día 27/2/2002 con una anticipación de 9 días
	- CUANDO el Usuario ingresa: "Deportivo Municipal Villa San Carlos", "27/2/2002", "00:30" y selecciona "Solicitar"
	- ENTONCES el sistema informa que "Su turno ha sido registrado con éxito".
	
- _Escenario 2: Reservación del turno fallida por cancha ocupada._ 
	- DADO que la reserva del turno se realiza el día "29/9/1969" con una anticipación de 13 días,
	- CUANDO el Usuario ingresa: "Deportivo Municipal Villa Ballester", "29/9/1969", "11:00" y selecciona "Solicitar"
	- ENTONCES el sistema informa "Cancha ocupada, por favor seleccione otro día y horario".
	
- _Escenario 3: Reservación fallida porque la cantidad de días de anticipación es menor a 2._ 
	- DADO que la reserva del turno se realiza el día "1/1/2021" con una anticipación de 1h 27m
	- CUANDO el Usuario ingresa: "Deportivo Municipal Villa Real", "1/1/2021", "21:00" y selecciona "Solicitar"
	- ENTONCES el sistema informa que deben haber al menos dos días de anticipación de la solicitud del turno.


___

#### Frente
- ID: **.**

- TITULO: 


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

