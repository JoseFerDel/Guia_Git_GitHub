[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)


# **git add**

Antes de ejecutar el comando `git init` para iniciar un nuevo repositorio los archivos que tengamos en ese momento se encuentran en un directorio de trabajo normal y corriente **sin seguimiento** por por parte de **git**.

Después de ejecutar `git init` los archivos de ese directorio, si los hubiese, pasan a estar en seguimiento, en el momento en que creemos un nuevo documento, o editamos uno existente, dentro del directorio de nuestro repositorio **git** nos informará de que han habido cambios si ejecutamos el comando `git status`, ahora los archivos siguen en el area directorio de trabajo, pero ahora con seguimeinto porque al ejecutar `git init` le estamos diciendo a **git** que le eche un ojo a ese directorio por si sufre cambios ,**git** nos informará de la existencia de estos archivos nuevos o con cambios si ejecutamos el comando `git status`.

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
Aquí podemos ver que aparece un nuevo archivo bajo la sección "Archivos sin seguimiento:", que aparezca en esta sección significa que **hellogit.py** es un archivo nuevo, no una modificación.


Para "capturar" el estado del repositorio en este momento con el nuevo archivo recién creado **hellogit.py** ejecutaremos el comando `git add`.

Obtener este registro del estado actual del repositorio tiene dos fases, una al ejecutar `git add` y otra al ejecutar justo después `git commit` (Se habla de `git commit` más adelante.)

Así que ejecutamos `git add` de la siguiente forma:

### git add [nombre_del_archivo]
(para cada archivo pendiente)

o también:

### git add . 
(el punto en este contexto se refiere a todos los archivos sin seguimiento.)

Si tras ejecutar este comando volvermos a ejecutar `git status` en el caso de nuestro ejemplo anterior veremos lo siguiente:
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
Utilizar `git add` pone nuestro archivos en el area STAGE.

![git_areas](/IMG/Git_areas_03.png "git add")
