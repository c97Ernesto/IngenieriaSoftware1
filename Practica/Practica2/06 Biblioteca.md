### Problema 6: Biblioteca.

**ROL DE USUARIOS:**

- Alumno. 
- Socio.
- Bibliotecario

**HISTORIAS DE USUARIOS:**
	
- Asociar alumnos.
- Prestar libros.
- Verificar pŕestamo.	


#### Frente
- ID: **Asociar Alumnos.**

- TITULO: Como Bibliotecaria quiero asociar un alumno para que éste pueda retirar libros.

- REGLAS DE NEGOCIO: 
	- Presentar DNI y certificado de alumno regular del alumno a asociar.

#### Dorso
- Criterios de aceptación (Asociar alumno):
- _Escenario 1: Asociación del alumno exitosa._
	- DADO el alumno que presenta su correspondido DNI y certificado de alumno regular
	- CUANDO la bibliotecaria ingresa: "1765678" y los datos correspondientes del ceritificado
	- ENTONCES el sistema informa que el alumno fue asociado correctamente.
	
- _Escenario 2: Asociacion del alumno fallida por DNI incorrecto._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Asociacion del alumno fallida por datos del certificado incorrecto._ 
	- DADO 
	- CUANDO
	- ENTONCES

___


#### Frente
- ID: **Prestar Libros.**

- TITULO: Como Bibliotecaria quiero realizar un préstamo para un alumno

- REGLAS DE NEGOCIO: 
	- socios habilitados, que no posean más de tres préstamos vigentes y no
	tengan préstamos vencidos.
	
#### Dorso
- Criterios de aceptación (Prestar Libros):
- _Escenario 1: Prestación exitosa._
	- DADO que el socio se encuentra habilitado,
	- CUANDO la bibliotecaria ingresa el DNI: "123123" y éste se encuentra habilitado,
	- ENTONCES el sistema informa que es socio se encuentra habilitado y registra el préstamo del libro.
	
- _Escenario 2: Error al prestar libro por socio inhabilitado por poseer más de tres préstamos vigentes._ 
	- DADO que el socio con DNI 123123 posee más de tres préstamos,
	- CUANDO la bibliotecaria ingresa: "123123" y éste se encuentra inhabilitado por poseer más de tres préstamos.
	- ENTONCES el sistema informa que el socio está inhabilitado por poseer más de tres préstamos.

- _Escenario 3: Error al prestar libro por socio inhabilitado por tener préstamos vencidos._ 
	- DADO que el socio con DNI 123123 tiene préstamos vencidos,
	- CUANDO la bibliotecaria ingresa: "123123" y este se encuentra inhabilitado por tener préstamos vencidos.
	- ENTONCES el sistema informa que el socio se encuentra inhabilitado por tener préstamos vencidos.

___

#### Frente
- ID: **Verificar Préstamo.**

- TITULO: Como bibliotecaria quiero verificar un pŕestamo para ver que no se encuentre vencido

- REGLAS DE NEGOCIO
	-
	
#### Dorso
- Criterios de aceptación (Verificar Pŕestamo):
- _Escenario 1: Verificación del préstamo exitoso, préstamo vencido._
	- DADO que el socio hace la devolución del préstamo y este se encuentra vencido,
	- CUANDO la bibliotecaria ingresa el DNI: "123123",
	- ENTONCES el sistema informa que el préstamo se encuentra vencido, y registra una suspención de 15 días.
	
- _Escenario 2: Verificación del préstamo exitoso, préstamo no vencido._ 
	- DADO que el socio hace la devolución del préstamo y este no se encuentra vencido,
	- CUANDO la bibliotecaria ingresa el DNI: "234234",
	- ENTONCES el sistema registra la devolución del préstamo.

