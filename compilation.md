# Práctica 04. Compilación de programas

# Factor de ponderación: 5

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Cree una cuenta en la plataforma Jutge y conozca el funcionamiento básico de la misma
* Conozca algunos detalles del proceso de compilación de programas simples escritos en C++

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva) que se tendrán en cuenta a la hora de evaluar esta práctica:
* Ha de demostrar que conoce el proceso de compilación de programas usando el de C++ de GNU
* Ha de acreditar que dispone de una cuenta de usuario en la plataforma Jutge

* AÑADIR

* Ha de acreditar que es capaz de editar ficheros remotos en su VM usando vi
* Ha de demostrar que es capaz de ejecutar comandos Linux en su VM
* Ha de acreditarse que se es capaz de conectarse a su máquina virtual (VM) de la asignatura 

### El fichero `.vimrc`
En vim se pueden modificar muchos parámetros del editor mientras se editan los ficheros. 
Por ejemplo, tecleando en modo comando `:set number` vim activará la numeración de líneas, algo que puede ser útil para programar.
Tecleando `:syntax on`, se activa para el fichero actual el coloreado de sintaxis, es decir, que las palabras especiales que el editor 
entienda que tienen un significado concreto aparecerán en diferentes colores. 
Si se está programando en C++, por ejemplo, las palabras reservadas de ese lenguaje (ya aprenderá lo que son) aparecerán de un color, 
las cadenas de otro, etc (algo realmente útil a la hora de programar).

Cualquier tipo de opción, macro, comando o función que vim entienda puede ser incluída en el fichero `.vimrc` 
en el directorio `$HOME` del usuario de modo que se aplique como opción por defecto cuando se lance Vim. 
Pruebe a crear un fichero `.vimrc` (por defecto normalmente no existirá) en el directorio HOME de su máquina
virtual, que contenga lo siguiente:
``` .bash
set nocompatible
set number
set ruler
syntax on
```

Esto hará que siempre que edite un fichero, aparezca numeración de líneas (`set number`), 
un indicador de fila y columna en la barra de estado (`set ruler`) y resaltado de sintaxis 
(si está definida para el tipo de fichero que esté editando) activado. 
Es algo así como el fichero de opciones de vim para nuestro usuario.

Así, se puede utilizar este fichero de configuración de vim para indicar aquellas configuraciones con las que estemos más cómodos, 
de forma que se adapte vim a nuestras necesidades. 
Para comenzar se recomienda un fichero `.vimrc` con el siguiente contenido:
``` .bash
" Fichero .vimrc de mi usuario
" Los comentarios en este fichero se ponen con comillas dobles

" Esta opción debe estar la primera porque cambia otras opciones
" nocompatible permite funciones que VI no soporta
set nocompatible

set number

" Muestra la posición del cursor en todo momento
set ruler

" Al presionar tab, inserta 2 espacios (Guía de estilo de Google)
set expandtab

" Muestra los tabs existente con 2 espacios
set tabstop=2

" shiftwidth (el número de espacios a usar cuando se indenta)
set sw=2

syntax on

" Volver a la última posición al abrir un fichero
" https://stackoverflow.com/questions/7894330/preserve-last-editing-position-in-vim
autocmd BufReadPost *
     \ if line("'\"") > 0 && line("'\"") <= line("$") |
     \   exe "normal! g`\"" |
     \ endif
```
Es fácil hallar en internet ejemplos de ficheros `.vimrc` escritos por usuarios expertos.
[Este](https://gist.github.com/simonista/8703722)
por ejemplo podría ser uno de esos ficheros.
Puede Ud. tomar del mismo (o de otros) aquellas opciones que le parezcan interesantes pero la recomendación es
que comience con uno simple, como el que se ha propuesto, y que no introduzca en él una opción salvo que
entienda bien la finalidad de la misma.

### La plataforma Jutge
[Jutge](https://jutge.org/) 
es una plataforma que ha sido desarrollada en la
[UPC](https://www.upc.edu/en) 
para uso docente en asignaturas de programación.
La plataforma ofrece una gran cantidad de problemas que los estudiantes han de resolver y el Jutge (juez en catalán) asigna un 
[veredicto](https://jutge.org/documentation/verdicts) 
a cada solución que se suba a la plataforma.

Jutge solo evalúa los programas desde el punto de vista de la corrección del resultado que ofrecen, 
no evalúa la calidad del código en cuanto a otros aspectos: diseño, estilo, formato, etc.
Para determinar si un programa es correcto o no, Jutge aplica varios tests al programa (tests unitarios)
que tratan de acreditar la bondad de la solución, que podría ser parcialmente correcta.
Algunos de esos tests son públicos y la programadora debiera encargarse de asegurar que su programa pasa
esos tests públicos (ofrece los resultados esperados) antes de enviar el programa al juez.

Para la realización de futuras prácticas de la asignatura deberá Ud. registrarse en la plataform Jutge. 
Recibirá para ello un mensaje de correo con asunto similar a: "Jutge.org - You have been invited to a course". 
Acepte esa invitación y regístrese en el curso "Informática Básica" en la plataforma Jutge usando para ello su
cuenta de correo electrónico institucional.
Es importante que se registre en Jutge con esa cuenta y no otra.

[Este documento](https://docs.google.com/presentation/d/1k53XMnI6Z9DTlBHRJ0cBqix0KZyVIFUgD61XAcsgA9Y/edit?usp=sharing)
contiene información algo más detallada sobre el uso de la plataforma Jutge. 
Estúdielo para preparse a usar Jutge en el futuro.



### Comandos Linux útiles a la hora de procesar ficheros de texto
Por último, estudie también aquellos comandos de linux que tienen relación con la gestión de ficheros.
En particular estudie (con sus páginas de manual) y practique los comandos 
[file](https://ss64.com/bash/file.html),
[grep](https://ss64.com/bash/grep.html),
[wc](https://ss64.com/bash/wc.html) y
[find](https://ss64.com/bash/find.html)
