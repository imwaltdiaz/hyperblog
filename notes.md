# Introduccion a Git

## ¿Por qué usar un sistema de control de versiones como Git?

Guardan pequeños cambios, donde ocurrieron, quien los hizo

```
$ git init 
$ git add biografia.txt
$ git commit -m "versión 1"
```

Con esto la base de datos de control sabe que se inició, que hay un documento llamado biografia.txt, y commit envía los últimos cambios del archivo a la base de datos

Todavía no tienes guardado los cambios en la base de datos, lo haces con 

```
$ git add .
```

Lo haces con todos los archivos, y al final son añadidos, vuelves a hacer un commit

```
$git commit -m "cambios a v1"
$git status
$git show
```

Con git status verás el estado del documento, y show con todo los cambios que se hicieron

Con toda su historia la ves con 

```
$git log biografia.txt
```

Pero... para enviarlo a un server es con 

```
$git push
```

En los rtf no puedes añadir imagenes
En los txt es un texto normal y plano 
En los docx puedes guardar imagenes y texto, es una estructura binaria, word lo entiende y lo abre


Nosotros solo podremos editar y guardar como versión texto plano

## Introducción a la terminal y línea de comandos

```
$ pwd te dice donde estás
```

Linux inicia la ruta en "/"

cd es change directory
ls es listar
ls -al 
"-al" es un argumentos, que te traes unos especiales, te pide que muestres todos los archivos incluso los ocultos

"ls -l" 
Muestra casi todo, pero no los oculto

clear limpia la consola

Si quieres acceder a otro disco duro en linux lo haces como
/mnt/disco-2

Pero si tienes solo un disco como el c
lo haces con cd /c

cd .. regresas a la carpeta anterior

La carpeta home es donde siempre etarás cuando digas cd

mkdir creas carpeta

touch te permite crear archivos con nada adentro

con history te sale toda la historia de comandos, si quieres repetir un comando puedes invocar el numero del comando con

!num (u otro numero)

rm es remove

## Crea un repositorio git y haz tu primer commit

Para un repositorio, crea donde esta la carpeta central

Lo inicias con 
```
$ git init
```