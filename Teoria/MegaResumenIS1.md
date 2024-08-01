## Requerimientos.

### Fuentes de Requerimientos
- **Documentación**

- **Especificación de sistemas similares**

- **Stakeholders**
	- Éste término se utiliza para referirse a cualquier persona o grupo que se verá afectado por el sistema, directa o indirectamente.
	- Puntos de vista:
		- _Interactuadores,_ representan a las personas u otros sistemas que interactúan directamente con el sistema y pueden influir en los requerimientos del sistema de una u otra manera.
		- _Indirecto,_ representan a los stakeholders que no utilizan el sistema ellos mismos, pero que influyen en los requerimientos de algún modo.
		- _Dominio,_ representan a las características y restricciones del dominio que influyen en los requerimientos del sistema

#### Requerimientos Funcionales.
Describen las funciones específicas y las operaciones que el sistema debe realizar. Estos requisitos se centran en lo que el sistema debe hacer y están orientados a las capacidades y comportamientos del software. 

#### Requerimientos no Funcionales.
Se centran en los atributos del sitema y como el sistema debe comportarse en términos de rendimiento, confiabilidad, usabilidad, entre otros


### Estudio de viabilidad
Es principalmente para sistemas nuevos.

A partir de una descripción resumida del sistema se elabora un informa que recomienda la conveniencia o no de realizar el proceso de desarrollo.

Responde a las siguientes preguntas:

- El sistema contribuye a los objetivos generales de la organización?

- El sistema se puede implementar con la tecnología actual?

- El sistema se puede implementar con las restricciones de costo y tiempo?

- El sistema puede integrarse a otros que existen en la actualidad?

## Elicitación de Requerimientos.
Proceso de adquirir ("eliciting") [sonsacar] todo el conocimiento relevante necesario para producir un modelo de los requerimientos de un dominio de problema

#### Objetivos:
- Conocer el dominio del problema para poder comunicarse con clientes y usuarios, y entender sus necesidades.
- Conocer el sistema actual (manual o informatizado).
- Identificar las necesidades, tanto implícitas como explícitas, de clientes y usuarios además de sus espectativas sobre el sistema a desarrolar.

### Técnicas de Elicitación de Requetimientos:
Son métodos y enfoques para utilizados para identificar, recopilar, clarificar y comprender las necesidades y expectativas de los stakeholder con respecto al sistema de software que se desea desarrollar.

#### Métodos Discretos:
Son menos perturbadores a la hora de averiguar los requerimientos, pero se consideran insuficientes para recopilar información por si solos, deben utilizarse junto con uno o varios de los métodos

- _Muestreo de la documentación:_ Recolección de hechos a partir a partir de la documentación existente. Organigramas, memos, notas internas, minutas, solicitudes de proyectos de sistemas de información anteriores, etc.

- _Observación del ambiente de trabajo:_ El analista se convierte en observador de personas y actividades con el objetivo de aprender sobre el sistema.

- _Investigación y visitas al sítio:_
	- Investigar el dominio.
	- Patrones de soluciones (mismo problema en otra organización).
	- Revistas especializadas.
	- Buscar problmeas similares en internet.
	- Consultar otras organizaciones.

#### Métodos Interactivos:
Se usan para obtener requerimientos sobre los miembros de la organización, la base está en hablar con las personas en la organización y escuchar para comprender.

- _Planeación Conjunta de Requetimientos (JRP o JAD):_ Proceso mediante el cual se conducen reuniones de grupo altamente estrucurados con el propósito de analizar problemas y definir requerimientos.

- _Brainstorming:_ Es una técnica para generar ideas, alentando a los participantes a que ofrescan tantas ideas como sea posible. Promueve el desarrollo de ideas creativas para obtener soluciones.

- _Cuestionarios:_ Documento que permite al analista recabar información y opiniones de los encuestados.
	- Recolectando hechos de un grán número de personas.
	- Detectando sentimientos generalizados.
	- Detectando problemas entre usuarios.
	- Cuantificar resupuestas.

- _Entrevistas:_ El analista recolecta información de las personas a través de la interacción cara a cara.
	- Es una conversación con un propósito específico, que se basa en un formato de preguntas y respuestas en general.
	- Se puede conocer las opiniones y sentimientos del encuestado.


## Validación de Requerimientos
Es un proceso que tiene como objetivo asegurar que los requisitos del sistema sean correctos, completos, consistentes y que satisfagan las expectativas y necesidades de los ususarios.
	

## Técnicas de Especificación de Requerimientos

#### Técnicas Estáticas

#### Técnicas Dinámicas

- Historias de Usuario.

- Casos de Usos.

- Diagramas de Transición de Estados.

- Redes de Petri.

- Tablas de Decisión.

## Modelos de Proceso del Software
Es un conjunto de actividades y resultados asociados que producen un producto de software.

### Modelos tradicionales
Formados por un conjunto de fases o actividades en la que no se tiene en cuenta la naturaleza evolutiva del software.

#### Cascada.
Sigue un enfoque lineal y secuencial, donde cada fase del ciclo se completa antes de pasar a la siguiente.

- Su simplicidad hace que sea fácil explicarlo a los clientes.
- La entrega del producto final ocurre al final del ciclo.

#### Modelo en V.
Similar al modelo en cascada, pero con énfasis en la verificación y validación en cada fase. Las actividades de prueba están asociadas directamente con cada fase del desarrollo.
- Las pruebas se realizan en paralelo con las actividades de desarrollo.
- Sugiere que la prueba unitaria y de integración también sea utilizada para para la verificación del diseño del programa.

#### Basado en prototipos.

### Modelos evolutivos.
Modelos que se adaptan a la evolución que sufren los requisitos del sistema en función del tiempo.

#### Desarrollo por fases.
Se desarrolla el sistema de tal manera que se puede ir entregando por partes. Esto implica que existan dos sistemas funcionando en paralelo: el sistema operacional y el sistema en desarrollo.

- Tipos de modelos de desarrollo por faces:

	- _Incremental_: El sistema es particionado en subsistemas de acuerdo con su funcionalidad. Cada entrega agrega un subsistema
	
	- _Iterativo_: Entrega un sistema completo desde el principio y luego aumenta la funcionalidad de cada subsistema con las nuevas versiones.

#### En espiral.



### Metodologías Ágiles
Son un conjunto de principios y prácticas que buscan entregar productos de software de calidad, satisfaciendo las necesidades y expectativas de los clientes, mediante el trabajo colaborativo, la adaptación al cambio y la mejora continua.

Se basan en el Manifiesto Ágil, un documento que establece 4 valores y 12 principios.

- Personas e interacciones por encima de procesos y herramientas.

- Software funcionando por encima de documentación extensiva.

- Colaboración con el cliente por encima de negociación contractual.

- Respuesta al cambio por encima de seguir un plan.


