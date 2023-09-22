[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **GIT ADD y GIT COMMIT**

Para explicar lo que hacen los comandos `git add` y `git commit` antes debemos entender las **areas de git**.

![git_areas.png](/IMG/Git_areas.png "Areas de git")

Imaginemos git como una mesa de trabajo, en esa mesa ponemos nuestros documentos y trabajamos con ellos. 

En el momento en creamos un nuevo documento o editamos uno existente dentro del directorio de nuestro repositorio estos archivos pasan al area del directorio de trabajo, estos documentos todavía no están están en seguimiento, git nos informará de su existencia si ejecutamos el comando `git status`

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
Significa que hemos hecho algo con ese archivo pero git todavía no lo tiene en su lista de archivos que debe tener controlados. 

> ## NOTA:
> Es posible indicarle a git que ignore algún archivo mediante la edición del archivo `.gitignore` esto se explica más tarde.

Tal como lo tenemos hasta ahora podemos seguir editando nuestros archivos y sería lo mismo que trabajar sin **Git**, es necesario que **Git** haga un seguimiento de los archivos que forman nuestro proyecto en seguimiento poder ir haciéndole “fotos” cada vez que lo necesitemos.

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

Ahora nuestro archivo aparece en la sección "**Cambios a ser confirmados**", esto es el area STAGE







