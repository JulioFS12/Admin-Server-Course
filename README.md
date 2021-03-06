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

#### Directorio Raíz o /
Toda la estructura de directorios en los sistemas basados en UNIX parte de un directorio raíz también llamado directorio root y que se simboliza por una barra inclinada o /. De este directorio, es desde donde nacen todo el resto de directorios, independientemente que estén almacenados físicamente en discos o unidades separadas.

Cualquier dirección de archivo o carpeta en Linux empieza por el directorio raíz o /, seguido de todos los directorios y subdirectorios que que lo contienen, separados cada uno de ellos por /.

A continuación conocerás con más en detalle a todos los directorios principales que parten del directorio raíz, junto con sus subdirectorios más importantes y los ficheros que suelen contener.

#### Bin, Sbin
El directorio /bin es un directorio estático y es donde se almacenan todos los binarios necesarios para garantizar las funciones básicas a nivel de usuario. Solo almacena los ejecutables de usuario, ya que los binarios necesarios para tareas administrativas gestionadas por el usuario root o superusuario del sistema se encuentran en el directorio /sbin.

Incluye también los binarios que permiten la ejecución de varias utilidades estándar de la terminal de Linux, concretamente cat, cd, cp, echo, grep, gzip, kill, ls, mv, rm, ping, su, ps, tar y vi.

El directorio /sbin hace lo mismo pero para los binarios relativos tareas propias del sistema operativo, y que solamente pueden ser gestionadas por el usuario root, tales como el arranque, tareas de restauración, reparación, etc.

#### Boot
Es un directorio estático e incluye todos los ejecutables y archivos que son necesarios en el proceso de arranque del sistema, y que deberán ser utilizados antes que que el kernel empiece a dar las órdenes de ejecución de los diferentes módulos del sistema. Es también donde se encuentra el gestor de arranque GRUB.

En algunas distribuciones, es común que ese directorio se almacene en su propia partición separada del resto. Esto suele darse sobretodo en el caso de de que utilicen LVM por defecto, ya que tradicionalmente el gestor de arranque GRUB (en versiones anteriores a la 2) no podía arrancar desde LVM, por lo que se requería que estuviera en una partición separada.

De hecho, si en una instalación normal de Ubuntu o Debian optas por utilizar LVM, verás que el instalador ya te genera un esquema de particiones con el directorio boot en una partición aparte.

En estos casos, en el momento de instalar el sistema es importante prever bien el espacio que le vayas a dar a la partición, ya que a la larga, con la acumulación de diferentes actualizaciones del Kernel, es común que se quede sin espacio. Si esto sucede, puedes tener problemas a la hora de instalar futuras actualizaciones del núcleo, y debas hacer limpieza de versiones antiguas del kernel.

#### Dev
Este directorio incluye todos los dispositivos de almacenamiento, en forma de archivos, conectados al sistema, es decir, cualquier disco duro conectado, partición, memoria USB, o CDROM conectado al sistema y que el sistema pueda entender como un volumen lógico de almacenamiento.

Siendo esto así, verás que la ruta en la que se encuentra cualquier volumen (partición o dispositivo externo) conectado al sistema siempre empieza por /dev.

Este es el directorio que contiene, por decirlo de algún modo, la información de cada uno de los volúmenes, a diferencia del directorio /media, que verás más adelante, que lo que contiene son solo los puntos de montaje, pero no la información real de estos volúmenes.

Para ver esto en la práctica, si abres una ventana de terminal y ejecutas el comando sudo fdisk -l, verás la estructura de particiones de tu sistema. En una instalación típica de cualquier distro GNU/Linux suele ser la siguiente:

/dev/sda1 - Partición principal
/dev/sda2 - Partición extendida 
/dev/sda5 - Partición Swap
La partición sda1 suele ser la partición principal, Obviamente si has editado manualmente el esquema de particiones, en tu caso será diferente, esto es solo un ejemplo típico para ayudar a explicar la función del directorio /dev.

Eso en cuanto a particiones. Si se trata de un dispositivo externo, el volumen estará igualmente dentro de /dev, pero en este caso varía el nombre que el sistema le asigna a dicho volumen. Generalmente la estructura suele ser la siguiente (si ejecutas nuevamente el comando sudo fdisk -l con un dispositivo externo conectado lo podrás comprobar tu mismo).

/dev/sdb1
/dev/sdb2
/dev/sdb3
...
Etc
Es el encargado de almacenar los archivos de configuración tanto a nivel de componentes del sistema operativo en sí, como de los programas y aplicaciones instaladas a posteriori.

Es un directorio que debería contener únicamente ficheros de configuración, y no debería contener binarios.

#### Home
Es el directorio de los usuarios estándar, y por lo tanto, el destinado a almacenar todos los archivos del usuario, como documentos, fotos, vídeos, música, plantillas, etc. También incluye archivos temporales de aplicaciones ejecutadas en modo usuario, que sirven para guardar las configuraciones de programas, etc.

Dentro /home hay los directorios personales de todos los usuarios, nombrados según el nombre de usuario utilizado. Así por ejemplo, si en un sistema pongamos que hay dos usuarios denominados User1 y User2, la estructura será así:

/home/User1
/home/User2
Cada directorio de usuario contiene asimismo diferentes carpetas para ayudarlo a clasificar la información. Estas generalmente son: /Documentos, /Imágenes, /Música, /Plantillas y /Vídeos /, así como otros archivos y carpetas ocultas, que son las encargados de guardar la información de configuraciones de las aplicaciones del usuario.

Para visualizar los ficheros ocultos dentro del directorio individual de cada usuario, puedes hacerlo rápidamente mediante la combinación de comandos CTRL + F. Por cierto, y muy importante, todas los archivos y carpetas ocultas en Linux empiezan por un punto, seguido del nombre de la carpeta.

En muchas distribuciones es una práctica recomendada el hecho de ubicar el directorio /home es una partición separada del resto, por tal de facilitar que, en caso de reinstalar el sistema operativo, puedas mantener intacta la partición de la /home, y de este modo mantener todos los archivos personales.

#### Lib
Incluye las bibliotecas esenciales  que son necesarios para que se puedan ejecutar correctamente todos los binarios que se encuentran en los directorios /bin y /sbin, así como los módulos del propio kernel.

En los sistemas operativos de 64 bits, además de /lib existe otro directorio denominado /lib64, referida a las bibliotecas para aplicaciones de 64 bits.

#### Media
Representa el punto de montaje de todos los volúmenes lógicos que se montan temporalmente, ya sean unidades externas USB, otras particiones de disco, etc.

En la mayoría de distribuciones GNU/Linux, desde hace ya algún tiempo, cada vez que se monta una unidad externa, partición, etc., esta se monta dentro del directorio /media y a su vez dentro de un directorio especifico dependiendo del usuario del sistema que monta el volumen.

De este modo, si en un sistema hay varios usuarios, pongamos User1 y User2, los puntos de montaje de los volúmenes que montan cada uno de ellos se mostraran en directorios separados tal como así:

/media/User1
/media/User2
Antiguamente se solía utilizar el directorio mnt para estas funciones, pero actualmente, la mayoría de distribuciones hacen uso de media.

#### Opt
En cierto modo vendría a ser como una extensión del directorio /usr, pero en este caso van todos aquellos archivos de solo lectura que son parte de programas auto-contenidos y que, por lo tanto, no siguen los estándares de almacenar los diferentes archivos dentro de los diferentes subdirectorios de /usr (que sería lo recomendable)

Haciendo una analogía con Windows, vendría a ser algo como el directorio de “Archivos y Programas”, pero en este caso, como hemos dicho, para determinados programas que ya vienen auto-contenidos.

#### Proc
Este directorio contiene información de los procesos y aplicaciones que se están ejecutando en un momento determinado en el sistema, pero realmente no guarda nada como tal, ya que lo que almacena son archivos virtuales, por lo que el contenido de este directorio es nulo.

Básicamente son listas de eventos del sistema operativo que se generan en el momento de acceder a ellos, y que no existen dentro del directorio como tales.

En este enlace de LinuxTotal tienes información más detallada sobre las particularidades de este directorio y todo el juego que le puedes sacar a la hora de obtener información muy diversa del sistema.

#### Root
Vendría a ser como el directorio /home del usuario root o superusuario del sistema.

A diferencia de los otros usuarios, que se encuentran todos dentro de /home en sus respectivas subcarpetas, el directorio del usuario root está en su propia carpeta colgando directamente de la raíz del sistema.

#### Srv
Sirve para almacenar archivos y directorios relativos a servidores que puedas tener instalados dentro de tu sistema, ya sea un servidor web www, un servidor FTP, CVS, etc.

Así, por ejemplo, en el caso de tener instalado un servidor web, sería buena idea tener el directorio web público dentro de /srv, tal como así:

/srv/www
Sys
Al igual que /proc, contiene archivos virtuales que proveen información del kernel relativa a eventos del sistema operativo.

Es en cierto modo una evolución de /proc, y a diferencia de este último, los archivos se distribuyen de forma jerárquica.

#### Tmp
Como ya da a entender su nombre, sirve para almacenar archivos temporales de todo tipo, ya sea de elementos del sistema, o también de diferentes aplicaciones a nivel de usuario como puedan ser Firefox o Chrome/Chromium.

Es un directorio dispuesto para almacenar contenido de corta durada, de hecho en la gran mayoría de los casos se suele vaciar de forma automática en cada reinicio del sistema. Aun así, no debes borrar su contenido de forma manual, puesto que puede contener archivos necesarios para ciertos programas o procesos que estén ejecutándose.

Las aplicaciones programadas para almacenar archivos en este directorio deben asumir que solo serán recuperables en la sesión actual. En este sentido, hay otro subdirectorio, /var/tmp, dispuesto igualmente para el almacenamiento de archivos temporales, pero cuyo contenido no se borra de forma automática tras el reinicio del sistema.

#### Usr
El directorio /usr viene de “User System Resources” y actualmente sirve para almacenar todos los archivos de solo lectura y relativos a las utilidades de usuario, incluyendo todo el software instalado a través de los gestores de paquetes de cada distribución. Contiene los siguientes subdirectorios:

/usr/bin
/usr/include
/usr/lib
/usr/local
/usr/sbin
/usr/share
/usr/src
Antiguamente /usr también contenía la carpeta particular de usuario, junto con todos sus documentos, vídeos, fotos, etc., pero más adelante se creó el directorio /home para este propósito, dejando /usr reservado para los ficheros relativos a programas.

#### Var
contiene varios archivos con información del sistema, como archivos de logs, emails de los usuarios del sistema, bases de datos, información almacenada en la caché, información relativa a los paquetes de aplicaciones almacenados en /opt, etc. En cierto modo se podría decir que actúa a modo de registro del sistema.

### Linea de Comandos

#### Diferencias entre LESS, CAT, HEAD y TAIL para lectura de archivos

1. cat: nos permite leer archivos en su totalidad.
2. less: nos ayuda a leer el contenido de nuestros archivos por páginas. Nos movemos con las flechas del teclado o la tecla de espacio. Salimos de la lectura del archivo con la 3. letra q. Buscamos palabras específicas escribiendo /palabra.
4. tail: nos muestra las últimas 10 líneas de nuestros archivos.
5. head: nos muestra las primeras 10 líneas de nuestros archivos.

#### [Mas comandos...](https://blog.desdelinux.net/mas-de-400-comandos-para-gnulinux-que-deberias-conocer/)

### Interacción con archivos y permisos

#### Permisos del propietario

El propietario es aquel usuario que genera o crea un archivo/carpeta dentro de su directorio de trabajo (HOME), o en algún otro directorio sobre el que tenga derechos. Cada usuario tiene la potestad de crear, por defecto, los archivos que quiera dentro de su directorio de trabajo. En principio, él y solamente él será el que tenga acceso a la información contenida en los archivos y directorios que hay en su directorio HOME.

#### Permisos del grupo

Lo más normal es que cada usuario pertenezca a un grupo de trabajo. De esta forma, cuando se gestiona un grupo, se gestionan todos los usuarios que pertenecen a éste. Es decir, es más fácil integrar varios usuarios en un grupo al que se le conceden determinados privilegios en el sistema, que asignar los privilegios de forma independiente a cada usuario.

#### Permisos del resto de usuarios

Por último, también los privilegios de los archivos contenidos en cualquier directorio, pueden tenerlos otros usuarios que no pertenezcan al grupo de trabajo en el que está integrado el archivo en cuestión. Es decir, a los usuarios que no pertenecen al grupo de trabajo en el que está el archivo, pero que pertenecen a otros grupos de trabajo, se les denomina resto de usuarios del sistema.

```
Permisos estan compuestos por 10 caracteres
- rw- rw- r-- 

1er caracter corresponde al tipo de archivo
'-' = archivo
'b' =	Archivo de bloques especiales (Archivos especiales de dispositivo)
'c' =	Archivo de caracteres especiales (Dispositivo tty, impresora…)
'd' = directorio
'l' = enlace simbólico
'p' =	Archivo especial de cauce (pipe o tubería)

Asignación de permisos en grupos de 3
'u' = usuarios (corresponde caracter del 2 al 4)
'g' = grupos (corresponde caracter del 5 al 7)
'o' = otros (corresponde caracter del 8 al 10)
'a' = todos

Tipo de permisos
'r' = lectura
'w' = escritura
'x' = ejecución
'-' = sin permiso

'+' añade permisos
'-' quita permisos

Formato octal
'0' = (0+0+0) = Sin permisos = ---
'1' = (0+0+1) = Ejecución = --X
'2' = (0+2+0) = Escritura = -w-
'4' = (4+0+0) = Lectura = r--
'7' = (4+2+1= = Eje, Esc, Lec = rwx

chmod | cambiar permisos (chmod u-r archivo.txt), forma rapida asignar permisos a todos 'chmod +x'
chown | (Change Owner), cambia la propiedad d
```
#### [Learn more...](https://blog.desdelinux.net/permisos-y-derechos-en-linux/)

### Conociendo las terminales en linux

* Las distribuciones de Linux para servidores no incluyen interfaz gráfica, ya que consumen muchos recursos. Esto significa que siempre vamos a trabajar desde la terminal.

* Las distribuciones de Linux para servidores no incluyen interfaz gráfica, ya que consumen muchos recursos. Esto significa que siempre vamos a trabajar desde la terminal.

* Tendremos disponibles 6 terminales virtuales a las que podemos entrar o salir con las teclas Ctrl + Alt + Fx. También podemos usar el comando chvt. La séptima terminal es la interfaz gráfica, así que en este caso no disponemos de ella.

* Cada usuario activo en nuestro sistema operativo crea una nueva conexión. Podemos ver todas estas conexiones con los comandos who y w (este último nos da un poco más de información).

* Para ver todos los procesos que corren en el sistema podemos usar el comando ps. Para filtrar los procesos y ver únicamente las conexiones de los usuarios usamos ps -ft tty.

* Este comando nos muestra el identificador de cada proceso. Para terminarlo podemos usar el comando kill -9 PID.

### Manejo y monitoreo de procesos y recursos del sistema

Para ver los procesos en sistemas Linux, contamos con el comando ‘ ps ’, que listará (de múltiples formas según las opciones que le pasemos) todos los procesos que se encuentran corriendo en nuestro equipo.

```
'ps' = todos los procesos
'man ps' = manual del comando ps
'ps aux' = (que mostrará un árbol jerárquico con la ruta del programa al que pertenece el proceso)
'ps axjf' = Nos permite mostrar el arbol de procesos
'ps aux | grep bash' = Nos permite filtrar por la palabra final los procesos
'top'= top nos da un informe en tiempo real de los los procesos y no estaticos como ps, man top
'jobs' = Al igual que el comando anterior, muestra los procesos. A diferencia de ps, es un comando interno de la terminal
'fg'=  Abre un proceso que estaba pausado"|" Pipe: Envia el standard output de un comando al standard input de otro.
"&" Ampersand: Envia un proceso al background
'nohup nombre-del-proceso' = Genera un archivo llamado “nohup.out” que muestra toda la información que produjo un proceso y lo revisamos con less o cat.

'free' = Me muestra información sobre la memoria de mi sistema. Con el modificador -h la información es más legible para un humano
'du' = Muestra información sobre el disco duro. Con el modificador -hsc y un directorio especificado muestra el tamaño de ese directorio
'htop' = Funciona como top pero funciona de forma más intuitiva

cat /proc/cpuinfo | grep "processor": Muestra información sobre el CPU
sudo ps auxf | sort -nr -k 3 | head -5: Muestra los 5 procesos que más uso hacen del CPU
sudo ps auxf | sort -nr -k 4 | head -5: Muestra los 5 procesos que más uso hacen de la memoria RAM
```
#### [Learn more](https://openwebinars.net/blog/20-comandos-para-administrar-y-gestionar--facilmente-los-procesos-linux/)

### Análisis de los parámetros de red

#### Ip privada

Una dirección IP Privada se utiliza para identificar equipos o dispositivos dentro de una red doméstica o privada. Se reservan para ello determinados rangos de direcciones:

* Clase A: 10.0.0.0 a 10.255.255.255
* Clase B: 172.16.0.0 a 172.31.255.255
* Clase C: 192.168.0.0 a 192.168.255.255

En una red, las direcciones IP Privadas deberán ser únicas para cada dispositivo o al duplicarlas surgirán problemas. Volviendo al ejemplo del servicio de paquetería, sería como si dos vecinos tuvieran el mismo nombre y la misma dirección, haciendo imposible saber a quién de ellos se deberá realizar la entrega.

Ahora bien, las direcciones IP Privadas sí pueden repetirse pero en redes distintas, en cuyo caso no habrá conflictos debido a que las redes se encuentran separadas. De la misma manera que es posible tener dos direcciones iguales pero en distintas ciudades.

#### Ip publica

En una red local habrá varias direcciones IP Privadas y generalmente una dirección IP Pública. Para conectar una red privada con Internet hará falta un “traductor” o NAT (Network Address Translation), que pasará los datos entre las direcciones IP Privadas y las direcciones IP Públicas.

La dirección IP Pública es aquella que nos ofrece el proveedor de acceso a Internet y se asigna a cualquier equipo o dispositivo conectado de forma directa a Internet. Por ejemplo, los servidores que alojan sitios web, los routers o modems que dan el acceso a Internet.

Las direcciones IP Públicas son siempre únicas, es decir, no se pueden repetir. Dos equipos con IP de ese tipo pueden conectarse directamente entre sí, por ejemplo, tu router con un servidor web o dos servidores web entre sí.

```
ifconfig ==> Interface Configuration / Se enlistan las tarjetas que tenemos y su direccionamiento especifico.

ip a ==> ip address show / También muestra la información de la red. Algunos modificadores para este comando son -4 para listar solo las ipv4 ó -6 para listar las ipv6.

hostname ==> Para visualizar el nombre del equipo, este hostname es como se identifica el equipo en las redes.

route -n ==> Para visualizar la puerta de enlace predeterminada del equipo. Muestra la IP routing table.

nslookup nombredominio ==> Para visualizar la ip de cualquier dominio especifico.

curl ==> Puede realizar simulaciones como las que hace Postman.

wget nombredominio ==> Para obtener información desde internet.
```
### Administración de paquetes acorde a la distribución

Administración de paquetes es un sistema que instala, actualiza, consulta o quita el software dentro de un sistema de archivos. En Linux hay muchos sistemas de administración de paquetes de software diferentes, pero los dos más populares son Debian y Red Hat. En el nivel más bajo del sistema de administración de paquetes de Debian está el comando dpkg.

```
Red Hat / CentOS / Fedora
  rpm: Red Hat Package Manager.
    Base de datos RPM, localizada en var/lib/rpm
    rpm -q para Listar todos los rpms instalados en la máquina. (query all)
    rpm -i paquete.rpm Realizar la instalación de un paquete. (install)
    rpm -e paquete.rpm Remover un paquete del sistema. (erase)
  Repositorios yum Permite instalar un paquete desde un repositorio sin tener que conocer la ruta del archivo o las dependencias.
yum install paquete

Debian / Ubuntu
  deb Debian package management.
    Base de datos DPKG, localizada en /var/lib/dpkg
    dpkg -l Listar todos los debs instalados en la máquina.
    dpkg -i paquete.deb Realizar la instalación de un paquete.
    dpkg -r paquete.deb Remover un paquete del sistema.
    dpkg-reconfigure
    dpkg-reconfigure paquete Volver a ejecutar el asistente de configuración si está disponible.
  repositorios apt otra forma de instalar.
    apt install paquete
    apt uninstall paquete
```


### Debian/Ubuntu

Uno de los puntos fuertes de la distribución Debian es su gestor de paquetes apt y su interfaz aptitude. La gestión de las actualizaciones y las instalaciones de software se hace mediante este potente e intuitivo gestor de paquetes. Con apt y aptitude se puede, por ejemplo, actualizar todo un sistema con apenas un par de comandos.

#### Actualización de la lista de paquetes
```
apt update
Actualiza en el equipo la lista de paquetes que hay en los repositorios configurados en el archivo /etc/apt/sources.list. Este comando hay que ejecutarlo antes de instalar, desinstalar o gestionar paquetes
(Equivalente a apt-get update o aptitude update).
```

#### Instalación de paquetes
```
apt install <paquete>
Instala un paquete de software y todos los paquetes de los que depende el paquete instalado. Se pueden instalar varios paquetes a la vez, usando esta sintaxis: apt-get install <paquete1> <paquete2> <paquete3>.
(Equivalente a apt-get install <paquete> o aptitude install <paquete>).
apt install –reinstall <paquete>
Re-instala un paquete, sustituyendo los archivos. Bastante útil, cuando se quiere reponer archivos que han sido cambiados
(Equivalente a apt-get reinstall <paquete> o aptitude reinstall <paquete>).
```

#### Actualización del sistema
```
apt upgrade
Actualiza todos los paquetes instalados en el sistema a la última versión que haya en el momento de ejecutar el comando. Si alguna actualización necesita la instalación de un nuevo paquete, esa actualización no se realiza. Actualiza sólo los paquetes que no requieran nuevas instalaciones.
(Equivalente a apt-get upgrade o aptitude safe-upgrade).
apt full-upgrade
Actualiza todos los paquetes instalados en el sistema a la última versión que haya en el momento de ejecutar el comando. Si alguna actualización necesita la instalación de un nuevo paquete, el nuevo paquete se instala y se completa la actualización. Actualiza todos los paquetes, y si hay que instalar nuevos paquetes para la actualización se instalan.
(Equivalente a apt-get dist-upgrade o aptitude full-upgrade).
```
#### Desinstalación y eliminación de paquetes
```
apt remove <paquete>
Desinstala un paquete, pero mantiene los archivos de instalación del paquete. Es posible desinstalar varios paquetes a la vez, usando la sintaxis: aptt remove <paquete> <paquete> <…>.
(Equivalente a apt-get remove <paquete> o aptitude remove <paquete>).
apt purge <paquete>
Elimina por completo un paquete, incluyendo los ficheros de configuración
(Equivalente a apt-get purge <paquete> oaptitude purge <paquete>).
apt autoremove
Elimina los paquetes auto-instalados que ya no sean necesarios.
(Equivalente a apt-get autoremove, sin equivalente en aptitude).
apt autoremove –purge
Elimina los paquetes auto-instalados que ya no sean necesarios, incluyendo los ficheros de configuración.
(Equivalente a apt-get autoremove –purge, sin equivalente en aptitude).
```
#### Búsqueda de paquetes
```
apt search <criterio>
Busca en la lista de paquetes y muestra las coincidencias de criterio
(Equivalente a apt-cache search <criterio> o aptitude search <criterio>)
Informaciones sobre paquetes
apt show <paquete>
Muestra información y características del paquete consultado
(Equivalente a apt-cache show <paquete> o aptitude show <paquete>)
```
#### Limpiar la cache de paquetes
```
apt-get clean
Elimina todos los archivos de paquetes existentes en cache
(es equivalente a aptitude clean).
apt-clean autoclean
Elimina los archivos de paquetes de versiones pasadas existentes en cache, pero mantiene los paquetes de versiones actualizados
(Equivalente a apt-get autoclean o aptitude autoclean).
```

### Festor de paquetes SNAP

Los nuevos paquetes Snap incluyen todos los archivos necesarios para la correcta instalación y ejecución de una aplicación y todas las dependencias del mismo de manera que la instalación esté asegurada. Además, tanto la aplicación como las dependencias se instalan de manera aislada evitando conflictos entre ellas y que, si se modifica una dependencia, otra aplicación pueda dejar de funcionar.

 ```
 snap find = Y nos aparecerán todos los paquetes disponibles.
 snap find name = búsquedas más concretas añadiendo al final una parte del nombre del paquete que buscamos.
 sudo snap install nombre-paquete = Ahora ya podemos ejecutarla, desde el propio terminal, ejecutándola por el nombre de la aplicación.
 sudo snap refresh nombre-paquete = Este comando buscará si existe una nueva versión del paquete Snap y, de haberla, la descargará e instalará automáticamente.
 snap list =  ver una lista con todos los paquetes instalados.
 sudo snap remove nombre-paquete =  para desinstalar los paquetes.

 ```
 [mas..](https://snapcraft.io/docs/getting-started#5)
 
#### Del curo
```
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
sudo apt search mysql
sudo apt search "mysql-server$"
sudo apt-cache search "mysql-server$"
dpkg -l
sudo dkpg-reconfigure tzdata
date
sudo snap search aws-cli
sudo snap refresh --list
sudo snap info aws-cli
sudo snap install canonical-livepatch
```

#### Por seguridad, actualizar con frecuencia
Es imprescindible que el servidor esté siempre al día con sus actualizaciones. La comunidad debian está actualizando constantemente el software para corregir bugs y fallos de seguridad. Un sistema no actualizado es una puerta abierta a los hackers y los crackers. La mejor fuente para buscar software actualizado es internet. Hay que escoger cuidadosamente las fuentes de software o repositórios y hacer actualizaciones frecuentemente.

También es importante seguir de cerca todas las informaciones referentes a bugs (conflictos o problemas que producen algunos paquetes) y fallos de seguridad, así como estar atentos a cuál es la mejor forma de corregir esos fallos. La distribución edita listas con los anuncios de seguridad y con sus respectivas correcciones en la página de la distribución o si prefiere en las listas de distribución.

### CentOs/Yum/Rpm
```
rpm -qa = Enlista los paquetes instalados en el SO.

rpm -qi nombre_paquete = Mostrar la información sobre un paquete especifico.

Con Bash podemos hacer scripting en SO Linux.

rpm -qc nombre_paquete = Muestra todos los archivos involucrados sobre el paquete.

También podemos usar yum. Pero lo primero es dar yum update. Pero para poder ejecutarlo necesitamos un usuario con todos los permisos, por ejemplo el usuario root.
Si se muestra un # al final del nombre del usuario, eso indica que estamos trabajando con un usuario root. Por ejemplo:
[root@server ~]#

Lo ideal es nunca trabajar con un usuario root. Lo ideal es crear usuarios que tengan ciertos permisos específicos, por medidas de seguridad y evitar errores.

yum install net-tools = Para habilitar el ifconfig.

rpm -e nombre_paquete = Para eliminar un paquete del SO.
```
### Nagios: Desempaquetado, descompresión, compilación e instalación de paquetes

No todo el software que necesitamos se encuentra en los repositorios. Debido a esto, algunas veces debemos descargar el software, realizar un proceso de descompresión y desempaquetado para finalmente instalar la herramienta.

Instalación de algunas herramientas para manejar una base de datos MySQL (recuerda que instalaremos y trabaremos con MySQL en una próxima clase):

```
sudo apt install build-essential libgd-dev openssl libssl-dev unzip apache2 php gcc libdbi-perl libdbd-mysql-perl
```
Instalación de Nagios:
```
wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.4.4.tar.gz -O nagioscore.tar.gz 
```
#### Descomprimir y desempaquetar archivos con tar:
```
tar xvzf nagioscore.tar.gz
```
Este comando creará una carpeta nagios-4.4.4. El nombre de la carpeta puede variar dependiendo de la versión que descargaste. Entrando a esta carpeta podemos ejecutar diferentes archivos y comandos para configurar el software y realizar la instalación.

# 1:
```
sudo ./configure --with-https-conf=/etc/apache2/sites-enabled
```
# 2:
```
sudo make all
```
# 3:
```
sudo make install
```
# 4:
```
sudo make install-init
```
# 5:
```
sudo make install-commandmode
```
# 6:
```
sudo make install-config
```
#7:
```
sudo make install-webconf
```
Por último, para administrar el servicio de nagios podemos usar el comando sudo systemctl (status, start, restart, reload, stop, enable, disable, list-dependencies) nagios.

### Los usuarios, una tarea vital en el proceso de administración del sistema operativo

* El comando ```id``` nos muestra el identificador único (uid) de cada usuario en nuestro sistema operativo. El ID 0 está reservado para el usuario root.

* Con el comando ```whoami``` podemos ver con qué usuario estamos trabajando en este momento. Podemos ver todos los usuarios del sistema leyendo el archivo /etc/passwd.

* Las contraseñas de los usuarios están almacenadas en el archivo ```/etc/shadow```, pero están cifradas. Y solo el usuario root tiene permisos de lectura/escritura.

* Para cambiar la contraseña de nuestros usuarios usamos el comando ```passwd nombre_usuario``` .

![imagen](https://static.platzi.com/media/user_upload/Untitled-2bd3cf0c-a997-49eb-a38e-a77caaffb1c3.jpg)

#### Comandos para administrar cuentas de usuarios:

* sudo useradd nombre-usuario: crea un usuario sin asignarle inmediatamente alguna contraseña ni consultar más información. Debemos terminar de configurar esta cuenta a mano posteriormente.
* sudo adduser nombre-usuario: crea un nuevo usuario con contraseña y algo más de información. También creará una nueva carpeta en la carpeta /home/.
* userdel nombre-usuario: eliminar cuentas de usuarios.
* usermod: modificar la información de alguna cuenta.
* Nunca modifiques a mano el archivo /etc/passwd con un editor de texto. Para administrar los usuarios debemos usar los comandos que estudiamos en clase.

#### Membresía de los grupos
* Los grupos nos ayudan a darle los mismos permisos a diferentes usuarios al mismo tiempo, sin necesidad de asignar el mismo permiso a cada usuario individualmente. Todos los usuarios que pertenezcan al mismo grupo tendrán los mismos permisos.

* Para cambiar de usuario sin necesidad de reiniciar el sistema podemos usar el comando ```su - nombre-usuario```. También podemos cambiar de usuario sin necesidad de saber su contraseña usando el comando ```sudo su - nombre-usuario```.

* Para ver a qué grupos pertenecen nuestros usuarios usamos el comando ```groups nombre-usuario```. Para agregar usuarios a un nuevo grupo usamos el comando ```sudo gpasswd -a nombre-usuario nombre-grupo``` . Los eliminamos de la misma forma con ```gpasswd -d nombre-usuario grupo(sudo)```.

* Para esto también podemos usar el comando del grupo super usuario donde se encuentra ```sudo usermod -aG nombre-grupo nombre-usuario```. Recuerda que en este caso el orden en que escribimos el grupo y el ususario se invierte.

* Para listar los permisos de nuestros usuarios ejecutamos el comando sudo -l.


### Usando PAM para el control de acceso de usuarios

Linux-PAM (abreviatura de módulos de autenticación conectables que evolucionaron de la arquitectura Unix-PAM) es un potente conjunto de bibliotecas compartidas que se utiliza para autenticar dinámicamente a un usuario en aplicaciones (o servicios ) en un sistema Linux.

Integra múltiples módulos de autenticación de bajo nivel en una API de alto nivel que proporciona soporte de autenticación dinámica para aplicaciones. Esto permite a los desarrolladores escribir aplicaciones que requieren autenticación, independientemente del sistema de autenticación subyacente.

PAM es un mecanismo para administrar a los usuarios de nuestro sistema operativo. Nos permite autenticar usuarios, controlar la cantidad de procesos que ejecutan cada uno, verificar la fortaleza de sus contraseñas, ver la hora a la que se conectan por SSH, entre otras.

```
'ls /etc/pam.d' = configuraciones respectivas que se pueden hacer sobre PAN
'ls /lib64/security' = Libreria de acceso de PAM
'ls /etc/security' = Realizar configuraciones para PAM
'pwscore' = Evaluar que tan buena es una contrasena
'ulimit -u 10  --numero de procesos' = Listamos los permisos del usuario lle agregamos -u para cambiar el  liminte mas el numero de 10 procesos
'vi /etc/security/time.conf' = configurar el tiempo determinado en que los usuarios de se deben logear.
'sudo vi /etc/security/time.conf ' = cambiar el permiso del archivo
'gpasswd -a usuario wheel' = agg usuario a un grupo.
'groups usuario' = ver grupos
```

### Autenticación de clientes y servidores sobre SSH

SSH o Secure Shell, es un protocolo de administración remota que le permite a los usuarios controlar y modificar sus servidores remotos a través de Internet a través de un mecanismo de autenticación.

Proporciona un mecanismo para autenticar un usuario remoto, transferir entradas desde el cliente al host y retransmitir la salida de vuelta al cliente. El servicio se creó como un reemplazo seguro para el Telnet sin cifrar y utiliza técnicas criptográficas para garantizar que todas las comunicaciones hacia y desde el servidor remoto sucedan de manera encriptada.

#### Funcionamiento

* SSH es un protocolo que nos ayuda a conectarnos a nuestros servidores desde nuestras máquinas para administrarlos de forma remota. No es muy recomendado usar otros protocolos como Telnet, ya que son inseguros y están deprecados.

*Con el comando ```ssh-keygen``` podemos generar llaves públicas y privadas en nuestros sistemas, de esta forma podremos conectarnos a servidores remotos o, si es el caso, permitir que otras personas se conecten a nuestra máquina.

* Para conectarnos desde nuestra máquina a un servidor remoto debemos:

1. Ejecutar el comando ``ssh-copy-id -i ubicación-llave-pública nombre-usuario@dirección-IP-servidor-remoto`` y escribir nuestra contraseña para enviar nuestra llave pública al servidor.
2, Usar el comando ssh nombre-usuario@dirección-IP-servidor-remoto para conectarnos al servidor sin necesidad de escribir contraseñas.
3. También podemos usar el comando ssh -v ... para ver la información o los errores de nuestra conexión con el servidor. Puedes usar la letra v hasta 4 veces (-vvvv) para leer más información.

* Las configuraciones de SSH se encuentran en el archivo ``/etc/ssh/sshd_config ```












