[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git init (iniciar repositorio)**

Supongamos que tenemos un directorio en nuestro equipo donde guardamos los archivos que vamos editando para nuestro proyecto.
De momento no estamos utilizando git, aunque esté instalado, así que nuestro proyecto se encuentra simplemente en un directorio de trabajo (Working directory).

![git_areas.png](/IMG/Git_areas_01.png "git init")

En este punto git no está haciendo un seguimiento de nuestros archivos y si se borrase el directorio se perdería todo.

El comando `git init` ejecutado desde un directorio indicará a **git** que queremos que ese directorio contenga un nuevo **repositorio**.

Para iniciar un contexto de Git en un directorio concreto primero nos desplazaremos a ese directorio desde el terminal y escribiremos el comando `git init`:

![git_init_01](/IMG/git_init_01.jpg "git_init")

Hecho esto, y dentro del directorio de nuestro proyecto, se habrá creado un nuevo directorio oculto llamado **.git**

![git_init_02](/IMG/git_init_02.jpg ".git")

Como curiosidad dentro de **.git** encontramos lo siguiente: 
```
zet@wukong:~/Escritorio/Hello_Git$ 
zet@wukong:~/Escritorio/Hello_Git$ cd .git
zet@wukong:~/Escritorio/Hello_Git/.git$ 
zet@wukong:~/Escritorio/Hello_Git/.git$ ls -lA
total 32
drwxr-xr-x 2 zet zet 4096 jul 10 17:47 branches
-rw-r--r-- 1 zet zet   92 jul 10 17:47 config
-rw-r--r-- 1 zet zet   73 jul 10 17:47 description
-rw-r--r-- 1 zet zet   23 jul 10 17:47 HEAD
drwxr-xr-x 2 zet zet 4096 jul 10 17:47 hooks
drwxr-xr-x 2 zet zet 4096 jul 10 17:47 info
drwxr-xr-x 4 zet zet 4096 jul 10 17:47 objects
drwxr-xr-x 4 zet zet 4096 jul 10 17:47 refs
zet@wukong:~/Escritorio/Hello_Git/.git$ 
```
El directorio **.git** contiene los archivos necesarios para que **git** gestione el nuevo repositorio, si borramos **.git** nuestro directorio volverá a ser un directorio normal sin seguimiento de versiones.

En este punto nuestro proyecto está en seguimiento, **git** tendrá en cuenta todo lo que ocurra a partir de ahora con los archvios contenidos en el directorio.

![git_areas.png](/IMG/Git_areas_02.png "git init")

