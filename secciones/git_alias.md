[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git alias**

Los alias en varios entornos donde se necesitan comandos son herrmaientas que nos permiten ejecutar una serie de instrucciones utilizando una instrucción más corta.

Por ejemplo, cuando ejecutamos el comando 'git log' y le añadimos atributos el comando puede llegar a tener un aspecto como este:


## git log --all --graph --decorate --oneline

Si creamos un alias, que sería como un diminutivo de este comando, podemos ejecutar todo eso escribiendo el nombre del alias en lugar de todo el comando.

Por ejemplo, vamos a crear un alias llamado reg que haga lo msimo que escribir `git log --all --graph --decorate --oneline`.

El comando que crea este alias se construye de esta forma:

Empezamos a introducir el comando para modificar la configuración de forma global...

## git config --global 

... justo después indicamos que queremos crear un alias añadiendole la palabra clave **alias** seguida de un punto:

## git config --global alias.

Justo después del punto ponemos el nombre para el alias, en nuestro caso "**reg**" ...

## git config --global alias.reg

... y aquí ponemos un espacio y justo después esribimos entre comillas simples el comando al que se llamará al ejecutar el alias:

## git config --global alias.reg 'log --all --graph --decorate --oneline'

## NOTA:
Al crear el alias no añadiremos la palabra **git** al principio porque la vamos a utilizar para llamar al propio alias.

Y ya estaría, con esto habremos creado el alias “reg” que ejecutará “log --graph --decorate --all --oneline” cada vez que sea ejecutado.     
![git_alias](/IMG/git_alias_01.png "git alias")      


Para borrar un alias creado utilziaremos el atributo `--unset` del comando config:
Así:    
## git config --global --unset alias.reg