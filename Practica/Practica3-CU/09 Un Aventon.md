### Problema 09: Un Aventón.

![ejercicio9](drawios/ejercicio09_P3.drawio.png)

**Actores:**

- Persona
- Usuario (piloto/copiloto)

**Casos de Usos**

- Iniciar Sesión.
- Cerrar Sesión.
- Registrar Persona.
- Publicar Viaje.
- Postular a un viaje.
- Aceptar/Rechazar Usuario.
- Calificar Usuario.


___

**Nombre del caso de uso:**

- Iniciar Sesión

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

- Cerrar Sesión

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

- Registrar Persona

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

- Publicar Viaje

**Descripción:** 

- Este Caso de Uso describe el evento en el que un Usuario publica un viaje.

**Actores:** 

- Usuario

**Precondiciones:**

- Tener la sesión iniciada

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Usuario selecciona la opción de "Publicar Viaje"
	
	- Paso 4: el usuario ingresa los datos del viaje

- **Acciones del Sistema:**
	
	- Paso 2: el sistema verifica que el Usuario no adeude calificaciones

	- Paso 3: el sistema solicita fecha, hora, y automovil que utilizará
	
	- Paso 5: el sistema verifica los datos del viaje
	
	- Paso 6: el sistema registra y publica el viaje.

**Curso Alterno:**

- Paso alternativo 2: el Usuario adeuda calificaciones. Se informa y finaliza el CU.
	
- Paso alternativo 5: los datos del viaje se superponen con otro viaje del mismo usuario. Se notifica y termina el Caso de Uso.

**Postcondición:**

- Se publica un viaje.

___

**Nombre del caso de uso:**

- Postularse a un viaje

**Descripción:** 

- Este Caso de Uso describe el evento en el que un Usuario se postula a un viaje.

**Actores:**

- Usuario

**Precondiciones:**

- El Usuario debe tener la sesión iniciada.

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Usuario selecciona la opción de "Mostrar Viajes"
	
	- Paso 3: el usuario selecciona un viaje

- **Acciones del Sistema:**

	- Paso 2: el sistema lista los viajes disponibles
	
	- Paso 4: el sistema lo pone en la lista de esperera.

**Curso Alterno:**

- Paso alternativo 2: No hay viajes disponibles. Se notifica, fin de CU.

**Postcondición:**

- Un usuario es puesto en la lista de espera.
___

**Nombre del caso de uso:**

- Aceptar/Rechazar candidatos.

**Descripción:** 

- Este Caso de Uso describe el evento en el que un Usuario acepta/rechaza candidatos postulados.

**Actores:** 

- Usuario

**Precondiciones:**

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Usuario selecciona la opción de "Listar Candidatos"
	
	- Paso 3: el usuario "Acepta"/"Rechaza" un pasajero

- **Acciones del Sistema:**

	- Paso 2: el sistema muestra una lista con los pasajeros postulados.
	
	- Paso 4: el sistema registra al pasajero en el viaje.

**Curso Alterno:**

- Paso alternativo 2: no hay usuarios postulados. Se notifica y termina el CU.

- Paso alternativo 4: el usuario "Rechaza" un pasajero. Fin de CU / se retorna al paso 2¿?

**Postcondición:**

- Se aceptó/rechazó un Usuario. / Se completó un viaje¿?

___

**Nombre del caso de uso:**

- Calificar Usuario

**Descripción:** 

- Este Caso de Uso describe el evento en el que un Usuario califica a otro.

**Actores:** 

- Usuario

**Precondiciones:**

- El Usuario debe tener la sesión iniciada.

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: el Usuario selecciona la opción de "Calificar Usuarios"
	
	- Paso 3: el usuario selecciona el Usuario a calificar
	
	- Paso 5: el usuario califica positivamente

- **Acciones del Sistema:**
	
	- Paso 2: el sistema muestra los usuarios
	
	- Paso 4: el sistema solicita califar negativa o positivamente

**Curso Alterno:**

- Paso alternativo 2: no hay usuarios para calificar. Se notifica y termina el CU.

- Paso alternativo 5: el usuario califica negativamente.

**Postcondición:**

___

