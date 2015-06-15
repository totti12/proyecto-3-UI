<!-- Portada -->
<div align="center">
	<h4> Curso </h4>
	<h5> Diseño Interfaces Usuario</h5>
	<hr></hr>
	<h4> Trabajo Investigación </h4>
	<h5> Aplicación para organizar/enviar correo personal</h5>
	<hr></hr>
	<h4> Profesor</h4>
	<h5> Armando Arce</h5>
	<hr></hr>
	<h4> Alumno</h4>
	<h5> Geovanny Quirós Pérez, ced. 604130302</h5>
	<hr></hr>
<div align="center"></div>
</div>
<!-- Logo Universidad -->	
<div align="center">
 <img src="../imagenes/una.png" title="Universidad Nacional">
 <div align="center"></div>
</div>
<!-- Introducción -->
<div align="center">
	<h2> Introducción </h2>
	<div align="center"></div>
</div>
_En este documento se detallará más a fondo la aplicación desarrollada para la parte 1 de este proyecto que consistía en la creación de distintas interfaces para nuestra aplicación, en este caso en específico se hará el debido modelado, tanto como el modelo de datos, como el modelo de  **diagramas IFML** que involucran la aplicación, **modelo de Datos**; con ello se tiene como objetivo que nuestra interfaz(Mockup como llamaré de ahora en adelante) no se realice sin antes tener sus modelos que las respaldan; es por ello que se hará el análisis completo de mi aplicación llamada **MailTool**, ésta aplicación provee el servicio de gestión de correos personales, en la siguiente sección(Aplicación) se estudiará la misma tal y como he dicho anteriormente_
<!-- Desarrollo -->
<div align="center">
	<h2> Desarrollo </h2>
	<h3> Aplicación </h3>
<div align="center"></div>
</div>
<!-- Desarrollo / Modelo de Datos  -->
#### La aplicación tendrá un único modelo de datos, dicho modelo no depende más que del análisis del problema/investigación inicial.
<div align="center">
 <img src="../imagenes/modeloDatos.png" title="Modelo Datos MailTool">
 <div align="center"></div>
</div>

Para el problema/investigación inicial se crearon las siguiente entidades:

1. Grupo (Clase/entidad genérica).
2. Grupo Contactos (**Hereda** de la entidad Grupo). Cardinalidad: 1..* 
3. Grupo Mensajes (**Hereda** de la entidad Grupo). Cardinalidad: 1..* 
4. Mensaje Entrada (**Hereda** de la entidad Grupo Mensajes). Base para el módulo Mensajes/Entrada.
5. Mensaje Salida (**Hereda** de la entidad Grupo Mensajes). Base para módulo Mensajes/Salida.
6. Mensaje Correo. (**Hereda** de la entidad Mensaje) El mensaje del correo en sí este se compone además de:

	6.1 Fecha  : Fecha de envío del correo, este parámetro no podrá ser digitado por el usuario, se toma del sistema. 

	6.2 Hora   : Hora envío del correo, al igual que el anterior se toma del sistema.

	6.3 Adjunto: Posibilidad de adjuntar un archivo, esta entidad dará esta posibilidad.

7. Mensaje (Clase/entidad genérica).
8. Contacto. Entidad que da posibilidad de gestionar contactos, gracias a sus atributos.


<!-- Desarrollo / Módulos  -->
#### La aplicación llamada **Mail Tool** tendrá 3 módulos:

1. **Principal:**
> En este módulo encontraremos 2 mockups, el primero llamado _**Login**_ y el segundo llamado _**Principal**_ .
2. **Mensajes:**
> En este módulo encontraremos 3 submódulos llamados: _**Detalles Mensaje**_,_**Eliminar Mensaje**_,_**Nuevo Mensaje**_ dentro de estos submódulos encontraremos sus respectivos mockups, que están asociados a la funcionalidad dentro de la aplicación; además tendremos un mockup llamado _**Búsqueda Mensaje**_. 
3. **Contactos:**
> En este módulo encontraremos 3 submódulos llamados _**Nuevo**_,_**Eliminar**_,_**Ver**_, dentro de estos submódulos se encuentran los respectivos mockups asociados como mencioné anteriormente a la funcionalidad que conllevan.

<!-- Módulos/Principal -->
<hr></hr>
<div align="center">
	<h4> 1. Módulo Principal </h4>
<div align="center"></div>
</div>
##### IFML Login
<!-- IFML Login -->	
<div align="center">
 <img src="../imagenes/principal/login_ifml.png" title="IFML Login">
 <div align="center"></div>
</div>
En este **Diagrama IFML** podemos observar cómo se comportará nuestra aplicación en el inicio de la misma, este **diagrama** proveerá la funcionalidad del inicio de sesión para nuestra aplicación por medio de las funcionalidades  _registrarse_ e _Iniciar Sesión_ . Este **diagrama respaldará nuestro primer Mockup**.
##### Mockups Login
<div align="center">
 <img src="../imagenes/principal/login_mockup.png" title="Mockup Login">
 <div align="center"></div>
</div>
Este **Mockup** provee la primer visualización de nuestra [aplicación](http://www.mail.mailtoo.com), la misma permitirá el ingreso al sistema. Cuenta con _etiquetas_ ,la primera llamada _Nombre de Usuario_ con su respectivo campo, servirá para digitar nuestro nombre de usuario de correo, enseguida se muestra la segunda etiqueta llamada _Contraseña_ con su respectivo campo, dicho campo es para digitar nuestra contraseña de correo electrónico. En dado caso que no se tenga una cuenta, la opción superior derecha identificada con un _botón_ cuya etiqueta _Crear cuenta_ nos proveerá la opción de creación de una cuenta de correo [MailTool](http://www.mail.mailtoo.com). Seguidamente que digitemos nuestro credenciales aparecerá nuestro segundo **Diagrama IFML** llamado _Principal_.
##### IFML Principal
<div align="center">
 <img src="../imagenes/principal/principal_ifml.png" title="IFML Principal">
 <div align="center"></div>
</div>
En este **Diagrama IFML** se pueden ver claramente los módulos: 

* Mensajes (_**por defecto se mostrarán los mensajes de entrada**_)
* Contactos

Además se ven los submódulos asociados a cada uno de ellos:

* Mensajes
>* Submódulos
>>* _**Detalles**_,_**Eliminar Mensaje**_,_**Nuevo Mensaje**_.

* Contactos
>* Submódulos
>>* _**Nuevo**_,_**Eliminar**_,_**Ver**_

También podemos ver otros **"Módulos"** como es el caso de _**Notificaciones**_ que empleará la funcionalidad de estar constantemente notificando al usuario lo que suceda en la aplicación. Además _**Configuraciones**_ que brindará la opción de configurar aspectos propios de la cuenta del correo del usuario(Opción no implementada se toma como de prioridad baja para mi caso).

Este **Diagrama IFML** nos permitirá crear el **Mockup** asociado al mismo. El detalle de cada uno de estos submódulos se detallarán **individualmente** (tal y como se pedía) más adelante. 

##### Mockups Principal
<div align="center">
 <img src="../imagenes/principal/principal_mockup.png" title="Mockup Principal">
 <div align="center"></div>
</div>
En nuestro **Mockup** _Principal_ se lleva a cabo la implementación de nuestro anterior **Diagrama IFML** , y como puede observarse en primera instancia los _Mensajes/Entrada_ aparecen por defecto seleccionados, a la derecha se muestran los mismos, acá mismo se asocian las implementaciones de los submódulos **Detalles**_,_**Eliminar Mensaje**_,_**Nuevo Mensaje**_ propios del módulo **Mensajes** , pero más adelante detallaré. Posteriormente abajo de _Mensajes/Entrada_ se puede observar la implementación a nuestro módulo **Contactos** y se asocian los los submódulos del mismo _**Nuevo**_,_**Eliminar**_,_**Ver**_.

<!-- Módulos/Mensajes -->
<hr></hr>
<div align="center">
	<h4> 2. Módulo Mensajes </h4>
<div align="center"></div>
</div>
##### IFML Mensajes
<div align="center">
 <img src="../imagenes/mensajes/mensajes_ifml.png" title="IFML Mensajes">
 <div align="center"></div>
</div>
En este **Diagrama IFML** se muestra el funcionamiento o composición de este módulo. Tendremos una lista **"MultiChoise"** de elementos que por defecto serán los mensajes de entrada y sus elementos visibles **VisibleAttributes** serán:

* Correo
* Asunto
* Fecha 
* Hora

Acontinuación el **Mockup** asociado a esta funcionalidad:
##### Mockup Mensajes
<div align="center">
 <img src="../imagenes/mensajes/mensajes_mockup.png" title="Mockup Mensajes">
 <div align="center"></div>
</div>

Se puede observar en el módulo **Mensajes** la selección por defecto de Entrada, al lado derecho se muestra la implementación del **Diagrama IFML** por medio de una tabla y en efecto los atributos _correo_, _asunto_,_Fecha_,_Hora_ son visibles al usuario. Además en la parte superior se muestra la notificación **_Mostrando Mensajes Entrada_** . En la parte inferior se muestra una paginación asocido a la navegación entre los mensajes en este caso **_se muestran 5 de 29 mensajes_** entrada, además se identifica con **{*}**, dicha funcionalidad está desabilitada ya que no hay mensajes anteriores a esta pantalla.

<!-- Módulos/Mensajes/Submódulo/Detalles -->
<hr></hr>
<div align="center">
	<h4> 2.1 Submódulo Detalles </h4>
<div align="center"></div>
</div>
##### IFML Detalles Mensaje
<div align="center">
 <img src="../imagenes/mensajes/detallesMensaje_ifml.png" title="IFML Detalles Mensaje">
 <div align="center"></div>
</div>

En este caso el **Diagrama IFML** mostrará la funcionalidad de ver detalles de un mensaje, para este caso se observa que al igual que en el anterior **Diagrama  IFML(Mensajes)** tendremos una lista **"MultiChoise"** de elementos que por defecto serán los mensajes de entrada y además que será necesario _seleccionar un mensaje_ y dar _doble click_ a uno de los mensajes que se muestran para poder ver el detalle de un mensaje. A continuación se mostrará los **Mockup** asociados.

##### Mockups Mensaje/Seleccion
<div align="center">
 <img src="../imagenes/mensajes/seleccionMensaje_mockup.png" title="Mockup Detalles Mensaje">
 <div align="center"></div>
</div>

Como se puede observar se ha seleccionado el mensaje perteneciente al correo **marce_h@una.cr** para poder ver el detalle se deberá hacer doble click, lo que dará como resultado el siguiente **Mockup**

##### Mockups Mensaje/Detalles
<div align="center">
 <img src="../imagenes/mensajes/detallesMensaje_mockup.png" title="Mockup Detalles Mensaje">
 <div align="center"></div>
</div>

Se muestra el detalle del mensaje al que se le ha dado doble click. Se muestran visibles los atributos Correo, asunto, hora, fecha y el cuerpo del mensaje.

<!-- Módulos/Mensajes/Submódulo/Nuevo -->
<hr></hr>
<div align="center">
	<h4> 2.2 Submódulo Nuevo </h4>
<div align="center"></div>
</div>
##### IFML Nuevo Mensaje
<div align="center">
 <img src="../imagenes/mensajes/nuevo_ifml.png" title="IFML Nuevo Mensaje">
 <div align="center"></div>
</div>

En este **Diagrama IFML** se llevará a cabo la funcionalidad de creación o redacción de un nuevo mensaje, muestra un formulario con los campos de entrada correo, asunto, adjuntar y mensajes, mismos que se detallaron en el **Modelo de Datos** anteriormente mencionado. En este caso como se llevará a cabo una funcionalidad a nivel de lógica del sistema será necesario una operación en un posible base de datos, dicha funcionalidad u operación se representa por medio de la etiqueta **_insert_**, esto significará que se insertará un nuevo mensaje en el buzón de salida o _Mensajes/Salida_ por lo que la actualización de este **Mockup** asociado deberá suceder, posteriormente se debe **notificar al usuario** el resultado de esa operación(para nuestro caso la operación sucedió con éxito). A continuación se mostrarán los **Mockups** asociados a esta operación dentro de nuestro sistema.

##### Mockups Mensaje/Nuevo
<div align="center">
 <img src="../imagenes/mensajes/nuevo_mockup.png" title="Mockup Nuevo Mensaje">
 <div align="center"></div>
</div>

En este caso se selecciona la opción superior izquiera llamada _Nuevo Mensaje_ que aparece en este **Mockup** . Además para este caso también se ha seleccionado la opción **Enviar** por lo que en la parte superior aparece la notificación **_Mensaje Enviado Exitosamente_**. En este ejemplo no se implementará la opción **Adjuntar Archivo** ya que así se pedía para este proyecto. Como mencioné en la especificación del **Diagrama IFML** , se deberá actualizar un nuevo **Submódulo** representado mediante la opción _Mensajes/Salida_ con un **Mockup**, por lo que se mostrará a continuación.

##### Mockups Mensaje/Salida
<div align="center">
 <img src="../imagenes/mensajes/mensajeSalida_mockup.png" title="Mockup Nuevo Mensaje/ Salida">
 <div align="center"></div>
</div>
<!-- Módulos/Mensajes/Submódulo/Eliminar -->
<hr></hr>
<div align="center">
	<h4> 2.2 Submódulo Eliminar </h4>
<div align="center"></div>
</div>
##### IFML Eliminar Mensaje
<div align="center">
 <img src="../imagenes/mensajes/eliminarMensaje_ifml.png" title="IFML Eliminar Mensaje">
 <div align="center"></div>
</div>

Para este caso el **Diagrama IFML** la secuencia de acciones es muy similar que en el caso de **Mensaje/Detalles** ha diferencia que se presentará una opción de confirmación para el usuario, y en caso que realmente desee eliminar el/los mensajes seleccionados, se hará una operación a nivel de lógica del sistema que podría ser en una Base de Datos por lo que se representa la misma mediante la etiqueta _eliminar_, además esta acción debe notificar al usuario el resultado de la acción para nuestro caso si se ha podido eliminar el correo seleccionado, y consecuentemente se independientemente de que el usuario cancele o no la eliminación de los mensajes se deberá reenviar de nuevo al **Mockup** _Mensajes/Entrada_. A continuación se verá la funcionalidad de dichas acciones.

##### Mockups Mensaje/Seleción a Eliminar
<div align="center">
 <img src="../imagenes/mensajes/eliminarSeleccionados_mockup.png" title="Mockup Seleccion a Eliminar">
 <div align="center"></div>
</div>

Se muestra en la parte superior la **notificación** que dice el número de mensajes que se irán a eliminar, además la opción **Eliminar Seleccionados** se encuentra activa por lo que se activa el siguiente **Mockup**.

##### Mockups Mensaje/Confirmación Eliminar
<div align="center">
 <img src="../imagenes/mensajes/confirmacionEliminacion_mockup.png" title="Mockup Confirmación">
 <div align="center"></div>
</div>

Se muestra un cuadro de diálogo para confirmar la eliminación de los mensajes. Para nuestro caso seleccionamos la opción **_OK_**, por lo que se deberá actualizar nuestro **Mockup** _Mensajes_. A continuación se muestra dicha acción reflejada mediante un mockup.

##### Mockups Mensaje/Nueva Lista Mensajes
<div align="center">
 <img src="../imagenes/mensajes/nuevosListaMensajesEliminados_mockup.png" title="Mockup Nueva Lista Mensajes">
 <div align="center"></div>
</div>

Se muestra en la parte superior la notificación **2 Mensajes Eliminados Correctamente** por lo que nuestra implementación haciendo referencia al **Diagrama IFML** _Eliminar Mensaje_.

##### IFML Buscar Mensaje
<div align="center">
 <img src="../imagenes/mensajes/busqueda_mensaje_ifml.png" title="IFML Buscar Mensaje">
 <div align="center"></div>
</div>

Este **Diagrama de IFML** tendrá la funcionalidad de buscar entre los mensajes ya sean entrada o salida un mensaje, tomando como clave el correo que se digite. A continuación se mostrarán los **Mockups** que implementan este **Diagrama de IFML**.

##### Mockups Busqueda Mensaje

<div align="center">
 <img src="../imagenes/mensajes/busquedaMensaje_mockup.png" title="Mockup Nueva Lista Mensajes">
 <div align="center"></div>
</div>

Se muestra el resultado de la búsqueda, además de la notificación **_Mensaje Encontrado_**.
<!-- Módulos/Contactos -->
<hr></hr>
<div align="center">
	<h4> 3. Módulo Contactos </h4>
<div align="center"></div>
</div>
<!-- Módulos/Contactos/Submódulo/Ver -->
<hr></hr>
<div align="center">
	<h4> 3.1 Submódulo Ver </h4>
<div align="center"></div>
</div>
##### IFML Ver Contactos
<div align="center">
 <img src="../imagenes/contactos/verContactos_ifml.png" title="IFML Ver Contactos">
 <div align="center"></div>
</div>

En esta ocasión se mostrarán los contactos que tenga el usuario, además si se selecciona alguno y se hace doble click esta acción se considera como un nuevo **Mockup**, pero en detalle los veremos a continuación.

##### Mockup Ver Contactos
<div align="center">
 <img src="../imagenes/contactos/verContactos_mockup.png" title="Mockup Ver Contactos">
 <div align="center"></div>
</div>

Como se puede apreciar ahora la opción seleccionada dentro de nuestro módulo _Mensaje_ en específico el submódulo _Ver_. En la parte superior se muestra la notificación asociada. En este caso si deseamos ver detalles de este contacto haremos lo que muestra el siguiente **Mockup**.

##### Mockup Seleccionar Contacto
<div align="center">
 <img src="../imagenes/contactos/seleccionContacto_mockup.png" title="Mockup Ver Contactos">
 <div align="center"></div>
</div>

Se ha seleccionado el _Contacto_ **Grace Rojas**, en la parte superior se muestra una notificación que relaciona dicha acción. Ahora si deseamos ver el detalle del contacto deberemos dar doble click, acontinuación se muestra dicho **Mockup**.

##### Mockup Detalles Contacto
<div align="center">
 <img src="../imagenes/contactos/detallesContacto_mockup.png" title="Mockup Ver Contactos">
 <div align="center"></div>
</div>

En la parte superior se muestra la notificación respectiva.

<!-- Módulos/Contactos/Submódulo/Nuevo -->
<hr></hr>
<div align="center">
	<h4> 3.2 Submódulo Nuevo </h4>
<div align="center"></div>
</div>

##### IFML Nuevo Contacto
<div align="center">
 <img src="../imagenes/contactos/AgregarContactos_ifml.png" title="IFML Nuevo Contacto">
 <div align="center"></div>
</div>

En este caso estando dentro del módulo **Contactos** si damos la opción nuevo nos llevará a un formulario donde deberemos digitar los campos que representan los atributos de la entidad _Contacto_ de nuestro **Modelo de Datos**. Además esta acción involucra nuestra lógica de negocio por lo que podría ser una Base de Datos como he mencionado en repetidas ocaciones a lo largo de este trabajo, dicha acción se representa por medio de una etiqueta _insert_. Si la creación del nuevo contacto se hace de la manera correcta nos mostrará al nuevo contacto creado. A continuación se muestran lo **Mockups** asociados a este **Diagrama IFML**.

##### Mockup Nuevo Contacto
<div align="center">
 <img src="../imagenes/contactos/nuevoContacto_mockup.png" title="Mockup Nuevo Contacto">
 <div align="center"></div>
</div>

Se ha dado la opción **Agregar** por lo que en la parte superior nos muestra la notificación. Esto hace que nuestro nuevo contacto exista en la lista de contactos por lo que el siguiente **Mockup** muestra dicha acción.

##### Mockup Lista con Nuevo Contacto
<div align="center">
 <img src="../imagenes/contactos/verContactos_mockup.png" title="Mockup Nueva Lista Contactos">
 <div align="center"></div>
</div>

Se observa que en efecto se ha agregado el nuevo contacto.

<!-- Módulos/Contactos/Submódulo/Eliminar -->
<hr></hr>
<div align="center">
	<h4> 3.3 Submódulo Eliminar </h4>
<div align="center"></div>
</div>

##### IFML Eliminar Contacto
<div align="center">
 <img src="../imagenes/contactos/EliminarContactos_ifml.png" title="Mockup Nueva Lista Contactos">
 <div align="center"></div>
</div>

Acá se podrá llevar a cabo la eliminación de un(os) contacto(s), dicho(s) contacto(s) se encuentran en una lista **MultiChoise** donde presentará la opción al usuario de seleccionar 1 o más de 1 contacto a eliminar, dicha acción lleva a una nueva ventana de confirmación y de darse como **OK** se procederá a simular el proceso de eliminación a nivel de base de datos, por lo que se deberá actualizar nuestra **Mockup*** de _Ver Contactos_. A continuación se proveerán los **Mockups** asociados a este **Diagrama de IFML**.

##### Mockup Selección Contacto
<div align="center">
 <img src="../imagenes/contactos/eliminarContacto_mockup.png" title="Mockup Contacto Eliminar">
 <div align="center"></div>
</div>

En este caso se ha seleccionado el Contacto **Marcela Hernandez** y se ha procedido con la opción **_Eliminar Seleccionados_** por lo que se debe mostrar un cuadro de diálogo que indique si realmente desea eliminar el contacto. En la parte superior se muestra la notificación asociada.

##### Mockup Confirmación Eliminar Contacto
<div align="center">
 <img src="../imagenes/contactos/confirmarEliminar.png" title="Mockup Confirmación">
 <div align="center"></div>
</div>

En este caso se dará la opción **Ok** por lo que obtendremos una nueva lista o una actualización de nuestra lista de contactos original tal y como muestra el siguiente **Mockup**.

##### Mockup Nueva Lista Contactos
<div align="center">
 <img src="../imagenes/contactos/nuevoContactoEliminar_mockup.png" title="Mockup Confirmación">
 <div align="center"></div>
</div>

En efecto no aparecerá el contacto que se ha eliminado anteriormente.


<!-- Conclusión -->
<div align="center">
	<h2> Conclusión </h2>
	<div align="center"></div>
</div>
> Realmente el realizar todo el proceso de análisis de esta aplicación, conociendo un poco a fondo sus modelos y diagramas, me dió una visión distinta, es decir la idea de como construir una interfaz apartir de todos sus diagramas en conjunto; si bien es cierto que no fue un análisis tan detallado como me hubiese gustado hacer, si puedo decir que el aprendizaje adquirido fue considerable.


