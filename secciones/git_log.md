[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git log**

Cada vez que ejecutamos un **commit** guardamos un registro del estado de los archivos del proyecto en ese momemento.    
Esto nos permite volver a ese estado si realizamos cambios inconvenientes en posteriores actualziaciones.

&nbsp;    

Para ver que registros (commits) tenemos guardados en nuestro proyecto utilizaremos el comando `git log`.

Por ejemplo, supongamos que tenemos un proyecto nuevo, en él hemos creado un archivo llamado "hellogit.py" y después hemos ejecutado `git add` + `git commit` con la nota "Este es mi primer commit.".

Si ejecutamos `git log` veremos algo como esto:    
![git_log](/IMG/git_log_01.png "git log")      

&nbsp;    

Esto nos mostrará un identificador de 41 caracteres tras la palabra "**commit**", este código representa a este commit en concreto y podremos utilizarlo más adeltante para interactuar con el.

También veremos el **autor** del commit, la **fecha** en que se hizo y la **nota** adjunta, esta nota es ese texto que tenemos que poner siempre que ejecutamos un **commit**.

---
## **NOTAS:**


## HEAD
Podemos ver al final del registro más reciente la palabra **HEAD** esto se refiere al registro en el que estamos en ese momento, cualquier cambio que hagamos será posterior al lugar donde se encuentre HEAD que puede cambiar si nos interesa. Esto se verá en más detalle en la sección que habla del comando `checkout`. **HEAD** es como el cursor que nos marca donde van a aparecer las letras cuando escribimos en un editor de texto.

## main
Al final del registro podemos encontrar que **HEAD** apunta con una flecha a **main**, este "main" es un nombre por defecto que se le aplica a la rama principal cuando creamos un proyecto nuevo, podemos llamar a esta rama de cualquier otra forma pero donde aparezca su nombre será el extremo más reciente de esa rama, lo mismo se aplica para cualquier otra rama, donde veamos su nombre esa es la punta de la rama.

Si observamos el ejemplo anterior y tenemos en cuenta estos dos conceptos nos encontramos (osea HEAD se encuentra) en la punta de la rama principal "main" y cualquier nuevo commmit se colocará por delante de este punto (de HEAD) y por lo tanto HEAD y main se desplazarán a el. 

---

&nbsp;    

Ahora creamos otro archivo en el mismo directorio que el anterior y le ponemos el nombre “hellogit_2.py”:

![git_log](/IMG/git_log_02.png "git log")

Si ahora ejecutamos otra vez el comando `git status` se nos informará de que nuestro nuevo archivo no está en seguimiento:

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

Si volvemos a ejecutar `git log` ahora aparece este nuevo registro que acabamos de crear con su identificador único:

![git_log](/IMG/git_log_04.png "git log")

&nbsp;    
&nbsp;    

## **Formas de utilizar "git log"**
Esta no es la única forma de ver al salida del comando `git log`, mediante algunos atributos podemos modificar el comando para que nos devuelva una salida más atractiva. En los siguientes ejemplos mostraré algunas formas de formatear el comando `git log`, existen más formas que podemos encontrar en la documentación de git --> https://www.git-scm.com/docs/git-log

&nbsp;    

Si ejecutamos el comando "git log" sin atributos vemos algo como esto:    
![git_log](/IMG/git_log_05.png "git log")

&nbsp;    

Los siguientes son algunos atributos que se pueden añadir al comando `git log`, en solitario o combinados.

&nbsp;    
&nbsp;    

## git log --all
Este comando muestra todos los registros de todas las ramas, sin este atributo solo veríamos los registros de la rama en la que estamos (osea donde se encuentra **HEAD**)


## git log --oneline    
Este comando comprime la salida de `git log` haciendo que ocupe una sola línea, el código abreviado que aparece en cada línea se puede utilizar de la misma forma que utilizaríamos la versión larga.

Ejemplo:     
![git_log](/IMG/git_log_06.png "git log")      


## git log --decorate    
Este comando muestra informacióne extra en los commits, como tags que hayamos creado, información sobre las ramas, etc.


## git log --graph    
Este comando mestra de forma gráfica (en **ASCII**) los cambios que nuestro log ha tenido a lo largo del tiempo en las diferentes ramas.

Ejemplo:     
![git_log](/IMG/git_log_08.png "git log")      

&nbsp;    
&nbsp;    

# **Filtros**

También podemos filtrar la salida para que se muestren solo unos commits concretos.

Por ejemplo:

## POR CANTIDAD:
## git log -[Nº_de_commits]
Muestra la cantidad de commits indicada tras el guión, en orden de más a menos recientes.     
Por ejemplo `git log -3` muestra los tres **commits** mas recientes:     
![git_log](/IMG/git_log_09.png "git log")      

&nbsp;    

## POR FECHA:
## git log --after="[Fecha]"
Muestra los commits posteriores a la fecha indicada tras el atributo "**--after**" y entre comillas. 
Por ejemplo:     
![git_log](/IMG/git_log_10.png "git log")      
--after soporta varios formatos de fecha.

También podemos utilizar la palabra clave "yesterday" para referirnos a todos los commits posteriores al día de ayer:
![git_log](/IMG/git_log_11.png "git log")      


De la misma forma que utilizamos `--after` para hacer referencia a fechas posteriores a la indicada podemos utilizar el atributo `--before` para hacer referencia a fechas anteriores a la indicada, o una combinación de ambos para referirnos a un rango de fechas.

Por ejemplo:     
`git log --after="1-7-2023" --before="1-8-2023"`

&nbsp;    

## POR AUTOR:
## git log --author="[AUTOR]"

Filtra los commits por el usuario que los creo.

También es posible indicar varios autores en este filtro separandolos con una tubería escapada --> `\|`:

Así:
`git log --author="Jack\|Zet"`

&nbsp;    

## POR MENSAJE DE COMMIT:
## git log --grep="Mensaje_de_commit"

Este comando filtra los commits por su mensaje adjunto, si el texto introducido entre las comillas está contenido en algún commit este se mostrará.

![git_log](/IMG/git_log_12.png "git log")     

&nbsp;    

## POR ARCHIVO:
## git log -- [Ruta_de_archivo]

Este comando nos permite buscar los commits que afectaron al archvio indicado, los dobles guines sin nada más indican a git que lo siguiente es una ruta de archivo.

Por ejemplo aquí buscamos todos los commits que afectaron al archivo **git_add.md**:
![git_log](/IMG/git_log_13.png "git log")     
A no ser que estemos en el mismo directorio que el arhibo buscado tendremos que indicar su ruta.

## POR CONTENIDO
## git log -S"Contenido"

Con este comando podemos encontrar el commit concreto en que se agrego cierto contenido a un archivo, por ejemplo si queremos buscar en que commit se añadió a un archivo el string "Hola gente!" el comando sería `git log -S"Hola gente!"`.
Esto se llama **pickaxe** y tiene la forma **-S""**, la cadena buscada va entre las comillas.
