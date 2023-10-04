[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git tag**

Un **tag** en git es un forma de ponerle una etiqueta a un **commit** en concreto, por ejemplo para indicar que hasta ese punto es la versión 1 o cualquier cosa que nos ayude a entender mejor los registros.

Para agregar un nuevo tag nos desplazaremos al commit deseado (moveremos el HEAD), y allí ejecutaremos el siguiente comando:

## git tag NOMBRE_DEL_TAG

&nbsp;    
&nbsp;    

Para el siguiente ejemplo crearemos un tag en el último **commit**, osea donde aparece el nombre de la rama, que en este caso es "main". Llamaremos a ese tag **cosa_1**.     
![git_tag](/IMG/git_tag_01.png "git log")      
Por convención se espera que los tags sean escritos en minúsculas y sin espacios.

&nbsp;    

En el siguiente ejemplo creamos dos commits nuevos tras haber creado el tag **"cosa_1"**, vemos que el tag permanece en donde lo pusimos mientras que **HEAD** y **main** avanzan.    
![git_tag](/IMG/git_tag_02.png "git log")     

&nbsp;    

Para ver los tags existentes ejecutaremos el comando:    
## git tag     
![git_tag](/IMG/git_tag_04.png "git log")      

&nbsp;    

Para desplazarnos a un tag en concreto también utilizaremos `git checkout` con la siguiente sintaxis:

## git checkout tags/NOMBRE_TAG.

Ejemplo, pasamos del final de la rama a la posición del tag “cosa_1”:    
![git_tag](/IMG/git_tag_05.png "git log")      

&nbsp;    

Podemos ver que el **HEAD** se ha desplazado a la posición de tag indicado:
![git_tag](/IMG/git_tag_06.png "git log")      

Para volver a la parte final de la rama ejecutaremos `git checkout main`.