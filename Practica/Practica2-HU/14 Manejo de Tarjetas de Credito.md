### Problema 14: Manejo de Tarjetas de Créditos.
La gerencia del banco donde trabajamos nos pide realizar un subsistema para el manejo de las tarjetas de crédito SIVA.

El sistema podrá ser operado únicamente por el personal de área comercial y por el gerente de la sucursal. En ambos casos las funcionalidades solo serán habilitadas con autenticación previa.

El registro del personal en el sistema no es necesario implementarlo, ya que las credenciales son obtenidas del sistema central del banco. Entonces, para autenticarse, el usuario debe ingresar sus credenciales (las mismas que usa para otros servicios del banco) y estas son corroboradas por el sistema del banco central (al cual nos comunicamos por intranet), enviándonos un token de autenticación válido en caso de ser correctas.

Una vez autenticado, todo el personal debe poder dar de alta una nueva tarjeta y dar de baja una existente. 

Para dar de alta se requiere nombre completo, DNI y CUIT del titular. Luego, se debe seleccionar un tipo de tarjeta (Básica o Gold). Para dar de alta la tarjeta la persona debe ser cliente del banco y no podrá darse de alta una tarjeta si la persona es morosa en el sistema SIVA (externo al banco). Para esto, nuestro sistema debe comunicarse con el SIVA y verificar la morosidad de la persona con el DNI. En el mismo momento, el sistema SIVA nos dará un número de tarjeta nuevo.

Para dar de baja una tarjeta, simplemente se debe ingresar el número de tarjeta y el sistema la debe eliminar de la base de datos del banco.

El gerente, además, podrá pedir un listado de las operaciones realizadas entre dos fechas. Para esto el sistema le pedirá que ingrese ambas fechas y le mostrará un listado. No debe ser posible ingresar fechas futuras al presente, ni tampoco que la fecha de inicio sea mayor a la fecha de fin.

**ROL DE USUARIOS:**

- 
- 

**HISTORIAS DE USUARIOS:**

- 
- 
- 

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

