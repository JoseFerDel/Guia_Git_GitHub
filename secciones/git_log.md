[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git log**

Cada vez que ejecutamos un **commit** guardamos un registro del estado de los archivos del proyecto en ese momemento.    
Esto nos permite volver a ese estado si realizamos cambios inconvenientes en posteriores actualziaciones.

&nbsp;    

Para ver que registros (commits) tenemos guardados en nuestro proyecto utilizaremos el comando `git log`

por ejemplo, supongamos que tenemos un proyecto nuevo, en él hemos creado un archivo llamado "hellogit.py" y después hemos ejecutado `git add` + `git commit` con la nota "Este es mi primer commit.".

Si ejecutamos `git log` veremos algo como esto:    
![git_log](/IMG/git_log_01.png "git log")      
En este caso solo hay un registro.

&nbsp;    

Esto nos mostrará un identificador tras la palabra "**commit**", este código representa a este commit en concreto y podremos utilizarlo más adeltante para interactuar con el.

También veremos el **autor** del commit, la **fecha** en que se hizo y la **nota** adjunta, esta nota es ese texto que tenemos que poner siempre que ejecutamos un **commit**.

&nbsp;    

Ahora creamos otro archivo en el mismo directorio que el anterior y le ponemos el nombre “hellogit_2.py”

![git_log](/IMG/git_log_02.png "git log")

Si ahora ejecutamos otra vez el comando `git status` se nos informará de que nuestro nuevo archivo no está en seguimiento.

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

&nbsp;    

Si volvemos a ejecutar `git log` ahora aparece este nuevo registro que acabamos de crear con su identificador único.

![git_log](/IMG/git_log_04.png "git log")

&nbsp;    
&nbsp;    

## **Formas de utilizar "git log"**
Esta no es la única forma de ver al salida del comando 'git log', mediante algunos atrubutos podemos modificar el comando para que nos devuelva una salida más atractiva.    

Aquí muestro una posible forma de formatear la salida de `git log`, es solo un ejemplo, hay mas formas.     
&nbsp;    

Si ejecutamos el comando "git log" sin atributos vemos algo como esto:    
![git_log](/IMG/git_log_05.png "git log")

&nbsp;    

Los siguientes son algunos atributos que se pueden añadir al comando `git log`, en solitario o combinados.

&nbsp;    
&nbsp;    

## git log --oneline    
Este comando comprime la salida de `git log` haciendo que ocupe una sola línea, el código abreviado que aparece en cada línea se puede utilizar de la misma forma que utilizaríamos la versión larga.

Ejemplo:     
![git_log](/IMG/git_log_06.png "git log")      



Si le agregamos el atributo `--graph` el comando quedará así:
## git log --graph    
![git_log](/IMG/git_log_20.png "git log")      
Esto hace aparecer una línea a la izquierda de los logs que trata de representar con caracteres la forma de las ramas de nuestro proyecto, en este caso solo hay una rama.

&nbsp;    


