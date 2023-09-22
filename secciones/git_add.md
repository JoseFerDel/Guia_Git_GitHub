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

En este directorio ya hemos ejecutado `git init` así que git lo tiene en seguimiento, se ha agregado un archivo y después hemos ejecutado 'git status', lo que se nos muestra es 