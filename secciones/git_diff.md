[ÍNDICE](https://github.com/JoseFerDel/Guia_Git_GitHub/blob/Zet_main/README.md)

# **git diff**

En algunas ocasiones hemos realizado cambios en alguna parte de nuestra rama pero no estamos seguros de si vale la pena ejecutar un **commit** de estos cambios.

Para estos casos tenemos el comando `git diff` que nos permitirá ver las diferencias entre la última vez que hicimos un commit y el estado actual de nuestros archivos.

Para ver esto tomamos el archivo **hellogit.py**:

```
zet@wukong:~/Escritorio/Hello_Git$ cat hellogit.py 
print("Hello Git! pistachos.")
zet@wukong:~/Escritorio/Hello_Git$ 
zet@wukong:~/Escritorio/Hello_Git$ 
```

Actualmente en el archivo hay una sola línea donde pone: print("Hello Git! pistachos."). En nuestro ejemplo, tras crear el archivo de esta forma habriamos ejecutado un **commit**.

&nbsp;    

```
zet@wukong:~/Escritorio/Hello_Git$ cat hellogit.py 
print("Hello Git! pipas peladas.")
zet@wukong:~/Escritorio/Hello_Git$ 
```
Hemos cambiado la línea anterior por: print("Hello Git! pipas peladas.")

&nbsp;    

Teniendo en cuenta que ya se ejecutó un **commit** con el archivo antes de hacer esta última modificación, podríamos utilizar el comando git diff para ver las diferencias en este archivo desde el último commit:

```
zet@wukong:~/Escritorio/Hello_Git$ git diff
diff --git a/hellogit.py b/hellogit.py
index 25d34fb..0903a39 100644
--- a/hellogit.py
+++ b/hellogit.py
@@ -1 +1 @@
-print("Hello Git! pistachos.")
+print("Hello Git! pipas peladas.")
zet@wukong:~/Escritorio/Hello_Git$ 
```

## Descripción:

> ### diff --git a/hellogit.py b/hellogit.py
Esto nos indica que se va a mostrar las diferencias entre dos versiones del mismo archivo.

> ### @@ -1 +1 @@
Aquí nos está diciendo que ha desaparecido (o sido modificada) una de las líneas de la versión A del archivo y a aparecido una nueva línea en la versión B del archivo, es la forma que tiene git de decirnos que una línea ha sido modificada, si cambias un solo carácter git considera que esa línea ha desaparecido y la nueva versión es  una nueva línea.

> ### -print("Hello Git! pistachos.")     
> ### +print("Hello Git! pipas peladas.")     
Aquí nos dice específicamente que línea ha desparecido y que línea ha sido agregada al archivo.