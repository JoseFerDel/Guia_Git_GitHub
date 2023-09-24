[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)


# **git commit**

El comando `git commit` 


Para ejecutar un **commit** escribiremos el comando `git commit`, esto nos abrirá un editor de texto con unas líneas precedidas por almohadillas, esto son comentarios y serán ignorados por git, son solo para que lo leamos nosotros, aquí se nos pide que escribamos un mensaje que se adjuntará al commit y se nos advierte que si el mensaje está vacío o solo contiene líneas cn # el commit será ignorado.

Como aquí:     
![git_commit](/IMG/doc_commit.png "git commit")    
En la captura añadimos algún texto, lo que sea, como nota informativa del **commit** y guardamos el archivo, si lo guardamos con algo que no sea un comentario el commit se realizará y tendremos registrados nuestros cambios.

![git_áreas](/IMG/Git_areas_04.png "git add")

Pero para hacerlo más rápido y que no se nos abra ese archivo de texto podemos escribir el mensaje junto con el propio comando “git commit” mediante la opción `-m` seguida del texto del **commit**

Así:
## git commit -m “COMENTARIO”

Ejemplo:    
![git_commit](/IMG/commit_comentario.png "commit comentario")    
El texto del comentario va entre comillas.

Si ahora repetimos el comando `git status` se nos informará de que ya no hay nada pendiente.
```
zet@wukong:~/Escritorio/Hello_Git$ git status
En la rama main
nada para hacer commit, el árbol de trabajo está limpio
zet@wukong:~/Escritorio/Hello_Git$
```
Con esto completaríamos todo el ciclo que nos lleva a guardar un registro de nuestro proyecto en nuestra máquina local, el comando `git push` sirve para subir los cambios a un servidor remoto (GitHUb) y se explicará en la sección de **GitHUb**.

Cada vez que queramos hacer una "foto" de nuestro proyecto repetiremos `git add` y `git commit` y si queremos saber si hay algo pendiente en git ejecutaremos el comando `git status`. Hasta aquí lo básico.
