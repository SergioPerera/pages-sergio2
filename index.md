---
title: "Informe de la práctica 1: configuración de la máquina virtual del IaaS"
---
# Índice
[Introducción](#introducción)

# Introducción
En este informe se detallarán los pasos a seguir para llevar a cabo la configuración e instalación de la 
máquina virtual de la asignatura.

# Pasos previos 
Para realizar esta práctica es necesario tener conocimientos básicos de GitHub Skills y Jekyll. Para ello 
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
* Quería lograr en el archivo index.md un índice desplegable como el que se puede encontrar en los tutoriales, 
concretamente, en el README.MD..
![Despliegue de pasos](media/videos/Despliegue_de_pasos.gif)
Pero esto me fue imposible. Por lo visto Jekyll no acepta el formato Markdown si se encuentra dentro de algunas
etiquetas de HTML como ``` <details>```.