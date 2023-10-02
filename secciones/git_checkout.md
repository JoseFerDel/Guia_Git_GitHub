[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)



# **git checkout**

Con el comando `git checkout` podemos volver a cualquier versión gurdada de las que se muestran con el comando `git log` para ello utizaremos el comando con la siguiente sintaxis:


> # git checkout ID_COMMIT


Para ver como funciona veamos este directorio donde se encuentra un archivo llamado "**git_checkout.md**":     

![git_checkout](/IMG/git_checkout_01.png "Archivo")      


Ahora mostramos la versión comprimida del log de los 3 últimos registros con el comando `git log -3 --oneline`:     
![git_checkout](/IMG/git_checkout_02.png "Archivo")      

Veremos que según la nota del penúltimo commit ahí es donde se creo el archivo. El código de este commit es `47030e2`

Si en un momento dado consideramos que fue un error haber creado ese archivo podemos volver atrás en el tiepo al momento en que ese archivo aún no había sido creado, para ello utilizaremos el comando `git checkout` para desplazarnos (desplazar el HEAD) al commit anterior a la creación de ese archivo que tiene el identificador `5febbab`.

Así: