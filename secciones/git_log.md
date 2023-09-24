[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git log**

Cada vez que ejecutamos un **commit** guardamos un registro del estado de los archivos en ese momemento, esto nos permite volver a ese estado si realizamos cambios inconvenientes de forma sencilla.

&nbsp;

Para ver que registros (commits) tenemos guardados en nuestro proyecto utilizaremos el comando `git log`

Sipongamos que tenemos un proyecto nuevo, en el hemos creado un archivo llamado "hellogit.py" y después hemos hecho un commit con la nota "Este es mi primer commit.", si ejecutamos git log veremos esto:

![git_log](/IMG/git_log_01.png "git log")

Esto nos mostrará un identificador tras la palabra commit, este código representa a este commit en concreto y podremos utilizarlo más adeltante para interactuar con el.

También veremos el **autor** de commit, la **fecha** en que se hizo y la **nota** adjunta, el texto que tenemos que poner siempre que ejecutamos un **commit**.

Ahora creamos otro archivo en el mismo directorio que el anterior y le ponemos el nombre “hellogit_2.py”

![git_log](/IMG/git_log_02.png "git log")

Si ahora ejecutamos otra vez el comando `git status` veremos que se nos informa de que nuestro nuevo archivo no está en seguimiento.

![git_log](/IMG/git_log_03.png "git log")


Aquí agregamos el archivo al **AREA STAGE** con el comando "git add" y guardamos el registro del nuevo estado del proyecto con  “git commit”:
```
zet@wukong:~/Escritorio/Hello_Git$ git add hellogit_2.py 
zet@wukong:~/Escritorio/Hello_Git$ 
zet@wukong:~/Escritorio/Hello_Git$ git commit -m "Este es mi segundo commit."
[main 263329a] Este es mi segundo commit.
 1 file changed, 1 insertion(+)
 create mode 100644 hellogit_2.py
zet@wukong:~/Escritorio/Hello_Git$ 
```

Si volvemos a ejecutar `git log`  veremos que ahora aparece este nuevo registro que acabamos de crear con su dientificador único.

![git_log](/IMG/git_log_04.png "git log")