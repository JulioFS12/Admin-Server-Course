# Admin-Server-Course

### INSTALAR LINUX CENTOS

* Descargar Virtual Box: https://www.virtualbox.org/
* Descargar CentOS: http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-DVD-1908.iso
* Crear una nueva máquina virtual
* En la configuración de nuestra máquina, en la sección Red cambiar de NAT a Adaptador puente. En avanzadas, colocar en el Modo promiscuo “Permitir todo”
* En la sección Storage seleccionamos el cd que dice “Vacío”, y en el apartado de atributos a la derecha seleccionamos el icono del cd para buscar nuestra imagen ISO de CentOS ya * descargada anteriormente. Aceptamos los cambios
* Iniciamos la máquina virtual
* Instalamos el sistema operativo
* En la configuración, en el apartado de NETWORK & HOST NAME, activar la interfaz con el botón “on”. Cambiamos el host name a “platzi-server” y damos click en aplicar
* En el apartado de INSTALLATION DESTINATION seleccionamos el disco de Virtual Box
* Configuramos la hora y damos click en done
* Hacemos click en ROOT PASSWORD y creamos una contraseña para el usuario root
* Creamos un usuario nuevo dando click en USER CREATION y finalizamos la instalación

### INSTALAR LINUX UBUNTU

* Descargar Virtual Box: https://www.virtualbox.org/
* Descargar Ubuntu Server: https://ubuntu.com/download/server
* Crear una nueva máquina virtual
* En la configuración de nuestra máquina, en la sección Red cambiar de NAT a Adaptador puente. En avanzadas, colocar en el Modo promiscuo “Permitir todo”
* En la sección Storage seleccionamos el cd que dice “Vacío”, y en el apartado de atributos a la derecha seleccionamos el icono del cd para buscar nuestra imagen ISO de Ubuntu ya descargada anteriormente. Aceptamos los cambios.
* Iniciamos la máquina virtual
* Si estamos trabajando en un servidor físico, deberíamos seleccionar “Comprobar memoria”
* Instalamos el sistema operativo

### GNX/LINUX

Linux es un sistema operativo: un conjunto de programas que le permiten interactuar con su ordenador y ejecutar otros programas.

Un sistema operativo consiste en varios programas fundamentales que necesita el ordenador para poder comunicar y recibir instrucciones de los usuarios; tales como leer y escribir datos en el disco duro, cintas, e impresoras; controlar el uso de la memoria; y ejecutar otros programas. La parte más importante de un sistema operativo es el núcleo. En un sistema GNU/Linux, Linux es el núcleo. El resto del sistema consiste en otros programas, muchos de los cuales fueron escritos por o para el proyecto GNU. Dado que el núcleo de Linux en sí mismo no forma un sistema operativo funcional, preferimos utilizar el término “GNU/Linux” para referirnos a los sistemas que la mayor parte de las personas llaman de manera informal “Linux”.

### Gestión del árbol de directorios

La estructura de los directorios de Linux, así como su contenido y funciones, viene definida en el denominado Filesystem Hierarchy Standard o FHS por sus siglas en inglés, que en otras palabras viene a ser el estándar de jerarquía para los sistemas de archivos en sistemas Linux y otros derivados de UNIX.

Todo el árbol de parte de una raíz común denominada root y que se simboliza por una barra inclinada. Aún así, esto no significa que varios de ellos no puedan estar en particiones separadas del resto. De hecho, en muchas distros GNU/Linux es una práctica muy común el hecho ubicar ciertos directorios en particiones separadas del resto.

![Gestión del árbol de directorios](https://computernewagedotcom.files.wordpress.com/2018/08/linux-jerarquia-directorios.png)

