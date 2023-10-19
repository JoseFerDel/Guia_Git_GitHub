[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git stash**

Si, mientras estamos editando un archivo en una rama, antes de terminar la edición y hacer un commit, intentamos cambiar de rama se nos advertirá de que todavía tenemos algo sin confirmar, sin hacer commit en el, y no se nos permitirá cambiar de rama.

![git_stash](/IMG/git_stash_01.png "git stash")      

por ejemplo, aquí editamos el archivo **nota.txt** en la rama llamada **mrama** y después intentamos camiar de rama sin hacer commit de los cambios, **git** no nos deja hacerlo.

&nbsp;    

Para poder cambiar a otra rama sin confirmar los cambios en la rama en la que estamos, tal vez porque todavía no hemos terminado, podemos utilizar el comando `stash`, que guardará temporalmente los cambios que hemos hecho sin que sea necesario hacer commit.

![git_stash](/IMG/git_stash_02.png "git stash")      

&nbsp;    

Y ahora si, nos deja cambiar de rama:

![git_stash](/IMG/git_stash_03.png "git stash")      

Con esto podríamos pausar temporalmente nuestro trabajo incompleto en una rama para trabajar en otra cosa que se encuentre en una rama diferente.

&nbsp;    
&nbsp;    

## git stash list

Con este comando podemos ver que **stash** hay guardados.

![git_stash](/IMG/git_stash_04.png "git stash")      

Se nos indica la rama donde se ha hecho el stash y el último commit que había en el momento de hacer la edición.

&nbsp;    

Si volvemos a la rama **mrama** y comprobamos el contenido del archivo **nota.txt**, al cual le cambiamos el texto de “*Datos datos datos*” a “*Nuevo contenido*” antes de ejecutar el **stash**, veremos que el contenido del archivo sigue siendo el que tiene almacenado en el último commit, el texto “Datos datos datos”.

![git_stash](/IMG/git_stash_05.png "git stash")      

&nbsp;    
&nbsp;    

## git stash pop

Con este comando recuperamos los contenidos guardados con stash para que todo vuelva a estar como cuando lo dejamos la última vez, así tendremos todas las ediciones no guardads en el **commit** en el que estamos:

![git_stash](/IMG/git_stash_06.png "git stash")      

&nbsp;    

Ahora solo tendríamos que agregar los archivos modificados a STAGE y hacer un commit para que todo quede en orden.

![git_stash](/IMG/git_stash_07.png "git stash")      

&nbsp;    

Tras recuperar los datos del **stash** con el comando `git stash pop` los stash que gurdamos quedan eliminados y no aparecerá nada al ejecutar `git stash list`.

![git_stash](/IMG/git_stash_08.png "git stash")      

&nbsp;    
&nbsp;    

## git stash drop

Con este comando eliminaremos los **stash** existentes sin hacer nada con ellos.

![git_stash](/IMG/git_stash_09.png "git stash")      








