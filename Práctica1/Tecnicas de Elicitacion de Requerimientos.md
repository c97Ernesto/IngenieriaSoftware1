## Obtención de los Requerimientos
###Parte 1: Definiciones.
**1.Definir brevemente qué es un requerimiento.**

Los requerimientos del sistema especifican lo que el sistema de información deberá hacer o cuál propiedad o cualidad debe de tener éste. 


**2.Definir requerimientos funcionales y no funcionales.**

**_Funcionales:_** Especifican lo que el sistema de información debe hacer.
	
- Describen una interacción entre el sistema y su ambiente. Cómo debe comportarse el sistema ante deteerminado estímulo.
- Describen lo que el sistema _debe hacer_, o incluso como _no debe comportarse_.
- Describen con detalle la funcionalidad del mismo.
- Son independientes de la implementación de la solución. 
- Se pueden expresar de distintas formas.
	
**_No funcionales:_** Especifican una propiedad o cualidad que el sistema debe tener.

- _Requerimientos del producto._ Especifican el comportamiento del producto (usabilidad, eficiencia, rendimiento, espacio, fiabilidad, portabilidad, etc).
- _Requerimientos organizacionales._ Se derivan de las políticas y procedimientos existentes en la organización del cliente y en la del desarrollador (entrega, implementación, estándares).
- _Requerimientos externos._ Interoperabilidad, legales, privacidad, seguridad, éticos, etc.

**3.Definir que es un stakeholder.** 

Son las personas que serán afectadas de uno u otro modo (directa o indirectamente) por el sistema

**4.Definir las fuentes más importantes para la obtención de información.**

_**Métodos discretos:**_

- Muestreo de la documentación, los formularios y los datos existentes.
- Investigación y visitas al lugar.
- Observación del ambiente de trabajo.

_**Métodos interactivos**_

- Cuestionarios.
- Entrevistas.
- Planeación conjunta de Requerimientos (JRP o JAD).
- Lluvia de ideas (Brainstorming).
	
**5.Indicar los puntos de vista (de manera genérica) que se pueden reconocer en un proyecto de software.**
	
**_Interactuadores:_** representan a las personas u otros sistemas que interactúan directamente con el sistema. Pueden influir en los requeriemientos del sistema de algún modo.

**_Indirecto:_** representan a los stakeholder que no utilizan el sistema ellos mismos pero influyen en los requeriemientos de algún modo.

**_Dominio:_** representan las características y restricciones del dominio que influyen en los requerimientos del sistema.

**6.Enumerar tres problemas de comunicación que pueden existir en la elicitación de requisitos.**

- Conflictos personales o políticos
- Medios de comunicación inadecuados (diagramas que no entienden los clientes y usuarios).
- Dificultad para expresar claramente las necesidades.


###Parte 2: Problemas.

**a) Indicar para cada problema quienes podrían ser los *Stakeholders*, los puntos de vista y las fuentes de información.**

**1)** En un sistema de registro de asistencia a través de técnicas biométricas (huella digital) de estudiantes universitarios para la cátedra de Ingeniería I. Este sistema se alimentará de un listado otorgado por la oficina de alumnos de la facultad. Además, necesita la autorización del Jefe de Trabajos Prácticos del turno correspondiente para luego los alumnos poder registrar el presente. También, el profesor a cargo de la materia podrá consultar y listar el estado de cada alumno perteneciente a su cátedra. El sistema sólo se utilizará en el ámbito de la facultad de Informática y deberá adecuarse a la reglamentación sobre privacidad de los datos en el ámbito de la misma.

- Stakeholders:
	- _Oficina (personal) de alumnos_, otorga el listado.
	- _Jefe de Trabajos Pŕacticos_, del cual se necesita la autorización.
	- _Alumnos_, que registran el presente en el sistema.
	- _Profesor_, que consulta y lista el estado de los alumnos registrados en el sistema.
	
- Puntos de vista:
	- Interactuadores:
		- _alumnos de la cátedra_, mediante su huella digital.
		- _profesor a cargo_, cunsulta el listado.
		- _jefe de trabajos pŕacticos_ da la autorización.

	- Indirecto: 
	
	- Dominio: 
		- _reglamentación sobre privacidad de los datos de la facultad_
		
- Fuentes de información:
	- _stakeholders_
	- _listado otorgado por la oficina de alumnos_
	
**2)** Se desea desarrollar un sistema para gestionar y administrar la atención de pacientes en una clínica privada especializada en tratamientos alérgicos. Cuando un paciente nuevo es ingresado a la clínica el empleado registra todos sus datos personales, posteriormente un enfermero registra los controles y realiza las anotaciones habituales (temperatura, presión, peso, reacciones alérgicas etc.). Luego, el paciente es derivado con alguno de los doctores de la clínica, quién registra qué tratamientos deberá realizar. El médico también se encarga de registrar si el paciente debe quedar internado y debe mantener su historia clínica durante el período que dure el tratamiento. Se sabe que el director de la clínica puede consultar las historias clínicas de todos los pacientes. El sistema debe adecuarse a las normativas impuestas por el ministerio de salud de la provincia de Bs As.

- Stakeholders:
	- _Pacientes_, se necesitan los datos (personales).
	- _Empleado_, que registra los datos del paciente.
	- _Enfermero_, registra controles habituales.
	- _Doctores_, registra los tratamientos (datos).
	- _Director_, consulta las historias clínicas


- Puntos de vista:
	- Interactuadores:
		- _Empleado_, registra datos personales.
		- _Enfermero_, registra controles
		- _Doctor_, registra tratamientos que debe realizar.

	- Indirecto: 
	
	- Dominio: 
		- _Normativas_, impuestas por el ministerio de salud
		
- Fuentes de información:
	- _stakeholders_
	- _Datos de los pacientes_
		
## Entrevistas
###Parte 1: Definiciones.
**1) Describa qué tipo de información puede obtenerse en una entrevista.**
- Buscar opiniones en vez de hechos.
- Capturar los sentimientos del entrevistado.
- Objetivos.
- Cuestiones sobre HCI (interacción humano computadora).

**2) Enumere y describa brevemente las etapas de la preparación de una entrevista.**

1. Leer el material sobre los antecedentes.
- Poner atención en el lenguaje. Buscar un vocabulario común. Imprescindible para poder entender al entrevistado.	
		
2. Establecer los objetivos de la entrevista.
	
3. Decidir a quien/es entrevistar.
- Minimizar el número de entrevistas
- Los entrevistados deben conocer con antelación el objetivo de la entrevista y las preguntas que se le van a hacer.
	
4. Planifiación de la entrevista y preparación del entrevistado.
- Establecer fecha, hora, lugar y duración de cada entrevista de acuerdo con el entrevistado.
	
5. Decidir sobre los tipos de preguntas y su estructura.

**3) Enumere y describa brevemente qué tipos de preguntas puede contener una entrevista. Detalle ventajas y desventajas de cada una.**

**Abiertas:** Permite al encuestado responder de cualquier manera.

- Ventajas
	- Revelan nueva línea de preguntas
	- Hacen más interesante la entrevista
	- Permiten espontaneidad

- Desventajas
	- Pueden dar muchos detalles irrelevantes
	- Se puede perder el control de la entrevista
	- Parece que el entrevistador no tiene los objetivo claros
	
**Cerradas:** Las respuestas son directas, cortas o de selección.

- Ventajas 
	- Ahorran tiempo.
	- Se mantiene más fácil el control de la entrevista.
	- Se consiguen datos relevantes.
- Desventajas
	- Pueden aburrir al encuestado.
	- No se obtienen detalles.
	- No se puede generar una buena comunicación entre las partes.

**Sondeo:** El propósito es ir más allá de la respuesta inicial para obtener más detalles significativos, aclarar la información y ampliar el punto del entrevistado.


**4) Enumere y describa brevemente qué tipo de estructuras y organización existen para el armado de una entrevista.**

1. _**Piramidal (inductivo):**_ Se empiezan con preguntas muy detallas, a menudo cerradas. Despúes expande los temas al permitir preguntas abiertas y respuestas más generalizadas. Se utiliza si se cree que el entrevistado necesita entrar en calor en cuanto al tema.

2. _**Embudo (deductivo):**_ Se comienza con preguntas generalizadas y abiertas, para despúes reducir la cantidad de respuestas posibles mediante el uso de preguntas cerrada. Es conveniente usar ésta secuencia de preguntas cuando el entrevistado está relacionado sentimentalmente con el tema y necesita libertad para expresar sus sentimientos.

3. _**Diamante (combinación de las anteriores):**_ El entrevistador empieza con preguntas fáciles y cerradas que permiten al entrevistador entrar en calor; a la mitad se le pregunta lo que opina sobre temas amplios que obviamente no tienen solo una respuesta "correcta". Después el entrevistador restringe incluso más las preguntas para obtener respuestas específicas, con lo cual se produce un cierre tanto para el entrevistado como para el entrevistador.

**5) Analice un formato de la planilla adecuado al momento de armar una entrevista.**

**6) Analice un formato de la planilla adecuado al momento de terminar una entrevista.**

###Parte 2: Situaciones.

####Situación 1
Tiene una entrevista con el gerente de ventas de una empresa el cual desea informatizar dicho sector pero no tuvo tiempo de preparar las preguntas por lo que le pidió a un nuevo empleado que le prepare algunas. Cuando las lee, se da cuenta que son inadecuadas.

Lea las preguntas y vuelva a redactarlas de una manera más apropiada. Especifique por qué le parece inadecuada cada una de ellas.

**1.** Sus subordinados me dijeron que la empresa no anda bien. ¿Es cierto?

- _Los empleados comentaron que la empresa no está en su mejor momento. Cómo cree que se encuentra en éste momento la empresa?_

**2.** Soy nuevo en esto. ¿Qué he dejado afuera?

- _Tengo poca experiencia en el tema. Hay algún otro tipo de información que me pueda proporcionar?_

**3.** ¿Estará usted de acuerdo con los demás gerentes de ventas, respecto a que computarizar las ventas mensuales y luego realizar un análisis de la tendencia tendría usted grandes mejoras?

- _Que piensa sobre computarizar las ventas mensuales para ver si al realizar un análisis de la tendencia se llegan a tener mejoras?_

**4.** ¿No habrá una mejor manera de hacer proyecciones de sus ventas, que ese procedimiento anticuado que usted utiliza?

- _Que opina sobre actualizar el procedimiento de proyecciones de ventas?_



####Situación 2
Apenas ha entrado a la oficina de su entrevistado se da cuenta que él no ha dejado de revisar papeles, mirar el reloj y hacer llamadas telefónicas. Usted supone que se siente nervioso porque está atrasado con otro trabajo que tiene que terminar.

**1.** Explique brevemente cómo resolvería tal situación.

**2.** Qué opciones propone para el caso en que la entrevista no pueda reprogramarse.

- Hablar con otra persona que esté en el mismo nivel jerárquico.
- Algún otra manera en que le resulte más facil/cómodo responder preguntas (cuestionario, 				etc).

####Situación 3
El siguiente es el primer informe de una entrevista realizada por uno de los miembros de su equipo de análisis de sistemas:

> En mi opinión, el resultado de la entrevista fue muy bueno. El entrevistado me permitió hablar con él durante una hora y media. Me relató toda la historia del negocio, que fue muy interesante. También mencionó que las cosas no han cambiado desde que él ha estado en la empresa, hace aproximadamente 16 años. En breve nos reuniremos nuevamente para terminar la entrevista, pues, no tuvimos tiempo para analizar las preguntas que preparé. 

**1.** Lea atentamente el informe de la entrevista y explique qué sensación le deja dicho informe.

- Respecto a los requisitos, parece que no se ha obtenido mucha información.
- Por otro lado, se pudo haber llegado a conocer bastante acerca de la persona.

**2.** Indique si existe información que es irrelevante en el informe.

- Si hablamos de requisitos, no hay información relevante más de la que se pudo haber llegado a obtener en documentación previa.
- En cuanto a la persona, se puede ver el tiempo que tuvo para la entrevista y que tendrá, además de que parece que habló bastante.

**3.** Mencione tres sugerencias que le haría a su compañero de equipo para que realizara una mejor entrevista la próxima vez.

- Apuntar más a los requeriemientos. 
- Controlar más a la otra persona cuando hable para no perder demasiado tiempo.
 

###Parte 3: Problemas.
**Problema 1**. Preparar una entrevista para obtener los requerimientos del siguiente problema:

Se desea desarrollar un sistema que permita compartir un vehículo para un viaje. La idea es que cuando una persona tiene que realizar un viaje lo publique en la aplicación. Luego el resto de los usuarios se postulan para acompañarla y el chofer podrá seleccionar quienes viajan. El objetivo es abaratar costos y evitar congestiones en el tránsito.

**Problema 2**. Preparar una entrevista para obtener los requerimientos del siguiente problema:

CookBooks es un negocio pequeño manejado por una pareja jubilada. Hasta este momento, Cookbooks ha vendido sus libros sólo a través de pedidos por correo. Los dueños ahora quieren desarrollar un sistema en línea para vender libros de cocina difíciles de conseguir y agotados a través de internet. 

Los visitantes podrán hojear diferentes libros de cocina, pero tendrán que crear una cuenta del cliente antes de poder hacer una compra. Los pagos se aceptarán sólo en línea con una tarjeta de crédito reconocida.

## Cuestionarios
###Parte 1: Definiciones.
**1) Describa qué tipo de información se busca mediante la aplicación de cuestionarios.**

- Recolectar hechos de un gran número de personas.
- Detectar un sentimiento generalizado.
- Detectar problemas entre usuarios.
- Cuantificar respuestas.

**2) Describa bajo qué circunstancia considera apropiado utilizar cuestionarios.**

- Cuando las personas están dispersas geográficamente (diferentes oficinas u ciudades).
- Muchas personas involucradas (clientes o usuarios).
- Obtención de opiniones generales.
- Identificar problemas generales.


**3) Describa los dos tipos de cuestionarios.**

De preguntas abiertas o cerradas.

1. Abiertas:
	- Son las que dejan abiertas todas las posibles opciones de respuesta.
	
2. Cerradas: 
	- Limitan o cierran las opciones de respuestas disponibles.

###Parte 2: Situaciones.
####Situación 1
Alguien nuevo en el centro de cómputo de un gimnasio que tiene varias sucursales, viene con muchas ganas de mejorar las cosas que ve dentro del mismo. Dicho centro está desarrollando un sistema en red que usarán todas las sucursales.

Dado el siguiente cuestionario verifique si es necesario reescribir las preguntas, justifique.

- **Cuestionario 1**
 
- _¡Urgente! Complételo y devuélvalo de manera inmediata, sino su cheque de pago será retenido
hasta que devuelva el presente._

	1. En pocas palabras indique qué problemas ha tenido el actual centro de cómputo.
	
	2. ¿Habrá alguien que piense de la misma manera que usted? Enumere sus nombres.
	
	3. ¿Cuántas PC fallaron en estos últimos 6 meses?
	
	4. ¿Cuál es el problema más grande que enfrenta al comunicar sus problemas al centro de cómputo?

####Situación 2
El siguiente es un cuestionario diseñado por un empleado de una empresa textil que se especializa en fabricar medias para hombres. Este empleado lo escribió en calidad de gerente de la oficina que tiene a cargo la propuesta de compra / implementación de un nuevo sistema de cómputos.

- _**¡Hola a todos los empleados!**
Según los rumores, estamos tras una nueva computadora. Aquí hay algunas preguntas para
que reflexionen._

	a . ¿Cuánto tiempo ha usado la computadora vieja?

	b. ¿Con que frecuencia se descompone?

	c. ¿Quién la repara?

	d. ¿Cuándo fue la ultima vez que usted sugirió una mejora al sistema de cómputos y esta
se puso en práctica? ¿De qué se trató?

	e. ¿Cuándo fue la última vez que usted sugirió una mejora al sistema de cómputos y
nadie la usó? ¿De que se trató?

	f. ¿Usted utiliza una pantalla o una impresora, o ambas?

	g. ¿Qué tan rápido escribe en la computadora?

	h. ¿Cuántas personas necesitan acceder a la base de datos regularmente en su sucursal?
¿Hay alguien que actualmente no utilice la computadora y que le gustaría
hacerlo?


















