### Problema 9: Pago electrónico.

**ROL DE USUARIOS:**

- Gerente de Sucursal

- Gerente
 

**HISTORIAS DE USUARIOS:**

- Recuperar datos de Factura.

- Registrar Pagos.

- Ver estadísticas


#### Frente
- ID: **Recuperar datos de factura.**

- TITULO: Como Gerente de Sucursal quiero recuperar los datos de una factura para informar el monto.

- REGLAS DE NEGOCIO: 

	- 2do vencimiento vencido, no se puede cobrar por dicho motivo.	
	- 1er vencimiento vencido, aplicar cargos al monto original.

#### Dorso
- Criterios de aceptación (Recuperar datos de la Factura):

- _Escenario 1: Recuperación de factura exitosa sin vencimientos._

	- DADO que el código de pago electrónico es correcto, la conexión con la central de cobro es correcta, y la factura no tiene vencimientos,
	
	- CUANDO el Gerente ingresa: "Empresa1", "0303456", "02/02/2022", "03/03/2022", "$1000", "7000".
	
	- ENTONCES el sistema informa el monto original de la factura.
	
	
- _Escenario 2: Recuperación de factura exitosa con 1er vencimiento._ 
	- DADO que la 1ra fecha de vencimiento fue superada,
	
	- CUANDO el Gerente ingresa: "Empresa1", "0303456", "02/02/2022", "03/03/2022", "$1000", "7000".
	
	- ENTONCES el sistema informa el monto original de la factura más un recargo.
	
	
- _Escenario 2: Recuperación de factura exitosa con 2do vencimiento._ 

	- DADO que la segundo fecha de vencimiento fue superada,
	
	- CUANDO el Gerente ingresa: "Empresa1", "0303456", "02/02/2022", "03/03/2022", "$1000", "7000".
	
	- ENTONCES el sistema informa que la factura no se puede cobrar por superar la 2da fecha de vencimiento.

___


#### Frente
- ID: **Registrar Pagos.**

- TITULO: Como Gerente de Sucursal quiero ingresar una clave para registrar los pagos.

- REGLAS DE NEGOCIO: 

	- No deben enviarse dos veces las transacciones.
	
	
#### Dorso
- Criterios de aceptación ():

- _Escenario 1: Registro de pagos exitoso._

	- DADO 
	
	- CUANDO 
	
	- ENTONCES
	
	
- _Escenario 2: Registro de pagos fallido por clave incorrecta._ 
	- DADA 
	- CUANDO
	- ENTONCES

- _Escenario 3: Registro de pagos fallido por conexión incorrecta con la central de cobros._ 
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 4: Registro de pagos fallido por querer enviar pos 2da vez los pagos._ 
	- DADA 
	- CUANDO
	- ENTONCES
___

#### Frente
- ID: **Ver estadísticas.**

- TITULO: Como Gerente quiero ingresar clave maestra para ver las estadísticas de los servicios e impuestos cobrados.

- REGLAS DE NEGOCIO: 
	- 

	
#### Dorso
- Criterios de aceptación (Ver estadísticas):
- _Escenario 1: Visualización exitosa de las estadísticas._
	- DADO que el gerente  
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Error al visualizar las estadísticas por clave incorrecta._ 
	- DADA 
	- CUANDO
	- ENTONCES

___

#### Frente
- ID: **.**

- TITULO:

- REGLAS DE NEGOCIO: 

	
#### Dorso
- Criterios de aceptación ():
- _Escenario 1: ._
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADA 
	- CUANDO
	- ENTONCES


