<div>
<h2 align="center"> Historias de Usuarios</h2>
</div>

### Formas de redactarlas
- La historia de usuario debe responder a tres preguntas:
	- Quién se beneficia?
	- Que se quiere?
	- Cuál es su beneficio?
	
#### Plantila de una Historia de Usuario:
#### Frente
- **ID**: Identificador unívoco de la historia expresado como texto generalmente de la forma `verbo` `sustantivo`.

- **TÍTULO**: Descripción de la historia de la forma: 
	- **Como** _rol_ **quiero** _algo_ **para poder** _beneficio_
	
- **REGLAS DE NEGOCIO**: Conjunto de reglas, normas, políticas, etc. que condicionan el método de operación.

#### Reverso
- **CRITERIOS DE ACEPTACIÓN:** Criterios por los cuales una historia cumple con las expectativas del cliente. Formato:
	- **Escenario 1:** título del criterio
		- _Dado_ `un contexto inicial`
		- _Cuando_ `ocurre un evento`
		- _Entonces_ `garantiza uno o más resultados`
					
						
	- **Escenario 2:** título del criterio
		- _Dado_ `un contexto inicial`
		- _Cuando_ `ocurre un evento`
		- _Entonces_ `garantiza uno o más resultados`
						
	- **Escenario N:** título del criterio
		- _Dado_ `un contexto inicial`
		- _Cuando_ `ocurre un evento`
		- _Entonces_ `garantiza uno o más resultados`	

### Conceptos
> Una historia de usuario es una representación de un requisito de software escrito en una o dos frases utilizando el lenguaje común del usuario.

> Una historia de usuario es una descripción corta y simple de un requerimiento de un sistema, que se escribe en lenguaje común del usuario y desde su perpectiva.


Debe ser **limitada**, ésta debería poder escribirse sobre una nota adhesiva pequeña.

Son una **forma rápida de administrar los requsitos de los usuarios** sin tener que elaborar gran cantidad de documentos formales y sin requerir de mucho tiempo para administrarlos.

Al momento de implementar las historias, los desarrolladores deben tener la posibilidad de **discutirlas con los clientes**. Generalmente se espera que la estimación de tiempo de cada historia de usuario se sitúe entre unas 10 horas y un par de semanas.

Estimaciones **mayores a dos semanas** son indicativo de que la historia es muy compleja y debe ser **dividida en varias historias**.

### Características
**Independientes unas de otras:** De ser necesario, combinar las historias dependientes o buscar otra forma de dividir las historias de manera que resulten independientes.

**Negociables:** La historia en sí misma no es lo suficientemente explícita como para considerarse un contrato, la discusión con los usuarios debe permitir esclarecer su alcance y éste debe dejarse explícito bajo la forma de pruebas de validación.

**Valoradas por los clientes o usuarios:** Los intereses de los clientes y de los usuarios no siempre coinciden, pero en todo caso, cada historia debe ser importante para alguno de ellos más que para el desarrollador.

**Estimables:** Un resultado de la discusión de una historia de usuario es la estimación del tiempo que tomará completarla. Esto permite estimar el tiempo total del proyecto.

**Pequeñas:** Las historias muy largas son difíciles de estimar e imponen restricciones sobre la planificación de un desarrollo iterativo. Generalmente se recomienda la consolidación de historias muy cortas en una sola historia.

**Verificables:** Las historias de usuario cubren requerimientos funcionales, por lo que generalmente son verificables. Cuando sea posible, la verificación debe automatizarse, de manera que pueda ser verificada en cada entrega del proyecto.

### Criterios de Aceptación
- Un criterio de aceptación es el criterio por el cual se define si una historia de usuario fue desarrollada según la expectativa del Product Manager/Owner (como representante de los criterios del cliente) y se si puede dar como hecha.

- Deben ser definidos durante la etapa inicial antes de la codificación, acompañan a la historia de usuario, porque complementan la historia de usuario y ayudan al equipo de desarrollo a entender mejor cómo se espera que el producto se comporte.

- Los criterios de aceptación son utilizados para expresar el resultado de las conversaciones del cliente con el desarrollador. El cliente debería ser quien las escriba más
que el desarrollador.

- Representan el inicio de la definición del cómo. No están diseñados para ser tan detallados como una especificación de diseño tradicional.

- Si una historia de usuario tiene más de 4 criterios de aceptación, debe evaluarse subdividir la historia.

- Puede añadirse un número de escenario para identificar al criterio, asociado a la historia de usuario en cuestión.

### Épicas
**Se denomina Épica a un conjunto de Historias de usuario que se agrupan por algún denominador común**

- La épica representa un objetivo alcanzable que nace de la necesidad del cliente.

- Es un objetivo al que nos aproximamos y que esperamos alcanzar algún día.

- La épica no es la funcionalidad.

#### Características

- Suelen abarcar varios equipos de desarrollo.

- Recogen nomrmalmente muchas historias de usuarios.

- Los clientes deciden si añaden o eliminan historias dentro de cada épica.

- Sirven para estructurar los temas e iniciativas (objetivos).

- Tambíen sirven para dar flexibilidad y agilidad al proyecto.

### Ejemplo: 
Se desea modelar un sistema web para la inscripción a los cursos de un Instituto. Las **personas** que desean asistir a algún curso previamente deben **matricularse al Instituto**. Para esto el sistema solicita: nombre, apellido, DNI y dirección del interesado. <u>Un DNI no puede estar registrado dos veces con diferentes matrículas</U>. Una vez hecho el registro y el pago correspondiente, se entrega un número de matrícula, que servirá a la persona para inscribirse a los cursos.

Los **matriculados** pueden **inscribirse en los cursos** que se dictan en el Instituto. Cada curso tiene un costo asociado y deberá abonarse al momento de la inscripción al mismo. El sistema primero solicita los datos del matriculado (nombre y código de matrícula) y da la opción de **elegir alguno de los cursos**. <u>Cada curso tiene un cupo de 30 personas</u>. <u>Un alumno sólo se puede inscribir una vez</u> a un mismo curso.

<u>Todos los **pagos se realizan** con tarjeta de crédito</u>. Se realizará el cobro, una vez que el servidor del <u>banco valide el número de tarjeta y verifique que el saldo sea suficiente</u>.

**ROL DE USUARIOS:**

- Persona (no inscripta al curso).
- Matriculado.

**HISTORIAS DE USUARIOS:**

- Cargar datos de matriculación.
- Elegir un curso.
- Pagar con tarjeta.

#### Frente
- ID: **Cargar datos de metriculación.**

- TITULO: Como Persona quiero cargar mis datos para matricularme.

- REGLAS DE NEGOCIO: 
	- Un DNI no puede estar registrado dos veces con diferentes matrículas.
	
**Dorso**

- Criterios de aceptación (Cargar datos de matriculación):

- _Escenario 1: Carga de datos exitosa._
	- DADO que el DNI 43224322 no se encuentra matriculado,
	- CUANDO la Persona ingresa: "Lalo Landa", "43224322", '21, e 2 y 3' y presiona "Matricularse".
	- ENTONCES el sistema redirige al usuario al pago de matrícula con tarjeta de crédito.
	
- _Escenario 2: Carga de datos fallida por matriculado existente._
	- DADO que el DNI 32435423 se encuentra matriculado,
	- CUANDO la Persona ingresa: "Juan Carlos", "32435423", 'Julio A.Roca' y preciona "Matricularse".
	- ENTONCES el sistea informa que el dni ingresado ya se encuentra matriculado

#### Frente
- ID: **Elegir curso.**

- TITULO: Como Matriculado quiero elegir un curso para inscribirme.

- REGLAS DE NEGOCIO: 
	- El curso tiene un cupo de 30 inscriptos.
	- Un matriculado solo se puede inscribir una vez a un mismo curso.


**Dorso**

- Criterios de aceptación (Elegir curso):

- _Escenario 1: Elección exitosa del curso._
	- DADO que la matrícula 32 no se encuentra inscripta al curso "Matemática 1" el cual tiene cupo disponible.
	- CUANDO el Matriculado ingresa: "32", selecciona el curso Matemática 1 y presiona "Inscribirse"
	- ENTONCES el sistema redirige al usuario al pago de inscripción con tarjeta de cŕedito.
	
- _Escenario 2: Elección fallida del curso por falta de cupo._
	- DADO que la matrícula  11 no se encuentra inscripta al curso "Álgebra lineal" el cual no tiene cupo disponible.
	- CUANDO el Matriculado ingresa: "11", selecciona "Álgebra lineal" y oprime "Inscribirse",
	- ENTONCES  el sistema informa que el curso no posee cupos disponibles.
	
- _Escenario 3: Elección fallida porque el alumno ya se encuentra inscripto en el curso._
	- DADO que la matrícula  17 se encuentra incripta al curso "Geometría Analítica", el cual tiene cupo disponible.
	- CUANDO el matriculado ingresa: "17", selecciona "Geometría Analítica" y oprime "Inscribirse"
	- ENTONCES el sistema informa que ya se encuentra inscripto al curso.

- _Escenario 4: Inscripción fallida por número de matrícula inexistente._
	- DADO que la matrícula  "700" no se encuentra inscripta al curso "Lengua y Literatura" el cual tiene cupo disponible.
	- CUANDO se ingresa: "700", se selecciona "Lengua y Literatura" y se oprime "Inscribirse"
	- ENTONCES el sistema informa que la matrícula ingresada no es válida.

#### Frente
- ID: **Pagar con tarjeta**

- TITULO: Como Persona o Matriculado quiero pagar con tarjeta para matricularme o inscribirme a un curso

- REGLAS DE NEGOCIO: 
	- El pago se realiza con tarjeta de crédito



**Dorso**

- Criterios de aceptación (Pagar con Tarjeta):

- _Escenario 1: Pago exitoso de matrícula._
	- DADO que la persona con DNI 43431243 hizo una correcta matriculación, la conexión con el servidor funciona, y el número de tarjeta de crédito ingresado es correcto conteniendo fondos suficientes.
	- CUANDO la persona ingresa: "88989898998" y selecciona "Pagar".
	- ENTONCES el sistema registra la matriculación, el pago e informa.
	
- _Escenario 2: Pago exitoso de inscripción al curso._
	- DADO que la persona con DNI 32443234 hizo una correcta elección del curso "Matemática 1", la conexión con el servidor funciona, y el número de tarjeta de crédito ingresado es correcto conteniendo fondos suficientes.
	- CUANDO la persona ingresa: "977898787" y selecciona "Pagar".
	- ENTONCES el sistema registra la incripción al curso decrementando la cantidad de cupos disponibles y registra el pago.

- _Escenario 3: Pago fallido por número de tarjeta inválido._
	- DADO que la conexión con el banco es exitosa, y el número de tarjeta "312123132" pertenece a una tarjeta de crédito inválida.
	- CUANDO el matriculado o la persona ingresa: "312123132" y selecciona pagar,
	- ENTONCES el sistema informa que el número de tarjeta es incorrecto y el pago no es registrado.


- _Escenario 4: Pago fallido por saldo insuficiente en la tarjeta de crédito._
	- DADO que la conexión con el banco es exitosa, el número de tarjeta 123132123 pertenece a una tarjeto de crédito válida, pero no posee saldo suficiente.
	- CUANDO el matriculado o la persona ingresa: "123132123" y selecciona pagar,
	- ENTONCES el sistema informa que la tarjeta no posee saldo suficiente y no registra el pago

- _Escenario 5: Pago fallido por no haber conexión con el servidor externo._
	- DADO que no hay conexión con el banco
	- CUANDO el matriculado o la persona desea pagar
	- ENTONCES el sistema informa que no se puede establecer la conexión con el servidor externo.




















