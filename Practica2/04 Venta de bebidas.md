###Problema 4: Venta de bebidas
Se desea modelar un sistema para el manejo de venta de bebidas alcohólicas en linea. Para poder empezar a comprar en el sitio, es necesario que las personas se registren ingresando nombre, apellido, mail (será utilizado como nombre de usuario por lo tanto debe ser único) y edad. Solo se permite que se registren al sitio personas mayores a 18 años, de lo contrario el sistema debe mostrar en pantalla el texto de la ley que impide la venta de bebidas alcohólicas a menores. Si el registro es exitoso el sistema genera una contraseña que es enviada al mail ingresado en el registro.

Para comprar el usuario debe iniciar sesión y una vez logueado el sistema muestra una lista de bebidas, una vez que el usuario selecciona todos los productos que desea comprar, si el usuario es premium se le hace un descuento del 20% y se informa en pantalla el total menos el 20%. Ademas si el usuario seleccionó productos por un monto superior a los $4500 se le hace un 10% de descuento y se informa en pantalla el total menos el 10%. Tenga en cuenta que si el usuario es premium y compra por un monto superior a $4500 se deben aplicar ambos descuentos.

**ROL DE USUARIOS:**

- Persona
- Usuario

**HISTORIAS DE USUARIOS:**

- Registrar persona.
- Inicio de Sesión del usuario¿?.
- Sleccionar Bebidas¿?
- Comprar siendo Usuario Premium.
- Comprar siendo Usuario Normal.
___

####Frente
- ID: **Registrar Persona.**

- TITULO: Como Persona quiero registrarme en el sistema para comprar bebidas.

- REGLAS DE NEGOCIO:
	- El mail tiene que ser único.
	- Solo personas mayores de 18 años
	

####Dorso
- Criterios de aceptación (Registrar Persona):

- _Escenario 1: Registro exitoso de la persona._
	- DADO que el email "email@gmail.com" no se encuentra registrado
	- CUANDO la persona ingresa: "Juan", "Perez", "email@gmail.com", "24", y presiona "Registrarse",
	- ENTONCES el sistema informa que la persona se registro correctamente y lo redirige al inicio de sesión
	
- _Escenario 2: Registro fallido por ingresar correo existente en el sistema._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 3: Registro fallido por no ser mayor de edad._
	- DADO
	- CUANDO
	- ENTONCES

___

####Frente
- ID: **.**

- TITULO:

- REGLAS DE NEGOCIO: 
	- 
	
####Dorso
- Criterios de aceptación (Verificar CUIT):

- _Escenario 1:._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 3:._ 
	- DADO 
	- CUANDO
	- ENTONCES
___

####Frente
- ID: **.**

- TITULO:

- REGLAS DE NEGOCIO:
	- 

####Dorso
- Criterios de aceptación ():

- _Escenario 1: ._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: ._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
___

####Frente
- ID: **.**

- TITULO:

- REGLAS DE NEGOCIO: 
	- 
	- 
	
####Dorso
- Criterios de aceptación ():
- _Escenario 1: ._
	- DADA 
	- CUANDO
	- ENTONCES
	
- _Escenario 2:._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 3:._ 
	- DADO 
	- CUANDO
	- ENTONCES
