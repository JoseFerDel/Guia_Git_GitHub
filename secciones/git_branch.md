[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git branch**

El comando branch nos permite crear una nueva rama en nuestro proyecto, esta será independiente de la rama principal.

Supongamos que nuestro proyecto es una aplicación y queremos empezar a trabajar en la funcionalidad de inicio de sesión, un login.

Crearemos una rama llamada **login** de la siguiente forma:
## git branch login

![git_branch](/IMG/git_branch_01.png "git brnach")      

Al hacer esto vemos que ahora **HEAD** se encuentra al final de la rama **main**, la flecha de **HEAD** apunta a main, también vemos que en ese mismo commit se encuentra el final de la nueva rama **login** que parte desde el punto donde nos encontrábamos al crearla.

Si quisiéramos cambiar a la rama **login**, utilizaríamos en este caso el comando switch de esta forma:
## git switch login

![git_branch](/IMG/git_branch_02.png "git brnach")      
Ahora estamos en la rama login, cosa que podemos comprobar ejecutando git log y viendo que la flecha de HEAD apunta a la rama con nombre login.

Si en este punto cambiamos otra vez a la rama main (con el comando git switch main), hacemos cambios y luego hacemos otro commit veremos, al ejecutar git log, que no hay nada referente a la rama login, cada rama es independiente de las demás aunque login parte de uno de los commits de la rama main.

![git_branch](/IMG/git_branch_03.png "git brnach")      

Para ver el contenido de todas las ramas añadiremos al comando “git log --oneline” el atributo "--all"     
![git_branch](/IMG/git_branch_04.png "git brnach")      
Con esto vemos todos los commits de todas las ramas y podemos utilizar sus IDs para navegar entre ellos.

Ahora volvemos a la rama login y hacemos cambios y añadimos otro commit, vemos que el commit que hemos antes en la rama login no aparece, la rama login está formada por todo lo había en el momento de su creación y cualquier commit posterior que hagamos desde ella.

![git_branch](/IMG/git_branch_04.png "git brnach")      


