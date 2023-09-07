###Problema 4: Venta de bebidas
Se desea modelar un sistema para el manejo de venta de bebidas alcohólicas en linea. Para poder empezar a comprar en el sitio, es necesario que las personas se registren ingresando nombre, apellido, mail (será utilizado como nombre de usuario por lo tanto debe ser único) y edad. Solo se permite que se registren al sitio personas mayores a 18 años, de lo contrario el sistema debe mostrar en pantalla el texto de la ley que impide la venta de bebidas alcohólicas a menores. Si el registro es exitoso el sistema genera una contraseña que es enviada al mail ingresado en el registro.

Para comprar el usuario debe iniciar sesión y una vez logueado el sistema muestra una lista de bebidas, una vez que el usuario selecciona todos los productos que desea comprar, si el usuario es premium se le hace un descuento del 20% y se informa en pantalla el total menos el 20%. Ademas si el usuario seleccionó productos por un monto superior a los $4500 se le hace un 10% de descuento y se informa en pantalla el total menos el 10%. Tenga en cuenta que si el usuario es premium y compra por un monto superior a $4500 se deben aplicar ambos descuentos.

**ROL DE USUARIOS:**

- Persona
- Usuario

**HISTORIAS DE USUARIOS:**
	
- Registrar persona.
- Iniciar de Sesión.
- Listar Bebidas
- Elegir bebidas.
- Comprar bebidas.

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
- ID: **Iniciar Sesión.**

- TITULO: Como Usuario quiero iniciar sesión para comprar bebidas

- REGLAS DE NEGOCIO:
	- Usuario y contraseña correctos.¿?
	
####Dorso
- Criterios de aceptación (Iniciar Sesión):

- _Escenario 1: Inicio de sesión exitoso._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Inicio de sesión fallido por contraseña incorrecta._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 3: Inicio de sesión fallido por email incorrecto._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
___

####Frente
- ID: **Listar de bebidas.**

- TITULO: Como Usuario quiero obtener el listado de las bebidas para poder comprar.

- REGLAS DE NEGOCIO:
	- ¿?
	
####Dorso
- Criterios de aceptación (Listar bebidas):

- _Escenario 1: Listado de bebidas exitoso._
	- DADO que hay bebidas con Stock
	- CUANDO el usuario selecciona: "Mostrar bebidas",
	- ENTONCES el sistema muestra una lista con las bebidas con stock
	
- _Escenario 2: Listado de bebidas fallido por no haber stock._ 
	- DADO que no hay stock de bebidas,
	- CUANDO el usuario selecciona: "Mostrar bebidas",
	- ENTONCES el sistema informa que no hay bebidas con stock
	
___

####Frente
- ID: **Elegir bebidas.**

- TITULO: Como usuario quiero Elegir una bebida para poder comprarla.

- REGLAS DE NEGOCIO:
	- ¿?
	
####Dorso
- Criterios de aceptación (Elegir bebida):

- _Escenario 1: Elección de bebidas exitoso._
	- DADO 
	- CUANDO
	- ENTONCES 
	
- _Escenario 2: Elección fallida por falta de stock de la bebida._ 
	- DADO ,
	- CUANDO ,
	- ENTONCES 
___

####Frente
- ID: **Comprar Bebidas.**

- TITULO: Como usuario quiero comprar bebidas para .

- REGLAS DE NEGOCIO:
	Usuario superando el monto a los 4500 se le hace descuento del 10%.
	Usuario Premiun se le hace un descuento del 20%.
	Usuario Premiun con monto mayor a 4500 se le hace descuento del 30%.

####Dorso
- Criterios de aceptación (Comprar Bebidas):

- _Escenario 1: Compra exitosa._
	- DADO que el usuario "no premium" "lalo@gmail.com" que eligió bebidas por un monto menor a $4500,
	- CUANDO el usuario "no premium" selecciona "Comprar",
	- ENTONCES el sistema informa que la compra se realizó con éxito.

- _Escenario 2: Compra exitosa con el 10% de descuento._
	- DADO que el usuario "no premium" "lalo@gmail.com" que eligió bebidas por un monto mayor a $4500,
	- CUANDO el usuario no premium selecciona "Comprar",
	- ENTONCES el sistema informa que la compra se realizó con éxito y con un descuento del 10%.
	
- _Escenario 3: Compra exitosa con el 20% de descuento._ 
	- DADO que el usuario "premium" "pepe@gmail.com" eligió bebidas por un monto menor a $4500,
	- CUANDO el usuario selecciona "Comprar",
	- ENTONCES el sisteama informa que la compra se realizó con éxito y con un descuento del 20%.
	
- _Escenario 4: Compra exitosa con el 30% de descuento._ 
	- DADO que el usuario "premium" "pepe@gmail.com" eligió bebidas por un monto mayor a $4500,
	- CUANDO el usuario selecciona "Comprar",
	- ENTONCES el sisteama informa que la compra se realizó con éxito y con un descuento del 30%.
___

