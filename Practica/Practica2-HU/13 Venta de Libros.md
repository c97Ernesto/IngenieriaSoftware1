### Problema 13: Venta de libros.

Una nueva empresa de venta de libros en línea está diseñando su sitio web. Cualquier visitante puede acceder a su catálogo de libros y navegar los distintos libros que se encuentren en él y solo los usuarios registrados pueden realizar compras.

Para poder comprar los libros se necesita un usuario registrado. El proceso de registro se realiza en dos pasos. En el primer paso el sistema requiere Nombre, Apellido, DNI y cuenta de correo electrónico (que no exista en el sistema) y una clave de 6 caracteres para darlo de alta de forma parcial. En este proceso el sistema debe generar un código de 16 dígitos y enviarlo por correo para que luego el visitante confirme la cuenta. Como segundo paso el visitante debe entrar a la página de confirmación e ingresar su dirección de correo y el código de 16 dígitos. Si estos datos son correctos el sistema lo registra definitivamente como usuario.

Una vez registrado, para autenticarse, el sistema requiere el correo del usuario y la clave de 6 caracteres. Para realizar la compra de un libro el sistema pide ingresar el ISBN del mismo y muestra al usuario la portada con una descripción del libro y la opción “Comprar”. Cuando el usuario selecciona “Comprar” se le pide los datos de la tarjeta: Apellido, Nombre, Nro de tarjeta. Es importante tener en cuenta que por disposición del Banco Central solo el titular de la tarjeta puede realizar la compra, por lo que el nombre y apellido registrado debe coincidir con el de la tarjeta. 

Realizada esta verificación se procede a enviar los datos al servidor de la tarjeta para realizar el cobro. Si todo es correcto se genera un enlace de descarga al correo del usuario.

**ROL DE USUARIOS:**

- Usuario no Registrado.
- Usuario Registrado.

**HISTORIAS DE USUARIOS:**

- Iniciar Registro.
- Finalizar Registro.
- Elegir Libro.
- Comprar Libro.
- Pagar con Tarjeta.
- Iniciar Sesión.
- Cerrar Sesión.

___

#### Frente
- ID: **Iniciar Registro.**

- TITULO: Como Usuario no Registrado quiero iniciar el registro para regitrar la cuenta.

- REGLAS DE NEGOCIO:
	- El correo electrónico no debe estar registrado en el sistema.
	- La clave debe contener 6 caracteres.

**Dorso**

- Criterios de aceptación (Iniciar Registro):

- _Escenario 1: Inicio de Registro Exitoso._
	- DADO que el correo electrónico "pepe@gmail.com" no se encuentra registrado y la clave "312312" contiene 6 caracteres.
	- CUANDO el Usuario no Registrado ingresa: "Pepe", "Villa", "23312654", "pepe@gmail.com", "321312" y presiona "Registrar"
	- ENTONCES el sistema genera un código de 16 dígitos y lo envía al correo electrónico registrado.
	
- _Escenario 2: Inicio de Registro Fallido por correo existente._ 
	- DADO que el correo electrónico "pepe@gmail.com" se encuentra registrado y la clave "444444" contiene 6 caracteres.
	- CUANDO el Usuario no Registrado ingresa: "Lalo", "Landa", "43434323", "pepe@gmail.com", "444444" y presiona "Registrar",
	- ENTONCES el sistema informa que el correo electrónico ingresado ya existe.
	
- _Escenario 2: Inicio de Registro Fallido porque la clave no contiene 6 caracteres._ 
	- DADO que el correo electrónico "usuario1@gmail.com" no se encuentra registrado, pero la clave "j2j2" no contiene 6 caracteres.
	- CUANDO el Usuario no Registrado ingresa: "Marco", "Polo", "12324365", "Marc@gmail.com", "j2j2" y selecciona "Registrar".
	- ENTONCES el sistema informa que la clave ingresado no contiene 6 caracteres.

___

#### Frente
- ID: **Finalizar registro.**

- TITULO: Como Usuario No Registrado quiero finalizar el registro para confirmar mi cuenta.


**Dorso**

- Criterios de aceptación (Finalizar registro):

- _Escenario 1: Finalización del Registro exitosa._
	- DADO que el código "9873847562918403" para la confirmación de la cuenta "usuario97@gmail.com" es correcto
	- CUANDO el Usuario no Registrado ingresa: "usuario97@gmail.com", "9873847562918403", y selecciona "Confirmar Registro"
	- ENTONCES el sistema registra el usuario en el sistema.
	
- _Escenario 2: Finalización de Registro Fallida por código de confirmación incorrecto._ 
	- DADO que el código "811141532313433" para la confirmación de la cuenta "usuario97@gmail.com" es correcto
	- CUANDO el Usuario no Registrado ingresa: "usuario03@gmail.com", "811141532313433"
	- ENTONCES el sistema informa que el código ingresado es incorrecto
	
- _Escenario 3: Finalización de Registro Fallida por correo electrónico inválido._ 
	- DADO que el código "9846292830738203" es correcto, pero el correo electrónico "usuario01@gmail.com" no pertence a ningún inicio de registro.
	- CUANDO el Usuario no Registrado ingresa: "usuario01@gmail.com", "9846292830738203",
	- ENTONCES el sistema informa que el correo electrónico ingresado no coincide con el código.

___

#### Frente
- ID: **Elegir Libro.**

- TITULO: Como Usuario Registrado quiero elegir un libro para poder comprarlo


**Dorso**

- Criterios de aceptación (Elegir libro):

- _Escenario 1: Elección exitosa._
	- DADO que el libro con número de ISBN "213" se encuentra en el catálogo,
	- CUANDO el Usuario Registrado ingresa el número de ISBN "213" y selecciona "Comprar",
	- ENTONCES el sistema redireccióna al Usuario Registrado al pago con tarjeta
	
- _Escenario 2: Elección fallida porque no existe el libro._ 
	- DADO que el libro con número de ISBN "333" no existe
	- CUANDO el usuario Registrado ingresa el número de ISBN "333"
	- ENTONCES el sistema informa que no hay libro con ese número de ISBN.


___

#### Frente
- ID: **Comprar Libro.**

- TITULO: Como Usuario Registrado quiero pagar el libro para comprarlo

- REGLAS DE NEGOCIO:
	- Por disposición del Banco Central solo el titular de la tarjeta puede hacer la compra. 


**Dorso**

- Criterios de aceptación (Comprar Libro):

- _Escenario 1: Compra exitosa._
	- DADO que el nombre "Carlo" y apellido "Magno" registrados en el sistema coinciden con el nombre del titular de la tarjeta y el número de tarjeta 72367832788623478 es válido.
	- CUANDO el Usuario Registrado ingresa nombre y apellido de la tarjeta: "Carlo", "Magno", el número: "72367832788623478" y selecciona "Pagar con Tarjeta"
	- ENTONCES el sistema redirige al usuario a realizar el pago con tarjeta
	
- _Escenario 2: Compra Fallida porque los datos del sistema no coinciden con los de la tarjeta._ 
	- DADO que el nombre "Esteban" y apellido "Quito" registrados, no coinciden con el nombre del titural de la tarjeta y el número de tarjeta 32132132312131212 es válido.
	- CUANDO el Usuario Registrado ingresa nombre y apellido de la tarjeta: "Esteban", "Quito" y número: "32132132312131212", y selecciona "Pagar con Tarjeta"
	- ENTONCES el sistema informa que el nombre o apellido no coinciden con lso registrados en el sistema.
	
- _Escenario 3: Compra Fallida porque número de tarjeta incorrecto._ 
	- DADO que el nombre "Juan" y apellido "Perez" registrados, coinciden con el nombre del titural de la tarjeta, pero el número de tarjeta 32132132312131212 no pertenece a una tarjeta válida.
	- CUANDO el Usuario Registrado ingresa nombre y apellido de la tarjeta: "Juan", "Perez" y número: "32132132312131212", y selecciona "Pagar con Tarjeta"
	- ENTONCES el sistema número de tarjeta ingresado no es válido.
	
___

#### Frente
- ID: **Pagar con tarjeta.**

- TITULO: Como Usuario Registrado quiero pagar con tarjeta para finalizar la compra del libro


**Dorso**

- Criterios de aceptación (Pagar con tarjeta):

- _Escenario 1: Pago exitoso._
	- DADO que hay conexión con el servidor, los datos de la tarjeta son correctos, el código de seguridad "000" pertenece a la tarjeta asociada y la misma tiene saldo.
	- CUANDO el Usuario Registrado ingresa: "000", y selecciona "Realizar Pago"
	- ENTONCES el sistema genera un enlace de descarga al correo del usuario
	
- _Escenario 2: Pago Fallido por no haber conexión con el servidor._ 
	- DADO que no hay conexión con el servidor, pero los datos de la tarjeta son correctos junto con el código de seguridad "999"
	- CUANDO el Usuario Registrado ingresa: "999", y selecciona "Realizar Pago"
	- ENTONCES el sistema informa que no se pudo establecer al conexión con el servidor.
	
- _Escenario 3: Pago fallido por no tener suficiente saldo._ 
	- DADO que hay conexión con el servidor, los datos de la tarjeta son correctos, el código de seguridad "888" también, pero no contiene saldo
	- CUANDO el Usuario Registrado ingresa: "888", y selecciona "Realizar Pago"
	- ENTONCES el sistema informa que la tarjeta no contiene saldo suficiente para realizar el pago.


- _Escenario 4: Pago fallido por código de seguridad de la tarjeta incorrecto._ 
	- DADO que hay conexión con el servidor, los datos de la tarjeta son correctos, pero no el código de seguridad
	- CUANDO el Usuario Registrado ingresa: "1", y selecciona "Realizar Pago"
	- ENTONCES el sistema informa que el código de seguridad no corresponde a la tarjeta asociada.

___

#### Frente
- ID: **Iniciar Sesión.**

- TITULO: Como Usuario Registrado quiero Iniciar Sesión para acceder a las funciones de mi cuenta


**Dorso**

- Criterios de aceptación (Iniciar Sesión):

- _Escenario 1: Inicio de Sesión exitoso._
	- DADO que el correo "juance@gmail.com" y la contraseña "j2j222" coinciden con la base de datos del sistema
	- CUANDO el Usuario Registrado ingresa "juance@gmail.com", "j2j222" y selecciona "Iniciar Sesión"
	- ENTONCES el sistema habilita las funciones del Usuario Registrado
	
- _Escenario 2:._ 
	- DADO que el correo "arac@gmail.com" y la contraseña "ewqeqw" no cpinciden en la base de datos del sistema
	- CUANDO el Usuario Registrado ingresa "arac@gmail.com", "ewqeqw" y selecciona "Iniciar Sesión"
	- ENTONCES el sistema informa que los datos ingresados no pertenecen a una cuenta asociada.
	
___

#### Frente
- ID: **Cerrar Sesión.**

- TITULO: Como Usuario Registrado quiero Cerrar la Sesión para finalizar las funciones de mi cuenta.


**Dorso**

- Criterios de aceptación (Cerrar Sesión):

- _Escenario 1: Cierre de Sesión exitoso._
	- DADO que se desea cerrar la sesión,
	- CUANDO el Usuario Registrado selecciona la opción de "Cerrar Sesión"
	- ENTONCES el sistema informa que se ha cerrado la sesión del usuario


___

#### Frente
- ID: **Comprar Libro.**

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

