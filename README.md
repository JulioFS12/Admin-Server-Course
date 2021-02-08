# Admin-Server-Course

## INSTALAR LINUX CENTOS

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
