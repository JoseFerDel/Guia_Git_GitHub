[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **GIT ADD y GIT COMMIT**

Para explicar lo que hacen los comandos `git add` y `git commit` antes debemos entender las **areas de git**.

![git_areas.png](/IMG/Git_areas.png "Areas de git")

## **AREA WORKING DIRECTORY**

Antes de ejecutar el comando `git init` para iniciar un nuevo repositorio los archivos que tengamos en ese momento se encuentran en un Working directory (directorio de trabajo normal y corriente) **sin seguimiento** por por parte de **git**.

Después de ejecutar `git init` los archivos de ese directorio pasan a estar en seguimiento, en el momento en que creemos un nuevo documento, o editamos uno existente, dentro del directorio de nuestro repositorio **git** nos informará de que han habido cambios si ejecutamos el comando `git status`, ahora los archivos siguen en el area **Working directory**, pero ahora con seguimeinto porque al ejecutar `git init` le estamos diciendo a **git** que les eche un ojo a ese directorio por si sufre cambios ,**git** nos informará de la existencia de estos archivos nuevos o con cambios si ejecutamos el comando `git status`

## **git status**
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

En este ejemplo vemos que en la sección "**Archivos sin seguimiento"** ha aparecido un nuevo archivo llamado **hellogit.py**
Significa que hemos hecho algo con ese archivo y git nos lo muestra en este area para que le podamos decir que queremos que haga con ellos.  

> ## NOTA:
> Es posible indicarle a git que ignore algún archivo mediante la edición del archivo `.gitignore` esto se explica más tarde.

Tal como lo tenemos hasta ahora podemos seguir editando nuestros archivos y sería lo mismo que trabajar sin **Git**, es necesario que **Git** haga una captura o "foto" del estado actual de los archivos para guardarlo por si queremos volver a este momento del proyecto en el futuro.

De esta forma si edito un archvivo pero tras guardarlo me doy cuenta de que todo ha sido un terrible error siempre puedo volver a alguna de las versiones pasadas del mismo archivo.

## **git add**

Ok, para que git haga el seguimiento de estos archivos con cambios mostrados por el comando `git status` utilizaremos el comando `git add` de la siguiente forma:

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


## **Area STAGE**

Ahora nuestro archivo aparece en la sección "**Cambios a ser confirmados**", esto es el area STAGE, puede parecer redundante pero git está pensado precisamente para eso, para tener control de todo, los archivos en el area STAGE siguen sin formar parte de ninguna "foto" del estado de nuestro proyecto, sigamos que solo falta confirmar, para ello utilizaremos el comando `git commit`.









