[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

![git_áreas.png](/IMG/Git_áreas_02.png "git init")

# **git add**

Antes de ejecutar el comando `git init` para iniciar un nuevo repositorio los archivos que tengamos en ese momento se encuentran en un directorio de trabajo normal y corriente **sin seguimiento** por por parte de **git**.

* Después de ejecutar `git init` los archivos de ese directorio, si los hubiese, pasan a estar en seguimiento.
* Si ejecutamos el comando `git status` **git** nos informará de que han habido cambios si hemos creado un nuevo documento, o editado uno existente, se nos informa de los cambios.
* Ahora los archivos siguen en el directorio de trabajo pero ahora con seguimeinto porque al ejecutar `git init` le estamos diciendo a **git** que le eche un ojo a ese directorio por si sufre cambios ,**git** nos informará de la existencia de estos archivos nuevos o con cambios si ejecutamos el comando `git status`.

Por ejemplo:
``` 
zet@wukong:~/Escritorio/Hello_Git$ git status
En la rama main

No hay commits todavía

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
        hellogit.py

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
zet@wukong:~/Escritorio/Hello_Git$ 
``` 

En este directorio ya hemos ejecutado `git init` así que **git** lo tiene en seguimiento, se ha agregado un archivo y después hemos ejecutado 'git status' para ver el estado del repositorio.
Aquí podemos ver que aparece un nuevo archivo bajo la sección "Archivos sin seguimiento:", que aparezca en esta sección significa que **hellogit.py** es un archivo nuevo, no una modificación de un archivo que **git** ya conocía.


Para "capturar" el estado del repositorio en este momento con el nuevo archivo recién creado **hellogit.py** ejecutaremos el comando `git add`.     
    
    
> ## Nota 1
> Guardar el estado del repositorio tiene dos fases, una al ejecutar `git add` y otra al ejecutar justo después `git commit` (Se habla de `git commit` más adelante.)

Así que ejecutamos `git add` de la siguiente forma:

### git add [nombre_del_archivo]
(para cada archivo pendiente)

o también:

### git add . 
(el punto en este contexto se refiere a todos los archivos sin seguimiento.)

> ## Nota 2
> El comando 'git add' actúa sobre el directorio actual en el que nos encontremos y sus subdirectorios, si por algún motivo estamos en un subdirectorio de nuestro directorio de trabajo los archivos que quedan en directorios superiores no podrán agregarse al área STAGE con 'git add', tendremos que volver a ejecutar 'git add' desde el primer nivel de nuestro directorio, no desde sus subdirectorios.

Si tras ejecutar este comando volvemos a ejecutar `git status`, y todo ha ido bien, en el caso de nuestro ejemplo anterior veremos lo siguiente:
```
zet@wukong:~/Escritorio/Hello_Git$  
zet@wukong:~/Escritorio/Hello_Git$ git status 
En la rama main 
 
No hay commits todavía 
 
Cambios a ser confirmados: 
  (usa "git rm --cached <archivo>..." para sacar del área de stage) 
        nuevos archivos: hellogit.py 
 
zet@wukong:~/Escritorio/Hello_Git$
```
Utilizar `git add` pone nuestro archivos en el área STAGE.

![git_áreas](/IMG/Git_áreas_03.png "git add")

## área STAGE
Ya casi tenemos el registro de nuestro repositorio, la fase en la que se encuentran ahora los archivos implicados se llama **STAGE** mientras están en el "escenario" los archivos puede seguir adelante y dejar registrados sus cambios en un registro ejecutando un 'commit' o salir de esta zona y volver al directorio de trabajo sin guardar nada.

> ## Nota 3:
> Algunas acciones en **git** no pueden realizarse hasta que todos los archvos del directorio hayan sido registrados con un `commit` o descartados de alguna forma, osea que si hay algo todavía en STAGE algunas acciones no podrán realizarse y se nos informará de ello.






