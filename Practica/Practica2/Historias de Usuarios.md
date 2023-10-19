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
