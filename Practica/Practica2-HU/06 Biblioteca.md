### Problema 6: Biblioteca.

**ROL DE USUARIOS:**

- Alumno
- Socio
- Bibliotecaria

**HISTORIAS DE USUARIOS:**
	
- Asociar alumno.
- Prestar libros.
- Verificar pŕestamo.	


#### Frente
- ID: **Asociar Alumno.**

- TITULO: Como Bibliotecaria quiero asociar un alumno para que éste pueda retirar libros.

- REGLAS DE NEGOCIO: 
	- Presentar DNI y certificado de alumno regular del alumno a asociar.

**Dorso**

- Criterios de aceptación (Asociar alumno):

- _Escenario 1: Asociación Exitosa del Alumno._
	- DADO el alumno que presenta su correspondido DNI y certificado de alumno regular,
	- CUANDO la bibliotecaria ingresa: "1765678", los datos correspondientes del ceritificado, y selecciona la opción de "Asosciar Alumno".
	- ENTONCES el sistema informa y registra el alumno.
	
- _Escenario 2: Asociacion Fallida por datos incorrectos del certificado._ 
	- DADO el alumno que presenta su correspondido DNI y certificado de alumno regular
	- CUANDO la bibliotecaria ingresa: "123123", los datos correspondientes del certificado y y selecciona la opción de "Asosciar Alumno".
	- ENTONCES el sistema informa que los datos ingresados no corresponden a un alumno.

___


#### Frente
- ID: **Prestar Libro.**

- TITULO: Como Bibliotecaria quiero realizar un préstamo para un alumno

- REGLAS DE NEGOCIO: 
	- socios habilitados, que no posean más de tres préstamos vigentes y no
	tengan préstamos vencidos.
	
**Dorso**

- Criterios de aceptación (Prestar Libros):

- _Escenario 1: Prestación exitosa._
	- DADO que el socio se encuentra habilitado, no posee más de tres préstamos vigentes y no tiene préstamos vencidos.
	- CUANDO la bibliotecaria ingresa el DNI: "123123" y selecciona la opción de "Realizar Préstamo".
	- ENTONCES el sistema informa que es socio se encuentra habilitado y registra el préstamo del libro.
	
- _Escenario 2: Prestación Fallida por socio inhabilitado._ 
	- DADO que el socio se encuentra habilitado, no posee más de tres préstamos vigentes y no tiene préstamos vencidos.
	- CUANDO la bibliotecaria ingresa el DNI: "123123" y selecciona la opción de "Realizar Préstamo".
	- ENTONCES el sistema informa que el socio no se encuentra habilitado.

- _Escenario 3: Prestación Fallida por socio inhabilitado al poseer más de tres préstamos vigentes._
	- DADO que el socio posee más de tres préstamos vigentes,
	- CUANDO la bibliotecaria ingresa el DNI: "123123" y selecciona la opción de "Realizar Préstamo".
	- ENTONCES el sistema informa que el socio no se encuentra habilitado por poseer más de tres préstamos vigentes.
	
- _Escenario 4: Prestación Fallida por socio inhabilitado al tener préstamos vencidos._
	- DADO que el socio tiene préstamos vencidos,
	- CUANDO la bibliotecaria ingresa el DNI: "123123" y selecciona la opción de "Realizar Préstamo".
	- ENTONCES el sistema informa que el socio no se encuentra habilitado por tener pŕestamos vencidos.

___

#### Frente
- ID: **Verificar Préstamo.**

- TITULO: Como bibliotecaria quiero verificar un pŕestamo para ver que no se encuentre vencido.

- REGLAS DE NEGOCIO
	- 
	
**Dorso**

- Criterios de aceptación (Verificar Pŕestamo):

- _Escenario 1: Verificación Exitosa del préstamo, préstamo vencido._
	- DADO que se ingresa el DNI del asociado para hacer el registro del préstamo,
	- CUANDO la bibliotecaria ingresa el DNI: "123123",
	- ENTONCES el sistema informa que el préstamo se encuentra vencido, y registra una suspención de 15 días.
	
- _Escenario 2: Verificación Exitosa del préstamo, préstamo no vencido._ 
	- DADO que se ingresa el DNI del asociado para hacer el registro del préstamo,
	- CUANDO la bibliotecaria ingresa el DNI: "234234",
	- ENTONCES el sistema registra la devolución del préstamo.

