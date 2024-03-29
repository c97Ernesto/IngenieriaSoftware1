### Problema 12: Créditos bancarios.
Se desea modelar mediante historias de usuario el manejo de créditos otorgados por un banco a sus clientes.

Los clientes que desean pedir un crédito, deben iniciar un trámite a través de un sitio web del banco ingresando dni, nombre, apellido, mail, tipo de crédito (personal, vivienda, etc.) y monto solicitado. El sistema acepta el inicio de trámite si el dni ingresado corresponde a un cliente del banco y si el crédito solicitado no supera los $400.000. En caso de que no sea cliente del banco el sistema deberá enviar un correo electrónico al email ingresado con un instructivo para hacerse cliente del banco. Si el monto supera los $400.000 el sistema rechaza el inicio de trámite y muestra el mensaje “El monto solicitado excede el límite permitido”. Si los datos son correctos, el sistema almacena el trámite para que sea analizado por el área económica e imprime un número de comprobante para el cliente.

Por otro lado, los clientes pueden consultar el estado de un trámite, para esto es necesario que se ingrese un número de comprobante. Si el número de comprobante es válido, el sistema retorna un informe con el estado del mismo, de lo contrario mostrará un mensaje “trámite inexistente”. Si el cliente ingresa tres veces un código inexistente el sistema bloquea la ip (dirección de red de la máquina que efectúa la consulta) del cliente por 24 horas mostrando un mensaje “Usted ha excedido el número de consultas inválidas”.

Por último, el gerente del banco puede pedir un listado de créditos aprobados entre fechas. Si las fechas ingresadas son válidas, el sistema mostrará un listado con los créditos aprobados, de lo contrario mostrará un mensaje “las fechas ingresadas no son válidas”. El sistema utiliza un sistema de autenticación general del banco, por lo que no es necesario modelar el iniciar y cerrar sesión. Si no hay créditos aprobados para las fechas ingresadas el sistema mostrará el siguiente mensaje: ”No hay créditos aprobados en las fechas ingresadas”.

**ROL DE USUARIOS:**

- Cliente
- Gerente

**HISTORIAS DE USUARIOS:**

- Iniciar trámite.

- Consultar trámite.

- Listar créditos.

___

#### Frente
- ID: **Iniciar trámite.**

- TITULO: Como cliente quiero iniciar un trámite para pedir un crédito en el banco.

- REGLAS DE NEGOCIO:
	- El dni debe corresponder a un cliente del banco.
	- El crédito no debe superar los $400000

**Dorso**

- Criterios de aceptación (Iniciar trámite):

- _Escenario 1: Inicio del trámite exitoso._
	- DADO que el dni "12312312" corresponde a un cliente del banco y el monto solicitado "350000" no supera los $400000.
	- CUANDO el Cliente ingresa: "12312312", "Juan" "Carlos", "juanca@gmail.com", "vivienda", "350000", y selecciona "Iniciar trámite.
	- ENTONCES el sistema almacena el trámite para que sea analizado por el área económica e imprime un número de comprobante para el cliente
	
- _Escenario 2: Inicio de trámite Fallido, porque el dni no pertenece a un cliente del banco._ 
	- DADO que el dni "1231231" no corresponde a un cliente del banco.
	- CUANDO el Cliente ingresa: "1231231", "Juan" "Carlos", "juanca@gmail.com", "vivienda", "350000", y selecciona "Iniciar trámite.
	- ENTONCES el sistema envía un correo elctrónico al email inrgesado con un instructivo para hacerse cliente del banco.
	
- _Escenario 3: Inicio de trámite Fallido, por monto mayor a 400000._ 
	- DADO que el dni "22312312" corresponde a un cliente del banco pero el monto solicitado "450000" supera los $400000.
	- CUANDO el Cliente ingresa: "12312312", "Juan" "Carlos", "juanca@gmail.com", "vivienda", "450000", y selecciona "Iniciar trámite.
	- ENTONCES el sistema rechaza el inicio del trámite e informa "El monto solicitado excede el límite permitido".

___

#### Frente
- ID: **Consultar trámite.**

- TITULO: Como Cliente quiero consultar el estado del trámite

- REGLAS DE NEGOCIO: 
	- Si el cliente ingresa tres veces un código inexistente el sistema bloquea la ip.


**Dorso**
- Criterios de aceptación (Consultar trámite):
- _Escenario 1: Consulta de trámite exitosa._
	- DADO que se ingresa un número de comprobante "0303456" válido, la ip del cliente no se encuentra bloqueada y la cantidad de intentos de consulta es menor a 3.
	- CUANDO el Cliente ingresa: 0303456, y selecciona "Consultar".
	- ENTONCES el sistema retorna un informe con el estado del mismo
	
- _Escenario 2: Consulta del trámite fallida, por número de comprobante inválido._ 
	- DADO que el número de trámite "312312" es incorrecto, la ip del cliente no se encuentra bloqueada, y la cantidad de intentos de consulta es menor a 3.
	- CUANDO el Cliente ingresa: 312312 y selecciona "Consultar".
	- ENTONCES el sistema informa que el trámite es inexistente e incrementa los intentos fallidos del cliente.
	
- _Escenario 3: Consulta del trámite fallida, por número de comprobante inválido y cantidad de intentos igual a 3._ 
	- DADO que el número de trámite "234234" es incorrecto, el cliente no tiene la ip bloqueada y la cantidad de intentos del cliente es igual a 3.
	- CUANDO el Cliente ingresa: "234234" y selecciona "Consultar".
	- ENTONCES el sistema bloquea la ip del cliente, e informa que el trámite es inexistente y que ha excedido el número de consultas inválidas.
	
- _Escenario 4: Consulta del trámite fallida, por IP bloqueada._ 
	- DADO que el número de trámite "987987" es correcto, pero el cliente tiene la IP bloqueda.
	- CUANDO el Cliente ingresa: "987987" y selecciona "Consultar".
	- ENTONCES el sistema informa que no puede realizar la consulta por tener la IP bloqueda.	
	
___

#### Frente
- ID: **Listar Créditos.**

- TITULO: Como Gerente quiero listar crédito para que puedan ser aprobados.
	
#### Dorso
- Criterios de aceptación (Listar Créditos):
- _Escenario 1: Listado Exitoso._
	- DADO que las fechas 1/3/4 y 2/4/4 son válidas, y se aprobaron créditos en esas fechas
	- CUANDO el Gerente ingresa: "1/3/4", "2/4/4" y selecciona "Listar cŕeditos".
	- ENTONCES el sistema muestra el listado de los créditos aprobados en esas fechas
	
- _Escenario 2: Listado Exitoso, listado vacío._ 
	- DADO que las fechas 1/3/6 y 2/4/6 son válidas, y no hay créditos aprobados
	- CUANDO el Gerente ingresa: "1/3/6", "2/4/6" y selecciona "Listar cŕeditos".
	- ENTONCES el sistema informa que no hay créditos aprobados en esas fechas.
	
- _Escenario 3: Listado Fallido, fechas inválidas._ 
		- DADO que las fechas 1/3/26 y 2/4/26 son inválidas,
	- CUANDO el Gerente ingresa: "1/3/26", "2/4/26" y selecciona "Listar cŕeditos".
	- ENTONCES el sistema informa que las fechas ingresadas son inválidas.

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

