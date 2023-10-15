[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git merge**

El comando merge nos permite importar el estado de una rama a otra para que está segunda tenga los datos de los dos.
La finalidad de tener varias ramas es que varios flujos de trabajo existan a la vez pero en algún momento querremos ver toda la obra junta, para esto utilizaremos git merge.
Para ver como funciona vamos a preparar una nueva zona de pruebas.

## Preparando la practica:

Para probar el comando merge vamos a crear un nuevo proyecto en un directorio nuevo.

primero nos desplazamos al nuevo directorio del proyecto, en este caso se llamará **merge_test**:
``` 
zet@wukong:~/Escritorio/merge_test$ ls -lA
total 0
zet@wukong:~/Escritorio/merge_test$
```   

&nbsp;    

### git init

Mediante el comando `git init` iniciamos el repositorio:
```   
zet@wukong:~/Escritorio/merge_test$ git init
ayuda: Usando 'master' como el nombre de la rama inicial. Este nombre de rama predeterminado
ayuda: está sujeto a cambios. Para configurar el nombre de la rama inicial para usar en todos
ayuda: de sus nuevos repositorios, reprimiendo esta advertencia, llama a:
ayuda: 
ayuda:  git config --global init.defaultBranch <nombre>
ayuda: 
ayuda: Los nombres comúnmente elegidos en lugar de 'master' son 'main', 'trunk' y
ayuda: 'development'. Se puede cambiar el nombre de la rama recién creada mediante este comando:
ayuda: 
ayuda:  git branch -m <nombre>
Inicializado repositorio Git vacío en /home/zet/Escritorio/merge_test/.git/
zet@wukong:~/Escritorio/merge_test$ 
``` 

Ahora cambiamos el nombre de la rama principal (**master**) por otro nombre, por ejemplo **mtest**, esta parte es opcional.

&nbsp;    

### git branch -m mtest

```
zet@wukong:~/Escritorio/merge_test$ git branch -m mtest
zet@wukong:~/Escritorio/merge_test$ 
``` 

Podemos ver el resultado si ejecutamos el comando `git status`:

``` 
zet@wukong:~/Escritorio/merge_test$ git status
En la rama mtest

No hay commits todavía

no hay nada para confirmar (crea/copia archivos y usa "git add" para hacerles seguimiento)
zet@wukong:~/Escritorio/merge_test$ 
```  

Con esto ya tenemos el nuevo proyecto funcionando con control de versiones **Git**.

&nbsp;    

Ahora vamos a crear unos archivos y commits para que la rama principal tengo algo de contenido.

![git_merge](/IMG/git_merge_01.png "git merge")      

&nbsp;    

Para facilitar la tarea crearemos un alias con un comando que muestre el log de forma mas atractiva.

Un alias para mostrar el log de todas las ramas (treeall):
### git config --global alias.treeall 'log --graph --decorate --all --oneline'

Y otro para mostrar solo el log de la rama actual en la que estamos (tree):
### git config --global alias.tree 'log --graph --decorate --oneline'

``` 
zet@wukong:~/Escritorio/merge_test$ git config --global alias.treeall 'log --graph --decorate --all --oneline'
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ git config --global alias.tree 'log --graph --decorate --oneline'
zet@wukong:~/Escritorio/merge_test$
``` 

Los alias sirven para todos los proyectos que tengamos, no solo para este en concreto.

&nbsp;    

Mientras solo tengamos una rama bastará con utilizar git tree para ver los registros del proyecto:

![git_merge](/IMG/git_merge_02.png "git merge")      


Aquí podemos ver 3 commits referentes a la creación de 3 archivos, vemos que el **HEAD** se encuentra en el último commit y que este además es el final de la rama **mtest**.

Con esto ya tenemos los preparativos, ahora vamos a crear una rama nueva llamada **mrama**.

Como de momento no hay commits en la nueva rama no hay diferencia ente utilizar nuestro alias `tree` o el `treeall`, en ambos podemos ver que ahora el registro `337468e` es el final de ambas ramas.

![git_merge](/IMG/git_merge_03.png "git merge")      

Creamos la nueva rama, llamada **mrama**, con el comando `git branch mrama`.

Vamos a cambiar a la nueva rama **mrama** y cambiar algunas cosas:

``` 
zet@wukong:~/Escritorio/merge_test$ git switch mrama
M       file_2
Cambiado a rama 'mrama'
zet@wukong:~/Escritorio/merge_test$ 
``` 

Primero modificaremos el contenido de **file_2**:

``` 
zet@wukong:~/Escritorio/merge_test$ ls
file_1  file_2  file_3
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ cat file_2
Merge test 2
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ echo "Merge test versión 2" > file_2
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ cat file_2
Merge test versión 2
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ 
``` 


Después añadiremos contenido, sin modificar el existente, en **file_3**:

``` 
zet@wukong:~/Escritorio/merge_test$ ls
file_1  file_2  file_3
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ cat file_3
Merge test 3
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ echo "Añado contenido a file_3" >> file_3
zet@wukong:~/Escritorio/merge_test$ 
zet@wukong:~/Escritorio/merge_test$ cat file_3
Merge test 3
Añado contenido a file_3
zet@wukong:~/Escritorio/merge_test$ 
``` 

Además vamos a borrar **file_1**:

``` 
zet@wukong:~/Escritorio/merge_test$ rm file_1 
zet@wukong:~/Escritorio/merge_test$ 
``` 

Si ejecutamos `git status` se nos informa de que tenemos cambios por agregar a la zona stage:

![git_merge](/IMG/git_merge_04.png "git merge")      

Ejecutamos `git add .` para agregar todas las modificaciones a STAGE y después ejecutamos un commit para registrar estos cambios:

![git_merge](/IMG/git_merge_05.png "git merge")      

Con esto el terreno de pruebas queda preparado.

Ahora cambiamos a la rama principal **mtest** y desde aquí ejecutamos los alias tree y treeall, vemos que que solo vemos la nueva rama al ejecutar el segundo.

![git_merge](/IMG/git_merge_06.png "git merge")      

Podemos ver que en la rama principal **mtest** no se refleja ninguno de los cambios realizados en la nueva rama **mrama**:

![git_merge](/IMG/git_merge_07.png "git merge")      

Para ampliar más la zona de pruebas voy a crear otro commit en la rama principal que será posterior en el tiempo a los commits que acabamos de hacer en la rama secundaria:

![git_merge](/IMG/git_merge_08.png "git merge")      

Además, para que el proyecto tenga más contenido voy a crear otro commit en la rama secundaria:

![git_merge](/IMG/git_merge_09.png "git merge")      

## Comando merge

Hecho esto ya podemos probar el comando `merge`, en este punto ambas ramas tiene diferentes documentos y difernte contenido en estos, con merge deberíamos poder unir todas las modificaciones en una sola rama:

La sintaxis del comando merge es la siguiente:

### git merge [rama cuyos datos queremos importar para mezclar]

Desde la rama secundaria “mrama” vamos a importar los datos que tenga la rama principal "mtest" para mezclalos con los de “mrama”.

![git_merge](/IMG/git_merge_10.png "git merge")      

En este ejemplo se ha ignorado pero el sistema te va a pedir que hagas un commit al mismo tiempo que ejecutas un merge, con el comando `git merge -m “Comantario commit"` podemos hacerlo.

Ahora el **log** nos muestra que las dos ramas se unen en un  commit automatico que se ha creado, porque no hemos puesto nungún texto por nuestra cuenta, **mrama** contiene ahora todos los datos de ambas ramas combinados.


![git_merge](/IMG/git_merge_11.png "git merge")      

![git_merge](/IMG/git_merge_12.png "git merge")      
