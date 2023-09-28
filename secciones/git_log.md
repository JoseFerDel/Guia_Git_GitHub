[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git log**

Cada vez que ejecutamos un **commit** guardamos un registro del estado de los archivos del proyecto en ese momemento.    
Esto nos permite volver a ese estado si realizamos cambios inconvenientes en posteriores actualziaciones.

&nbsp;

Para ver que registros (commits) tenemos guardados en nuestro proyecto utilizaremos el comando `git log`

Supongamos que tenemos un proyecto nuevo, en él hemos creado un archivo llamado "hellogit.py" y después hemos ejecutado `git add` + `git commit` con la nota "Este es mi primer commit.".

Si ejecutamos `git log` veremos algo como esto:    
![git_log](/IMG/git_log_01.png "git log")
En este caso solo hay un registro.

&nbsp;

Esto nos mostrará un identificador tras la palabra "commit", este código representa a este commit en concreto y podremos utilizarlo más adeltante para interactuar con el.

También veremos el **autor** del commit, la **fecha** en que se hizo y la **nota** adjunta, esta nota es ese texto que tenemos que poner siempre que ejecutamos un **commit**.

&nbsp;

Ahora creamos otro archivo en el mismo directorio que el anterior y le ponemos el nombre “hellogit_2.py”

![git_log](/IMG/git_log_02.png "git log")

Si ahora ejecutamos otra vez el comando `git status` veremos que se nos informa de que nuestro nuevo archivo no está en seguimiento.

![git_log](/IMG/git_log_03.png "git log")

Así que agregamos el archivo al **AREA STAGE** con el comando `git add` y guardamos el registro del nuevo estado del proyecto con  `git commit`:

```
zet@wukong:~/Escritorio/Hello_Git$ git add hellogit_2.py 
zet@wukong:~/Escritorio/Hello_Git$ 
zet@wukong:~/Escritorio/Hello_Git$ git commit -m "Este es mi segundo commit."
[main 263329a] Este es mi segundo commit.
 1 file changed, 1 insertion(+)
 create mode 100644 hellogit_2.py
zet@wukong:~/Escritorio/Hello_Git$ 
```

Si volvemos a ejecutar `git log`  veremos que ahora aparece este nuevo registro que acabamos de crear con su identificador único.

![git_log](/IMG/git_log_04.png "git log")


## **Formas de utilizar "git log"**

La salida del comando `git log`se puede modificar utilizando algunos atributos.
Aquí muestro una posible forma de formatear la salida de `git log`, es solo un ejemplo, hay mas formas.
    
&nbsp;    

Si ejecutamos el comando "git log" sin atributos vemos lo siguiente:    
![git_log](/IMG/git_log_05.png "git log")

&nbsp;    

Si le agregamos el atributo `--graph` el comando quedará así:
## git log --graph    
![git_log](/IMG/git_log_06.png "git log")
Esto hace aparecer una línea a la izquierda de los logs que representa la forma de las ramas de nuestro proyecto, en este caso solo hay una rama.

&nbsp;    

Si a esto le añadimos el atributo `--pretty=oneline` el comando quedará así:
## git log --graph --pretty=oneline
![git_log](/IMG/git_log_07.png "git log")
Ahora a `graph` le hemos añadido `--pretty=oneline` que hace que el texto se vea más bonito y con cada registro en una sola línea, a costa de mostrar menos información por registro.


## **Otras formas de mostrar el log:**

## git log --oneline
![git_log](/IMG/git_log_09.png "git log")
Con `--oneline` se nos muestra una versión compactada del log donde veremos los 7 primeros carácteres del código de cada commit y su nota.




