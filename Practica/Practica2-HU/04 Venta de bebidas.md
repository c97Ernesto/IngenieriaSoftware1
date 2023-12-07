### Problema 4: Venta de bebidas.
Se desea modelar un sistema para el manejo de venta de bebidas alcohólicas en linea. Para poder empezar a comprar en el sitio, es necesario que las personas se registren ingresando nombre, apellido, mail (será utilizado como nombre de usuario por lo tanto debe ser único) y edad. Solo se permite que se registren al sitio personas mayores a 18 años, de lo contrario el sistema debe mostrar en pantalla el texto de la ley que impide la venta de bebidas alcohólicas a menores. Si el registro es exitoso el sistema genera una contraseña que es enviada al mail ingresado en el registro.

Para comprar el usuario debe iniciar sesión y una vez logueado el sistema muestra una lista de bebidas, una vez que el usuario selecciona todos los productos que desea comprar, si el usuario es premium se le hace un descuento del 20% y se informa en pantalla el total menos el 20%. Ademas si el usuario seleccionó productos por un monto superior a los $4500 se le hace un 10% de descuento y se informa en pantalla el total menos el 10%. Tenga en cuenta que si el usuario es premium y compra por un monto superior a $4500 se deben aplicar ambos descuentos.

**ROL DE USUARIOS:**

- Persona

- Usuario

**HISTORIAS DE USUARIOS:**

- Comprar bebidas.

- Registrar persona.

- Iniciar de Sesión.

- Cerrar Sesión

___


#### Frente
- ID: **Comprar Bebidas.**

- TITULO: Como usuario quiero seleccionar babidas para comprarlas.

- REGLAS DE NEGOCIO:
	- Usuario superando el monto a los 4500 se le hace descuento del 10%.
	- Usuario Premiun se le hace un descuento del 20%.
	- Usuario Premiun con monto mayor a 4500 se le hace descuento del 30%.

**Dorso**

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
	- ENTONCES el sistema informa que la compra se realizó con éxito y con un descuento del 20%.
	
- _Escenario 4: Compra exitosa con el 30% de descuento._ 
	- DADO que el usuario "premium" "pepe@gmail.com" eligió bebidas por un monto mayor a $4500,
	- CUANDO el usuario selecciona "Comprar",
	- ENTONCES el sistema informa que la compra se realizó con éxito y con un descuento del 30%.

___

#### Frente
- ID: **Registrar Persona.**	

- TITULO: Como Persona quiero ingresar mis datos para registrarme.

- REGLAS DE NEGOCIO:
	- El mail tiene que ser único.
	- Solo personas mayores de 18 años
	

**Dorso**

- Criterios de aceptación (Registrar Persona):

- _Escenario 1: Registro exitoso de la persona._
	- DADO que el email "email@gmail.com" no se encuentra registrado, y la persona es mayor de edad,
	- CUANDO el Persona ingresa: "Juan", "Perez", "email@gmail.com", "24", y presiona "Registrarse",
	- ENTONCES el sistema registra al nuevo Usuario, genera una contraseña y la envía al email registrado.
	
- _Escenario 2: Registro fallido por ingresar correo existente en el sistema._ 
	- DADO que el email "email2@gmail.com" se encuentra registrado, 
	- CUANDO el Persona ingresa: "Juan", "Perez", "email2@gmail.com", "24", y presiona "Registrarse".
	- ENTONCES el sistema informa que ese email ya se encuentra registrado.
	
- _Escenario 3: Registro fallido por no ser mayor de edad._
	- DADO que el email "email3@gmail.com" no se encuentra registrado, pero la persona es menor de edad,
	- CUANDO el Persona ingresa: "Juan", "Perez", "email3@gmail.com", "17", y presiona "Registrarse".
	- ENTONCES el sistema informa que se impide la venta de bebidads alcohólicas a menores de edad.

___

#### Frente
- ID: **Iniciar Sesión.**

- TITULO: Como Usuario quiero iniciar sesión para comprar bebidas.
	
	
**Dorso**

- Criterios de aceptación (Iniciar Sesión):

- _Escenario 1: Inicio de sesión Exitoso._
	- DADO que el mail "asd@gmai.com" y la contraseña "123" se encuentran registrados en el sistema,
	- CUANDO el Usuario ingresa: "asd@gmail.com", "123", y selecciona "Iniciar Sesión".
	- ENTONCES el sistema habilita las funciones del Usuario e informa el correcto inicio de sesión.
	
- _Escenario 2: Inicio de sesión Fallido por contraseña incorrecta._ 
	- DADO que el mail "asd@gmai.com" se encuentra en el sistema, pero no coincide la contraseña "321"
	- CUANDO el Usuario ingresa: "asd@gmail.com", "321", y selecciona "Iniciar Sesión".
	- ENTONCES el sistema informa que la contraseña es incorrecta.
	
- _Escenario 3: Inicio de sesión Fallido por email incorrecto._ 
	- DADO que el mail "dsa@gmail.com" no se encuentra en el sistema,
	- CUANDO el Usuario ingresa: "dsa@gmail.com", "123", y selecciona "Iniciar Sesión".
	- ENTONCES el sistema informa que el email ingresado no pertenece a una cuenta registada en el sistema.
	
___

#### Frente
- ID: **Cerrar Sesión.**

- TITULO: Como Usuario quiero cerrar sesión para finalizar.



**Dorso**

- Criterios de aceptación (Cerrar Sesión):

- _Escenario 1: Cierre de Sesión Exitoso._
	- DADO que se encuentra la sesión del usuario abierta,
	- CUANDO el Usuario selecciona la opción de "Cerrar Sesión".
	- ENTONCES el sistema cierra la sesión del usuario y deshabilita sus funciones.
	

