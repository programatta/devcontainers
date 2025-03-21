# GO Ebiten Development Container.
Contenedor para el desarrollo de Go con las dependencias para usar [Ebiten](https://ebitengine.org/).

Contiene:
* build-essential
* gdb
* make
* wget
* unzip
* libc6-dev
* libgl1-mesa-dev
* libxcursor-dev
* libxi-dev
* libxinerama-dev
* libxrandr-dev
* libxxf86vm-dev
* libasound2-dev
* pkg-config

Hace uso de la variable __$DISPLAY__ del sistema anfitrion para ser mapeada al docker.

Comparte los sockets de X11: __/tmp/.X11-unix__.

## Permisos de uso de X11 al usuario del contenedor.
Permitir el uso de X11 al usuario del contenedor mediante la orden __xhost__:

Para saber que hay, tecleamos xhost en la terminal:
~~~bash
xhost
~~~

Si no hay nada, nos mostrará:
>_access control enabled, only authorized clients can connect_.

Para añadir los permisos a usar X11:
~~~bash
xhost +SI:localuser:USUARIO
~~~

Y nos mostrará lo siguiente:
>_localuser:USUARIO being added to access control list_

Para visualizarlo:
~~~bash
xhost
~~~

Y nos mostrará:
>_access control enabled, only authorized clients can connect
SI:localuser:USUARIO_

Para retirar los permisos hacemos:
~~~bash
xhost -SI:localuser:USUARIO
~~~

Y nos mostrará los siguiente:
>_localuser:USUARIO being removed from access control list_

Y para verificar que todo está como inicalmente lo teníamos:
~~~bash
xhost
~~~
y nos mostrará:
>_access control enabled, only authorized clients can connect_
