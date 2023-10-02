[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)



# **git checkout**

Con el comando `git checkout` podemos volver a cualquier versión gurdada de las que se muestran con el comando `git log` para ello utizaremos el comando con la siguiente sintaxis:


> # git checkout ID_COMMIT


Para ver como funciona veamos este directorio donde se encuentra un archivo llamado "**git_checkout.md**":     

![git_checkout](/IMG/git_checkout_01.png "Archivo")      

&nbsp; 

Ahora mostramos la versión comprimida del log de los 3 últimos registros con el comando `git log -3 --oneline`:     
![git_checkout](/IMG/git_checkout_02.png "Archivo")      

&nbsp; 

Veremos que según la nota del commit con código `47030e2` ahí es donde se creo el archivo.

Si en un momento dado consideramos que fue un error haber creado ese archivo podemos volver atrás en el tiepo en nuestro proyecto al momento en que ese archivo aún no había sido creado, para ello utilizaremos el comando `git checkout` para desplazarnos (desplazar el HEAD) al commit anterior a la creación de ese archivo que tiene el identificador `5febbab`.

Así:     
![git_checkout](/IMG/git_checkout_03.png "Archivo")      

&nbsp; 

Si volvemos a comprobar el contenido de nuestro directorio vemos que ahora el archivo "git_checkout.md" no existe, estamos en un registro anterior y todo está como en el momento en que hicimos ese commit, tanto en lo que respecta al contenido de los archivos a su existencia:
![git_checkout](/IMG/git_checkout_04.png "Archivo")      

&nbsp; 

Esto ha provocado que HEAD y la punta de nuestra rama ya no estén sincronizadas, están en posiciones diferentes, podemos comprobar esto con el comando `git branch` que nos informará de la rama en la que nos encontramos:
Mover el HEAD a otro registro provoca que 
![git_checkout](/IMG/git_checkout_05.png "Archivo")      
En este caso se ha generado una rama nueva sin nombre desde la nueva posición de HEAD, si ahora hicieramos nuevos commits desde aquí estos crecerían desde este punto.

&nbsp; 