[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **.gitignore**

En ocasiones podemos tener archivos dentro de nuestro directorio de proyecto que no queremos tener en seguimiento, estos siguen estando en ese directorio por la razón que sea y se nos va a recordar que no hemos ejecutado `git add` con ellos cada vez que ejecutemos `git status`

Por ejemplo, supongamos que tenemos un archivo en el directorio de nuestro proyecto llamado "lista_compra.txt", aunque necesitamos este archivo no queremos que se incluya en el repositorio como un arhcivo más, queremos ignorarlo.     
![gitignore](/IMG/gitignore_01.png ".gitignore")      


**.gitignore** es un archivo oculto que añadimos dentro del directorio de nuestro proyecto donde añadimos instrucciones para ciertos archivos concretos que pueden encontrase en el.

Para que funcione crearemos el archivo .gitignore dentro del directorio de nuestro proyecto y dentro escribiremos `**/` seguido del nomrbe del arhivo que queremos ignorar (sin la ruta). Hay varias sintaxis para introducir instrucciones dentro de este archivo, esta en concreto nos servirá para ignorar archivos:     
![gitignore](/IMG/gitignore_02.png ".gitignore")      
El archivo .gitignore contiene una sola línea en la que pone ****/lista_compra.txt**

Si tras colocar el nombre del archivo a ignorar dentro de .gitignore ejecutamos `git status` veremos lo siguiente:     
![gitignore](/IMG/gitignore_03.png ".gitignore")      
El archivo **lista_compra.txt** ya no aparece, ni aparecerá cualquier otro archivo con ese nombre que por lo que sea se cree dentro del directorio de trabajo.

Lo que si aparece es el archivo `.gitignore` que hemos creado, este si es un archivo importante que queremos tener al día, así que este si lo añadiremos con `git add` y lo pasaremos a seguimiento con `git commit`.     
![gitignore](/IMG/gitignore_04.png ".gitignore")      


Y ahora si, si ejecutamos `git status` ya no tenemos nada pendiente:    
![gitignore](/IMG/gitignore_05.png ".gitignore")      