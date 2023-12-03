### Problema 7: Mutual.

Una mutual necesita automatizar el manejo de las prestaciones que ofrece a sus afiliados.

Una persona puede afiliarse sólo si posee una tarjeta de crédito para que se pueda hacer el pago de la cuota mensual automáticamente. Una vez que la persona se ha afiliado, puede pasar a tener a cargo a su pareja e hijos (hasta 18 años, luego es dado de baja). A cada uno se le otorga un número de afiliado.

Las prestaciones que brinda, siempre y cuando esté asentado el pago del mes anterior al que es solicitado, son:

- Ortodoncia: Se reconoce sólo una y a los afiliados menores de 15 años que estén afiliados desde al menos nueve meses. Debe presentarse historia clínica elaborado por el profesional.
- Plantillas: A cualquier afiliado, hasta dos por año calendario. Debe presentarse la indicación del profesional y factura del comercio que la confeccionó.
- Anteojos: A cualquier afiliado con fecha de afiliación superior a tres meses, un par cada 18 meses. 
- Internación: A cualquier afiliado, sin límite.
- Consultas médicas: A cualquier afiliado, hasta 2 por mes.

**ROL DE USUARIOS:**

- Persona.
- Afiliado.


**HISTORIAS DE USUARIOS:**

- Afiliar Persona.
- Prestar Ortodoncia.
- Prestar Plantillas.
- Prestar Anteojos.
- Prestar Internación.
- Prestar Consulta Médica.
___

#### Frente
- ID: **Afiliar Persona.**

- TITULO:

- REGLAS DE NEGOCIO:
	- Poseer tarjeta de crédito.


**Dorso**

- Criterios de aceptación (Afiliar Persona):

- _Escenario 1: Afiliación exitosa._
	- DADO que se posee una tarjeta de crédito válida
	- CUANDO la Persona solicita la afiliación a la mutual
	- ENTONCES el sistema registra la persona como afiliado y a sus familiares
	
- _Escenario 2: Afiliación fallida por tener una tarjeta de crédito inválida._ 
	- DADO que no posee una tarjeta de crédito válida,
	- CUANDO la Persona solicita la afiliación a la mutual
	- ENTONCES el sistema informa que la tarjeta no es válida
	
- _Escenario 2: ._ 
	- DADO 
	- CUANDO
	- ENTONCES
___

#### Frente
- ID: **Prestar Ortodoncia.**

- TITULO: Como afiliado quiero hacer uso de la prestación para pedir ortodoncia.

- REGLAS DE NEGOCIO:
	- Asentado el pago del mes anterior.
	- Se reconoce una ortodondia.
	- Menor de 15 años con afiliación desde al menos 9 meses.
	- Presentar historia clínica.


**Dorso**

- Criterios de aceptación (Prestar ortodoncia):

- _Escenario 1: Prestación exitosa._
	- DADO que está asentado el pago del mes anterior, no hay ortodoncia reconocida, la persona tiene 12 años, se encuentra afiliado hace 1 año y 6 meses, y presentó historia clínica.
	- CUANDO el afiliado solicita el préstamo de la Ortodoncia
	- ENTONCES el sistema registra la prestación de la ortodoncia al afiliado
	
- _Escenario 2: Prestación fallida por no tener asentado el pago del mes anterior._ 
	- DADO que no se encuentra asentado el pago del mes anterior, no hay ortodoncia reconocida, la persona tiene 14 años y 256 días, se encuentra afiliado hace 9 meses y un día, y presentó historia clínica.
	- CUANDO el afiliado solicita el préstamo de Ortodoncia
	- ENTONCES el sistema informa que el afiliado no tiene asentado el pago del mes anterior.
	
- _Escenario 3: Prestación fallida por tener ortodoncia reconocida._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 4: Prestación fallida porque el afiliado es mayor de 15 años._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 5: Prestación fallida porque el afiliado no es afiliado hace más de 9 meses._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 6: Prestación fallida porque el afiliado no presentó/presenta historia clínica._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
___

#### Frente
- ID: **Prestar Plantillas.**

- TITULO: Como afiliado quiero hacer uso de la prestación para pedir plantillas.

- REGLAS DE NEGOCIO
	- Tener asentado el pago del mes anterior.
	- Solo dos por año.
	- Haber indicación del profesional.
	- Presentar factura del comercio que la confeccionó.

**Dorso**

- Criterios de aceptación (Prestar Plantillas):

- _Escenario 1: Prestación exitosa._
	- DADO que se encuentra asentado el pago del mes anterior, solo se encuentra una prestación del servicio (Plantillas), hay indicación del profesional y está presente la factura del comercio que la confeccionó.
	- CUANDO el Afiliado solicita el préstamo de Plantillas,
	- ENTONCES el sistema registra la prestación de las plantillas al afiliado
	
- _Escenario 2: Prestación fallida por tener dos prestaciones del servicio._ 
	- DADO que se encuentra asentado el pago del mes anterior, hay indicación del profesional, está presente la factura del comercio que la confeccionó, pero ya hay dos prestaciones del servicio
	- CUANDO el Afiliado solicita el prestamo del servicio de Plantillas,
	- ENTONCES el sistema informa que ya se solicitaron las dos prestaciones por año.
	
- _Escenario 3: Prestación fallida por no tener asentado el pago del mes anterior._ 
	- DADO 
	- CUANDO
	- ENTONCES

- _Escenario 4: Prestación fallida por no haber indicación del profesional._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 5: Prestación fallida no tener la factura del comercio que confeccionó las plantillas._ 
	- DADO 
	- CUANDO
	- ENTONCES
___

#### Frente
- ID: **Prestar Anteojos.**

- TITULO: Como afiliado quiero hacer uso de la prestación para pedir Anteojos.

- REGLAS DE NEGOCIO
	- Haber hecho el pago del mes anterior.
	- Ser afiliado hace más de tres meses.
	- Haber solicitado el último par hace más de 18 meses.


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
- ID: **Prestar Internación.**

- TITULO: Como afiliado quiero hacer uso de la prestación para pedir una Internación.

- REGLAS DE NEGOCIO.
	- Tener el pago del mes anterior asentado


**Dorso**

- Criterios de aceptación (Prestar Internación):

- _Escenario 1: Prestación exitosa._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Prestación fallida por no tener asentado el pago del mes anterior._ 
	- DADO 
	- CUANDO
	- ENTONCES
	


___

#### Frente
- ID: **Prestar Consulta Médica.**

- TITULO: 
	- Tener el pago del mes anterior.
	- Dos solicitudes por mes.

**Dorso**

- Criterios de aceptación (Prestar consulta médica):

- _Escenario 1: Prestación exitosa._
	- DADO que se encuentra asentado el pago del mes anterior, y no se han hecho solicitudes de consulta médica.
	- CUANDO el Afiliado solicita la prestación de la consulta médica.
	- ENTONCES el sistema registra la prestación
	
- _Escenario 2: Prestación fallida por no tener el pago del mes anterior._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 3: Consulta fallida por ya tener dos prestaciones de consulta médica._ 
	- DADO 
	- CUANDO
	- ENTONCES

