[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git reset**

Primero hablaré de `git reset` y la diferencia con `git checkout` para que quede claro.
Puede parecer que los comandos `git checkout` y `git reset` hacen lo mismo, la diferencia principal es que `git checkout` nos permite mover solamente el **HEAD**, el puntero donde estamos trabajando actualmente, manteniendo el registro intacto mientras que `git reset` mueve tanto el **HEAD** como el **main** (o como se llame la rama en cada caso) y nos permite realizar cambios en el registro.

&nbsp;    

Para entender bien esta parte vamos a recordar los diferentes estados que puede tener nuestro proyecto en un momento dado.

Creamos un archivo en nuestro proyecto, este archivo no existía antes así que al ejecutar `git status` se nos informara de que este archivo no está en seguimiento y deberemos ejecutar `git add` para que que los posteriores commits le afecten.

Si ejecutamos el comando `git add` sobre el nuevo archivo este pasa a estar en seguimiento y cualquier cambio que realicemos al archivo será susceptible de ser registrado, como hacerle una foto en el estado en que se encuentra en ese momento, esto se hará mediante el comando `git commit`. Para poder utilizar `git commit` el archivo debe haber sido agregado antes a la zona stage mediante el comando `git add`.

Habiendo dejado esto claro pasamos a explicar que hacen los modos de **git reset**:

La secuencia básica para que registrar cambios en una archivo sería esta:
## Modificación / Creación →  git add  → git commit

&nbsp;    

## git reset tiene 3 modos:


* ### Soft Reset 
**git reset --soft CÓDIGO_DEL_COMMIT:**      
		Mueve la rama actual (master, main, o lo que sea) y el "HEAD" al commit especificado, pero mantiene los cambios de los commits posteriores en el área de preparación.
		Si están en el area de preparación no tendremos que ejecutar `git add` otra vez con esos archivos para que vuelvan a estar en seguimiento, solo se habrán desehcho los commits posteriores.


* ### Mixed Reset 
**git reset --mixed CÓDIGO_DEL_COMMIT:**     
		Mueve la rama actual (master, main, o lo que sea) y el "HEAD" al commit especificado, restablece el área de preparación, pero conserva los cambios en el árbol de trabajo (osea los archivos se quedan igual).
		En este caso los commits posteriores estan en el area de preparación, por lo que no es necesario volver a ejecutar “git add” pero se han perdido sus commits posteriores al punto donde nos hemos movido, esos archivos siguen ahí pero tendremos que volver a ejecutar `git commit`para que los cambios vuelvan a estar registrados.
		Esta es la opción por defecto de git reset así que no es necesario poner --mixed al final.

* ### Hard Reset 
**git reset --hard CÓDIGO_DEL_COMMIT:**      
		Mueve la rama actual (master, main, o lo que sea) y el "HEAD" al commit especificado, restablece el área de preparación y el árbol de trabajo, eliminando todos los cambios de los commits posteriores.
		Aquí también nos movemos al registro especificado pero se elimina todo lo creado posteriormente, cualquier archivo o cambio posterior desaparecerá y no podremos recuperarlos de forma normal (existe alguna forma pero ya es una operación de rescate, git borrará definitivamente estos archivos de su “papelera” pasado un tiempo o si necesita espacio. Lo que hace `git reset --hard` es retroceder en el tiempo completamente.

&nbsp;    
&nbsp;    

Veamos un ejemplo de un **reset hard**:

Si ejecutamos el comando `git log --oneline` veremos los registros que tenemos antes del reset hard:    
![git_reset](/IMG/git_reset_02.png "git reset")      
Vemos que tenemos 5 registros.

Ahora, mediante el comando `git reset --hard` vamos a movernos al segundo registro, en donde pone “Este es mi segundo commit.”, como es un **resert hard** todo lo posterior, registros y archivos creados después del punto al que vamos a movernos, desaparecerá.

Para hacerlo pondremos el **ID del commit** al que queremos cambiar después del comando, en este caso sería el ID `263329a`:

Así:
## git reset --hard 263329a    
![git_reset](/IMG/git_reset_03.png "git reset")      

Si tras el reset volvemos a ejecutar el comando `git log --oneline` veremos que han desaparecido los registros posteriores al punto desde donde hemos hecho el reset:     
![git_reset](/IMG/git_reset_04.png "git reset")      

&nbsp;    
&nbsp;    

Aunque he mencionado que los registros posteriores desaparecen esto solo es en apariencia.    
Si ejecutamos un `git log` con el atributo `--all` veremos todos lo registros en todas las ramas, incluidos los que se han eliminado, que en realidad están guardados temporalmente.     
![git_reset](/IMG/git_reset_05.png "git reset")      

Repitiendo un `git reset --hard` sobre uno de los registros desaparecidos restauraríamos la rama hasta ese punto, `git reset hard` sirve tanto para **eliminar registros** como para **restaurarlos**.

Restauremos la rama para volver tener todos los registros que teníamos al principio, para ello ejecutaremos `git reset --hard` sobre el ID del commit que corresponda, en este caso el `eb21565`, el que erá el más reciente antes de hacer el reset.     
![git_reset](/IMG/git_reset_06.png "git reset")      


Otro `git log` nos mostrará que volvemos a tener todos los commits como al principio.    
![git_reset](/IMG/git_reset_07.png "git reset")      
Los registros que habían desaparecido han vuelto, igual que cualquier archivo que también hubiese desaparecido.


> ## NOTA: 
> Si hemos estado utilizando `git reset --hard` es posible que **HEAD** haya quedado en un estado conocido como “**Desacoplado**”, esto lo podemos ver ejecutando “git status”, significa que **HEAD** ya no se mueve junto con **main**, si ocurre esto veremos que **HEAD** avanza con los nuevos commits mientras que el nombre de la rama, en este caso “main” sigue en el mismo sitio aunque sigamos haciendo más commits, porque sigue siendo ese el verdadero final de la rama main.     
> ![git_tag](/IMG/git_reset_08.png "git log")      

> **Dos posibles soluciones:**    
>> 1. Ignoramos los nuevos commits desacoplados y ejecutamos `git checkout main` para volver al verdadero final de la rama donde podremos crear nuevos commits.
>> 2. Si los **commits** desacoplados son importatens podemos crear una nueva rama con ellos ejecutando `git branch tmp` mientras estamos en la rama desacoplada sin nombre, "tmp" es un nombre cualquiera que le damos a la rama, después ejecutar "git checkout main" para volver a la rama principal y desde aquí ejecutamos `git merge tmp` para combinar el contenido de la rama **tmp** con nuestra rama principal **main**.
