

# **Configuración inicial**

Para configurar **Git** introduciremos el comando `git config` seguido del nivel al que va a afectar dicha configuración (solo para el usuario actual, para todos, solo para un proyecto concreto, etc).

Para empezar vamos a modificar la configuración a nivel global con el siguiente comando:     
`git config --global`

Al hacer esto se nos indicará que tenemos que agregar alguna opción entre las siguientes para modificar su configuración, el comando está incompleto.

```
zet@wukong:~/Escritorio/Hello_Git$ git config --global  
uso: git config [<opciones>] 
 
Ubicación del archivo de configuración 
    --global              usar archivo de config global 
    --system              usar archivo de config del sistema 
    --local               usar archivo de config del repositorio 
    --worktree            usar archivo de config del árbol de trabajo 
    -f, --file <archivo>  usar archivo de config especificado 
    --blob <blob-id>      leer config del objeto blob suministrado 
 
Acción 
    --get                 obtener valor: nombre [patrón de valor] 
    --get-all             obtener todos los valores: clave [patrón de valor] 
    --get-regexp          obtener valores para regexp: name-regex [value-pattern] 
    --get-urlmatch        obtener valor específico para el URL: sección[.var] URL 
    --replace-all         reemplazar todas las variables coincidentes: nombre valor [valor-patrón] 
    --add                 agregar nueva variable: nombre valor 
    --unset               eliminar una variable: nombre [patrón de valor] 
    --unset-all           eliminar todas las coincidencias: nombre [patrón de valor] 
    --rename-section      renombrar sección: nombre-viejo nombre-nuevo 
    --remove-section      borrar una sección: nombre 
    -l, --list            listar todo 
    --fixed-value         usar la igualdad de cadenas al comparar valores con 'patrón de valor' 
    -e, --edit            abrir el editor 
    --get-color           encontrar el color configurado: slot [default] 
    --get-colorbool       encontrar las opciones del color: slot [stdout-es-tty] 
 
Tipo 
    -t, --type <tipo>     al valor se ha dado este tipo 
    --bool                valor es "true" o "false" 
    --int                 valor es un número decimal 
    --bool-or-int         valor es --bool o --int 
    --bool-or-str         el valor es --bool o cadena 
    --path                valor es una ruta (archivo o nombre de directorio) 
    --expiry-date         valor es una fecha de caducidad 
 
Otro 
    -z, --null            terminar valores con un byte NULL 
    --name-only           mostrar solo nombres de variables 
    --includes            respetar directivas include en la búsqueda 
    --show-origin         mostrar el origen de configuración (archivo, stdin, blob, línea de comandos) 
    --show-scope          mostrar el scope de la configuración (worktree, local, global, system, command) 
    --default <valor>     con --get, usar el valor por defecto cuando falta una entrada
``` 

Esto nos está indicando que el comando está incompleto y nos sugiere una lista de opciones a añadir para completarlo.


En los siguientes pasos añadiremos alguna de estas opciones para configurar nuestro Git.


## **Cambiar (o establecer) nombre de usuario:**

Utilizaremos la siguiente sintaxis para establecer nuestro nombre de usuario:
```   
git config --global user.name “NOMBRE”
``` 

Por ejemplo así asignariamos el nombre de usuario "Zet":
```
zet@wukong:~/Escritorio/Hello_Git$ git config --global user.name "Zet"
zet@wukong:~/Escritorio/Hello_Git$
```
Vemos que no da ningún error, el nombre se ha establecido.

Esta modificación creará un archivo oculto en el directorio HOME del usuario llamado **.gitconfig**:    
![gitconfig](/IMG/gitconfig.jpg ".gitconfig")

Si analizamos el contenido de este archivo veremos que dentro se encuentra la configuración que hemos realizado:
```
zet@wukong:~$  
zet@wukong:~$ cat .gitconfig  
[user] 
        name = Zet 
zet@wukong:~$
```
## **Cambiar (o establecer) email de usuario:**

El comando para establecer nuestro mail de usuario en Git tiene esta sintaxis:    
`git config --global user.email “CORREO ELECTRONICO”`


Si introducimos el comando correctamente podremos volver a examinar el archivo **.gitconfig** donde ahora veremos el mail:

```
zet@wukong:~$ git config --global user.email "zetmail@duck.com"
zet@wukong:~$ 
zet@wukong:~$ cat .gitconfig 
[user]
        name = Zet
        email = fakemail@duck.com
zet@wukong:~$ 
zet@wukong:~$ 
```

Estas dos configuraciones, el usuario y el mail, son lo mínimo que necesitamos para empezar a trabajar con Git.

Otra forma de comprobar que usuario y mail tenemos configurado en nuestor git es ejecutar el siguiente comando:

`git config --global --list'`

```
zet@wukong:~/cosas/Proyectos_GITHUB/Guia_Git_GitHub$ git config --global --list
alias.arbol=log --graph --decorate --all --oneline
alias.treeall=log --graph --decorate --all --oneline
alias.tree=log --graph --decorate --oneline
alias.subir=push -u origin Zet_main
user.email=fakemail@duck.com
user.name=Zet
zet@wukong:~/cosas/Proyectos_GITHUB/Guia_Git_GitHub$ 
```
Esto nos mostrará información sobre nuestro git local como alias configurados o nuestro usuario y mail.








