---
title: "Informe de la práctica 1: configuración de la máquina virtual del IaaS"
---
# Índice
[Introducción](#introducción)

[Conexión y configuración de la máquina virtual](#conexión-y-configuración-de-la-máquina-virtual)
  * [Tomar la máquina virtual del pool y SSH](#tomar-la-máquina-virtual-del-pool-y-ssh)
  * [Modificación del nombre del host, la MV y actualización de la misma](#modificación-del-nombre-del-host-la-mv-y-actualización-de-la-misma)
# Introducción
En este informe se detallarán los pasos a seguir para llevar a cabo la configuración e instalación de la 
máquina virtual de la asignatura.

# Pasos previos 
Para realizar esta práctica es necesario tener conocimientos básicos de *GitHub Skills* y *Jekyll*. Para ello 
seguí los tutoriales facilitados por el profesorado:
* [Introduction to GitHub](https://github.com/skills/introduction-to-github)
* [Communicate using Markdown](https://github.com/skills/communicate-using-markdown)
* [GitHub Pages](https://github.com/skills/github-pages)

A la hora de seguir estos tutoriales me encontré con varios problemas:
* Hasta que no pude clonar el repositorio en la máquina virtual tuve que crear un repositorio personal para 
poder ir documentando a medida que iba realizando la práctica.
* Las imágenes y los vídeos de este informe no se añadían puesto que están guardados en ``` media/ ```. 
Para solucionarlo simplemente concreté donde se alojaban con ``` media/images``` o ``` media/videos```.
* Para hacer el índice no me fue posible poner títulos como *1. Introducción*. Intenté poner 
*1.-introducción* debido a que el formato de los links no lleva espacios ni mayúsculas, pero tampoco funcionó.
Así que opté por solo poner el título *Introducción*.
* Quería lograr en el archivo ```index.md``` un índice desplegable como el que se puede encontrar en los tutoriales, 
concretamente, en el *README.MD*.
![Despliegue de pasos](media/videos/Despliegue_de_pasos.gif)
Pero esto me fue imposible. Por lo visto *Jekyll* no acepta el formato *Markdown* si se encuentra dentro de algunas
etiquetas de *HTML* como ``` <details>```.

# Conexión y configuración de la máquina virtual
Ahora procederemos a detallar los pasos seguidos para poder conectar y configurar la máquina virtual
### Tomar la máquina virtual del pool y SSH
Lo primero es tener instalada la VPN *Global Protect* para conectarse a la VPN de la ULL. Una vez conectados
accedemos a [iaas.ull.es](iaas.ull.es), introducimos nuestras credenciales y tomamos una máquina virtual del
pool. Cuando la máquina esté operativa tomamos su IP, luego accedemos a la *Consola VNC* e introducimos ``` usuario ```
y ``` usuario ``` como nombre y contraseña.

Al entrar en [iaas.ull.es](iaas.ull.es) no tuve ningún problema la primera vez, cogí la MV y su correspondiente IP. El
problema surge la segunda vez que intenté conectarme, ya que la página estaba caída. Desde *Visual Studio Code* 
pretendí hacer un *SHH* pero al no haberme registrado con ``` usuario ``` y ``` usuario ``` y puesto una nueva 
contraseña no me dejaba hacer *SSH*
![Fallo ssh](media/images/fallossh.bmp)
Como podemos ver en la imagen conecta correctamente, pero a la hora de solicitar el cambio de contraseña se 
pueden apreciar los errores, sobretodo el error ```[19:29:24.435] Resolver error: failed```.
Una vez arreglado el acceso a la página ya pude entrar y hacer un SSH desde *Visual Studio Code* desde la extensión oficial [Remote-SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) poniendo ```ssh usuario@10.6.131.207```

## Modificación del nombre del host, la MV y actualización de la misma
Como podemos ver en el prompt: ```usuario@ubuntu:~$``` tenemos como nombre de la máquina ubuntu. 
Dentro del archivo ```hostname``` alojado en ```/etc/hostname``` está especificado el nombre del host, por lo tanto
procederemos a cambiarlo mediante los siguientes pasos:
* 
```
usuario@ubuntu:~$ cat /etc/hostname
ubuntu
```

Con este comando comprobamos dentro del archivo ```hostname``` que el nombre es *ubuntu* como mencionamos 
anteriormente. Acto seguido hacemos uso del comando ```sudo vi /etc/hostname``` para editar el fichero. Al 
hacerlo nos debería aparecer lo siguiente:
```
ubuntu
~                                                                                                                                                                                                        
~                                
1,5           All
```
Simplemente le damos a la tecla i y pasamos a modo insertar, una vez cambié el nombre por ```dsi2223```. De 
esta manera el archivo queda de la siguiente manera:
```
dsi2223
~                                                                                                                                                                                                        
~                                                                                                                                                                                         
"/etc/hostname" 1L, 8C                                                                                                                                                                 1,7           All
```
Para guardar el archivo pulsamos la tecla ```esc```, escribimos ```:wq``` y pulsamos enter

## Modificación del nombre de host
Para ver el nombre actual de host, podemos mirar el prompt ```usuario@ubuntu:~$``` y ver que tenemos el nombre 
de host ```ubuntu```

O bien con el comando:
* 
```
usuario@ubuntu:~$ cat /etc/hosts
127.0.0.1 localhost
127.0.1.1 ubuntu
```

Podemos ver en la línea ```127.0.1.1 ubuntu``` el nombre, este lo cambiamos mediante ```sudo vi /etc/hosts``` 
del actual a ``` phoenix```