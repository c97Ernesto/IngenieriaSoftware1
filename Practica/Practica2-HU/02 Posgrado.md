### Problema 2: Posgrado.
Suponga que trabaja en el área de sistemas de la Facultad de Informática y se le solicitó la automatización del pago decarreras de posgrado. Inicialmente se coordinó una reunión con el director del posgrado y se obtuvo la siguiente información:

Ya que no se desea seguir cobrando el dinero en la secretaría, es necesario que los alumnos puedan pagar las carreras vía web. Como el director de posgrado no realiza tareas administrativas nos recomendó hablar con el secretario académico.
De la entrevista con el secretario académico se obtuvo la siguiente información:

Es necesario cargar las carreras a un sistema. En esta primera versión del sistema sólo se nos pidió esta funcionalidad, sin la modificación ni eliminación. De cada carrera se conoce: nombre de la carrera (no puede repetirse), duración en años (a partir de la consulta del estatuto de posgrado se obtuvo que como máximo son 5 años), costo y cantidad máxima de cuotas para el pago. La carga de las carreras no la realiza el secretario académico sino un empleado administrativo.

Al preguntarle por la dinámica del sistema, el secretario académico nos derivó con el jefe del área administrativa, con el cual hicimos otra entrevista y pudimos obtener la siguiente información:

El requerimiento fue que el alumno ingrese a la web de posgrado y pueda registrarse ingresando: nombre, apellido, nombre de usuario (único) y contraseña (más de 6 dígitos). Cualquier alumno previamente registrado, puede iniciar sesión con su nombre de usuario y contraseña, habilitándose la inscripción a alguna de las carreras. Para ejemplificar esta funcionalidad nos otorgaron acceso al sistema SIGEF, el cual realiza funcionalidades similares para las carreras de grado. Para inscribirse, el alumno deberá seleccionar la carrera, ingresar la cantidad de cuotas a pagar, ingresar el número de tarjeta y, en caso de que la tarjeta sea válida y tenga fondos, se hará efectivo el cobro y la inscripción. La tarjeta de crédito se valida a través de un servicio del banco con el cual la universidad tiene convenio. Luego de efectuado el cobro, el sistema debe imprimir dos comprobantes, uno de inscripción y otro de pago. La única forma que tiene el alumno de pagar es con tarjeta de crédito.

**ROL DE USUARIOS:**

- Empleado administrativo.
- Alumno 

**HISTORIAS DE USUARIOS:**

- Cargar Carrera.
- Registrar Alumno.
- Seleccionar Carrera.
- Realizar pago.

___

#### Frente
- ID: **Cargar Carrera.**

- TITULO: Como EMpleado Adminstrativo quiero realizar la carga de las carreras de posgrado para que los alumnos se puedan elegir a cual inscribirse.

- REGLAS DE NEGOCIO: 
	- No se puede ingresar el nombre de una carrera que ya existe.
	- Las carreras no pueden superar los 5 años.
	
**Dorso**

- Criterios de aceptación (Cargar carrega de posgrado):
- _Escenario 1: Carrera de Posgrado cargada con éxito._
	- DADA la carrera "Ingeniería de Software" que no se encuentra cargada,
	- CUANDO el Empleado administrativo ingresa: "Ingeniería de Software", "1", "60000", "12", y selecciona "Cargar Carrera",
	- ENTONCES el sistema informa que la Carrera fue cargada.
	
- _Escenario 2: Fallo al cargar la Carrera de Posgrado por nombre existente._ 
	- DADA la carrera "Informática" que ya encuentra cargada,
	- CUANDO el Empleado adminsitrativo ingresa "Informática", "5", "60000", "12", y selecciona "Cargar Carrera",
	- ENTONCES el sistema informa que la Carrera ya existe.
	
- _Escenario 2: Fallo al cargar la Carrera por superar los 5 años._ 
	- DADA la carrera "Cheffcito" que no se encuentra cargada,
	- CUANDO el Empleado adminsitrativo ingresa "Cheffcito", "6", "12312", "12", selecciona "Cargar Carrera",
	- ENTONCES el sistema informa que la duración máxima de la cerrera no puede superar los 5 años.
	
___

#### Frente
- ID: **Seleccionar Carrera.**

- TITULO: Como Alumno quiero poder elegir una Carrera de Posgrado para poder inscribirme.

- REGLAS DE NEGOCIO: 
	- 
	
**Dorso**
- Criterios de aceptación (Seleccionar Carrera de Posgrado):
- _Escenario 1: Elección de Carrera de Posgrado exitosa._
	- DADO que el alumno no está inscripto en la carrera de "Mecatrónica"
	- CUANDO el alumno elige "Mecatrónica", coloca Ahora12 y selecciona "Pagar".
	- ENTONCES el sistema lo redigire a que realice el pago.
	
- _Escenario 2: Elección de Carrera Fallida._ 
	- DADO que el alumno se encuentra inscripto en la carrera de "Mecanografía en tiempos modernos"
	- CUANDO el alumno elige la carrera, coloca 3 cuotas y selecciona "Pagar"
	- ENTONCES el sistema informa que ya se encuentra inscripto.
	
___

#### Frente
- ID: **Realizar Pago.**

- TITULO: Como Alumno quiero poder realizar el pago de la inscripción a la Carrera de Posgrado seleccionada.

- REGLAS DE NEGOCIO: 
	- Tiene que ser con tarjeta de crédito validada a través de un servicio del banco con el cual la universidad tiene convenio.
	
**Dorso**
- Criterios de aceptación (Realizar Pago):
- _Escenario 1: Pago realizado con éxito._
	- DADO el alumno con nombre de usuario "elBarto" eligió una Carrera, ingresó un número de tarjeta de crédito "123123" válido y la tarjeta tiene fondos suficientes,
	- CUANDO el alumno ingresa el número de tarjeta "123123" y selecciona "Pagar",
	- ENTONCES el sistema registra el pago y la inscripción del alumno a la Carrera de Posgrado que seleccionó, imprimiendo los comprobantes mismos.
	
- _Escenario 2: Pago fallido por número de tarjeta inexistente._ 
	- DADO el alumno con nombre de usuario "elBarto" que eligió una Carrera de Posgrado a la cual inscribirse e ingresó un número de tarjeta de crédito "12312" inválido.
	- CUANDO el alumno ingresa el número de tarjeta "12312" y selecciona "Pagar",
	- ENTONCES el sistema informa que el pago no se registró por no ingresar un número de tarjeta de crédito válido.
	
- _Escenario 3: Pago fallido por no tener fondos suficientes._ 
	- DADO el alumno con nombre de usuario "elBarto" que eligió una Carrera de Posgrado a la cual inscribirse e ingresó un número de tarjeta de crédito "0303456" válido la cual no tiene fondos suficientes.
	- CUANDO el alumno ingresa el número de tarjeta "0303456" y selecciona "Pagar",
	- ENTONCES el sistema informa que el pago no se registró por no tener fondos suficiente.
	
___
	
#### Frente
- ID: **Registrar Alumno.**

- TITULO: Como alumno quiero poder Registrarme en el sistema para poder elegir una carrera.

- REGLAS DE NEGOCIO: 
	- Nombre de usuario único.
	- Contraseña de más de 6 dígitos.
	
**Dorso**

- Criterios de aceptación (Registrar Alumno):
- _Escenario 1: Registro Exitoso del Alumno._
	- DADO que el alumno con nombre de usuario "Juancito1" no se encuentra registrado,
	- CUANDO el alumno ingresa: "Juan", "Lopez", "Juancito1", "a1b2c3d4", y selecciona "Registrarse", 
	- ENTONCES el sistema informa que se ha completado el registro.
	
- _Escenario 2: Registro Fallido por nombre de usuario existente._ 
	- DADO que el alumno con nombre de usuario "Juancito2" se encuentra registrado,
	- CUANDO el alumno ingresa: "Juan", "Rodriguez", "Juancito2", "a1b2c3d4", y selecciona "Registrarse",
	- ENTONCES el sistema informa que ese nombre de usuario ya existe.
	
- _Escenario 3: Registro Fallido po contraseña menor a 6 dígitos._ 
	- DADO que el alumno con nombre de usuario "Alex" no se encuentra registrado,
	- CUANDO el alumno ingresa: "Alex", "Caniya", "Alex", "a1b2c3", y selecciona "Registrarse",
	- ENTONCES el sistema informa que la contraseña es demasiado corta.
___

#### Frente
- ID: **Iniciar Sesión.**

- TITULO: 
	- Como Alumno quiero Iniciar Sesión para poser inscribirme a una Carrera.

- REGLAS DE NEGOCIO: 
	- Ingresar con su usuario y contraseña


**Dorso**
- Criterios de aceptación (Iniciar Sesión):

- _Escenario 1: Inicio de Sesión Fallido por contraseña incorrecta._
	- DADO que el usuario es correcto, pero no la contraseña,
	- CUANDO el Alumno ingresa: "Marco", "123" y selecciona "Iniciar Sesión"
	- ENTONCES el sistema informa que la contraseña ingresada es incorrecta.
	
- _Escenario 2: Inicio de Sesión Fallido por Usuario incorrecto._
	- DADO que el usuario es incorrecto,
	- CUANDO el ALumno ingresa: "Polo", "123" y selecciona "Iniciar Sesión"
	- ENTONCES el sistema informa que el usuario no existe en el sistema.
	
- _Escenario 3: Inicio Exitoso._ 
	- DADO que la contraseña y el usuario son correctos,
	- CUANDO el usuario ingresa: "Marco", "Polo", y selecciona la opción de "Iniciar Sesión"
	- ENTONCES el sistema registra el inicio de sesión y habilita las funciones correspondientes.

___

#### Frente
- ID: **Cerrar Sesión.**

- TITULO: Como Alumno quiero cerrar sesión para poder terminar.

- REGLAS DE NEGOCIO: 
	- 

**Dorso**

- Criterios de aceptación (Cerrar Sesión):

- _Escenario 1: Cierre de Sesión Exitoso._
	- DADO que el alumno tiene la sesión abierta
	- CUANDO selecciona la opción de "Cerrar Sesión"
	- ENTONCES el sistema deshabilita todas las funciones de la Sesión abierta.

