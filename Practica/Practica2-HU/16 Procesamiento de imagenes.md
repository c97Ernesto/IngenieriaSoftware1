### Problema 16: Procesamiento de Imágenes.

**ROL DE USUARIOS:**

- Operario

- Operario autenticado

- Supervisor

**HISTORIAS DE USUARIOS:**

- Autenticar Operario.
- Cargar Imagen.
- Recortar áreas de interes.
- Listar imágenes.


___


#### Frente
- ID: **Autenticar Operario.**

- TITULO: Como Operario quiero autenticarme para poder usar el sistema.


**Dorso**

- Criterios de aceptación (Autenticar Operario):

- _Escenario 1: Autenticación exitosa._
	- DADO que el usuario "Operario1" y la contraseña "123" pertencen a un operario registrado y hay conexión con el Sistema General del Observatorio
	- CUANDO el Operario ingresa: "Operario1", "123" y selecciona "Iniciar Sesión"
	- ENTONCES el sistema retorna un token indicando la autenticación correcta.
	
- _Escenario 2: Autenticación fallida por datos incorrectos._ 
	- DADO que el usuario "Op7" y la contraseña "Op7" no pertencen a un operario registrado,
	- CUANDO el Operario ingresa: "Op7", "Op7" y selecciona "Iniciar Sesión".
	- ENTONCES el sistema informa que los datos ingresados son incorrectos
	
- _Escenario 3: Autenticación fallida por no haber conexión con el Sistema General del Observatorio._ 
	- DADO que el usuario "admin" y la contraseña "admin" pertenecen a un operario registrado,
	- CUANDO el Operario ingresa: "admin", "admin" y selecciona "Iniciar Sesión",
	- ENTONCES el sistema informa que no hay conexión con el Sistema General del Observatorio.

___

#### Frente
- ID: **Recortar Imagen.**

- TITULO: Como operario quiero recortar una imagen

- REGLAS DE NEGOCIO: 
	- No se pueden recortar más de 4 áreas.
	- Las áreas recortadas no se pueden superponer
	
**Dorso**

- Criterios de aceptación (Recortar imagen):

- _Escenario 1: Recorte de imagen Exitoso._
	- DADO que se encuentra una imagen cargada, el operario marcó 4 áreas y no hay áreas que se superpongan,
	- CUANDO el Operario Autenticado marca las áreas a recortar y selecciona "Recortar Áreas".
	- ENTONCES el sistema almacena en disco las áreas recortadas.
	
- _Escenario 2: Recorte fallido por áreas superpuestas._ 
	- DADO que se encuentra una imagen cargada, el operario marcó 3 áreas, pero hay áreas recortadas que se encuentras superpuestas,
	- CUANDO el Operario Registrado marca las áreas recortadas y selecciona "Recortar Áreas"
	- ENTONCES el sistema informa que hay un error en las áreas recortadas.
	
- _Escenario 3: Recorte fallido por seleccionar más de 4 áreas para recortar._ 
	- DADO 
	- CUANDO
	- ENTONCES

- _Escenario 4: Recorte fallido por no haber imágen cargada para recortar._ 
	- DADO 
	- CUANDO
	- ENTONCES
___

#### Frente
- ID: **Cargar Imagen.**

- TITULO: Como Operario autenticado quiero cargar una imagen.

- REGLAS DE NEGOCIO:
	- Solo se muestran imágenes de más de 2 Megapixeles.

**Dorso**

- Criterios de aceptación (Cargar Imagen):

- _Escenario 1: Carga Exitosa, visualización en escala de grises._
	- DADO que hay imágenes de más 2 Megpíxeles de resolución, y se elige una imagen de 2.9 Megapixeles.
	- CUANDO el Operario autenticado ingresa la imagen de 2.9Megapíxeles y elige la opción de "Escala de grises" y selecciona "Cargar Imagen".
	- ENTONCES el sistema carga la imagen y la visualiza en escala de grises.
	
- _Escenario 2: Carga Exitosa, visualización a color._ 
	- DADO que hay imágenes de más de 2 Megapixeles de resolución, y se elige una imagen de 2.9 Megapixeles
	- CUANDO el Operario autenticado ingresa la imagen de 2.9 Megapixeles y elige la opción de "Color" y selecciona "Cargar Imagen".
	- ENTONCES el sistema carga la imagen y la visualiza a color.
	
- _Escenario 3: Carga Fallida por no haber imágenes._ 
	- DADO que no hay imagenes de más de 2 Megapixeles de resolución
	- CUANDO el Operario quiere ingresar una imagen,
	- ENTONCES el sistema informa que no hay imágenes de más de 2Megapixeles.
	
___

#### Frente
- ID: **Listar imágenes.**

- TITULO: Como Supervisor quiero listar imágenes para visualizarlas.

- REGLAS DE NEGOCIO:
	- No se pueden mostrar más de 20 imágenes a la vez.

**Dorso**

- Criterios de aceptación ():

- _Escenario 1: Listado Exitoso._
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Listado fallido por no haber imágenes procesadas._ 
	- DADO 
	- CUANDO
	- ENTONCES
	
- _Escenario 2: Listado fallido, solo se pueden mostrar 20 imágenes a la vez._ 
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

