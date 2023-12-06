## Problema 5: Impresión de fotos.

Se desea desarrollar un sistema para la impresión de fotos para una casa fotográfica. Los clientes pueden subir sus fotos, pagar por internet y luego ser retiradas personalmente por el local.

Para subir las fotos la persona debe registrarse en el sitio, ingresando sus datos personales, nombre, apellido, email, domicilio, nombre de usuario y contraseña.

Una vez autenticado, el usuario puede subir un máximo de 50 fotos para ser impresas. Las fotos se ingresan de a una. Una vez subidas, el usuario debe abonar el monto total (el valor de cada foto es de $15). El pago se realiza con tarjeta de crédito, ingresando los datos de la misma (número de tarjeta, código de seguridad y nombre del titular), la cual debe ser validada a través del sistema del banco. Una vez que se realiza el pago se le otorga al cliente un código único que le servirá posteriormente para retirar las fotos.

Un cliente debe acercarse a la sucursal para retirar las fotos enviadas previamente. Para esto debe presentar el código único a un empleado. Este registra el código, la fecha de retiro y entrega las fotos al cliente.

![ejercicio5](./drawios/ejercicio05_P3.drawio.png)

**Actores:**

- Usuario no registrado

- Usuario registrado

- Servidor externo

- Empleado

**Casos de Usos**

- Cargar Fotos.

- Realizar Pago.

- Pagar con Tarjeta.

- Registrar Retiro.

- Registrar Usuario.

- Iniciar Sesión.

- Cerrar Sesión.

___

#### Nombre del caso de uso:

- Cargar Imágenes

**Descripción:** 

- Este caso de uso describe el evento en el que un usuario registrado sube fotos al sistema.

**Actores:** 

- Usuario Registrado

**Precondiciones:**

- El usuario debe tener una sesión iniciada.

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Usuario Registrado selecciona la opción de "Subir Imagen"
	
	- Paso 4: el Usuario Registrado sube una imagen
	
	- Paso 6: el usuario selecciona la opción de "Realizar Pago"

- **Acciones del Sistema:**

	- Paso 2: el sistema verifica la cantidad de imágenes ingresadas
	
	- Paso 3: el sistema solicita el ingreso de una imagen
	
	- Paso 5: el sistema registra la imagen ingresada y habilita la función de "Realizar Pago"
	
	- Paso 7: el sistema se ejecuta el CU "Realizar Pago".
	
	
**Curso Alterno:**

- Paso alternativo 2: La cantidad de imágenes ingresadas llegó al máximo permitido. Se notifica y salta al paso 7.

- Paso alternativo 6: El usuario registrado selecciona la opción de "Subir Foto". Se retorna al paso 2.

- Paso alternativo 7: No se registra el pago. Se notifica y finaliza el CU.
	
**Postcondición:**

- Se hace la carga de imágenes.

___

#### Nombre del caso de uso:

- Realizar Pago.

**Descripción:** 

- Este caso de Uso describe el evento en el que el Usuario Registrado realiza el pago recibiendo el código de retiro de imágenes.

**Actores:** 

- Usuario Registrado.

**Precondiciones:**

- Haber ejecutado el Caso de Uso: Cargar Fotos.

**Curso Normal:**

- **Acción del Actor:**

	- Paso 3: el Usuario Registrado ingresa los datos de la tarjeta
	
	-

- **Acciones del Sistema:**

	- Paso 1: El sistema calcula el monto de las imágenes cargadas.
	
	- Paso 2: el sistema solicita los datos de la tarjeta
	
	- Paso 4: el sistema ejecuta el Caso de Uso "Pagar con Tarjeta"
	
	- Paso 5: el sistema registra el pago y hace la entrega del código único de retiro.

**Curso Alterno:**

- Paso alternativo 4: no se registra el pago. Se informa y finaliza el CU

**Postcondición:**

- Se hace entrega del ćodigo de retiro de las imágenes.

___

#### Nombre del caso:

- Pagar con Tarjeta.

**Descripción**

- Este Caso de Uso describe el evento en el que se realiza el pago de las imágenes.

**Actores**

- Servidor externo.

**Precondiciones**

- Haber ejecutado el Caso de Uso: Realizar Pago.

**Curso Normal:**

- **Acción del Actor:**
	
	- Paso 2: el sistema externo acepta la conexión
	
	- Paso 4: el servidor externo valida los datos y los fondos de la cuenta
	
	- Paso 5: el servidor externo retorna el estado de la tarjeta

- **Acciones del Sistema:**
	
	- Paso 1: el sistema establece conexión con el servidor externo
	
	- Paso 3: el sistema envía los datos de las tarjeta
	
	- Paso 6: el sistema recibe que los datos de la tarjeta son correctos y posee fondos suficientes
	
	- Paso 7: el sistema registra el pago y cierra la conexión con el servidor externo

**Curso Alterno:**

- Paso alternativo 2: Falla la conexión con el servidor externo. Se notifica y termina el Caso de Uso.

- Paso alternativo 6: los datos de la tarjeta son incorrectos. Se notifica y se retorna al paso 1.

- Paso alternativo 6: la cuenta no tiene fondos suficientes. Se notifica y termina el Caso de Uso.

**Postcondición:**

- Se efectúa el pago de las imágenes con tarjeta de crédito.

___

#### Nombre del caso:

- Registrar retiro.

**Descripción**

- Este Caso de uso describe el evento en el que el Empleado registra el retiro de las imágenes.

**Actores**

- Empleado.

**Precondiciones**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: el empleado selecciona "Registrar código de retiro"
	
	- Paso 3: el empleado ingresa el código provisto
	
	- Paso 6: el empleado ingresa la fecha de retiro de las imágenes

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita el código único de retiro
	
	- Paso 4: el sistema verifica el código ingresado
	
	- Paso 5: el sistema solicita la fecha del retiro
	
	- Paso 7: el sistema verifica la fecha
	
	- Paso 8: se registra el retiro de las imágenes

**Curso Alterno:**

- Paso alternativo 4: el código ingresado no corresponde a un código único. Se notifica y se vuelve al paso 2

- Paso alternativo 6: la fecha ingresada es incorrecta. Se notifica y se vuelve al paso 5

**Postcondición:**

 Se registra el retiro de las imágenes.

___

#### Nombre del caso de uso:

- Registrar Usuario

**Descripción:** 

- Este Caso de Uso describe el evento en el que una persona ingresa sus datos para hacer el registro de una cuenta en el sistema.

**Actores:** 

- Usuario no Registrado.

**Precondiciones:**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Usuario no Registrado selecciona la opción de "Registrarse"
	
	- Paso 3: el usuario ingresa los datos solicitados
	
	- Paso 5: el usuario ingresa el email, nombre de usuario y contraseña.

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita los datos de la persona
	
	- Paso 4: el sistema pide email, nombre de usuario único y contraseña.
	
	- Paso 6: el sistema verifica los datos ingresados
	
	- Paso 7: el sistema registra la cuenta en el sistema.

**Curso Alterno:**
	
- Paso alternativo 6: El nombre de usuario ya existe en el sistema. Se notifica y se vuelve al paso 4.
	
- Paso alternativo 6: La contraseña ingresada es demasiado corta o no cumple con los caracteres solicitados. Se notifica y se vuelve al paso 4.

**Postcondición:**

- Se crea una nueva cuenta de usuario en el sistema.

___

#### Nombre del caso:

- Iniciar Sesión

**Descripción**

- Este Caso de Uso especifica el evento en el que un Usuario registrado inicia la sesíon con su nombre y contraseña.

**Actores**

- Usuario Registrado

**Precondiciones**

- 

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: el Usuario Registrado selecciona la opción de "Iniciar Sesión"
	
	- Paso 3: el Usuario Registrado ingresa los datos de inicio de sesión

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita usuario y contraseña
	
	- Paso 4: el sistema verifica los datos ingresados
	
	- Paso 5: el sistema registra el inicio de sesión del Usuario Registrado y activa las funciones del mismo

**Curso Alterno:**

- Paso alternativo 4: Los datos ingresados no corresponden a una cuenta del sistema. Se notifica discrepancia y retorna al paso 2.

**Postcondición:**

- Se inicia la sesión y se habilitan las opciones para los usuarios registrados.

___


#### Nombre del caso:

- Cerrar Sesión.

**Descripción**

- Este Caso de Uso especifica el evento en el que un Usuario registrado cierra la sesíon.

**Actores**

- Usuario Registrado

**Precondiciones**

- El usuario debe tener la sesión iniciada.

**Curso Normal:**

- **Acción del Actor:**

	- Paso 1: El Usuario Registrado selecciona la opción de "Cerrar Sesión"
	
	- Paso 3: el Usuario Registrado confirma el cierre de la sesión

- **Acciones del Sistema:**

	- Paso 2: el sistema solicita la confirmación del cierre de sesión
	
	- Paso 4: el sistema finaliza la sesión del Usuario Registrado y deshabilita las funciones del mismo.

**Curso Alterno:**

- Paso alternativo 3: El Usuario Registrado cancela la operación y se termina el CU.

**Postcondición:**

- La sesión es cerrada y se deshabilitan las opciones para el usuario registrado eliminando los datos de la sesión.

