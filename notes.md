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
https://platzi.com/clases/1557-git-github/19936-crea-un-repositorio-de-git-y-haz-tu-primer-commit/

Para un repositorio, crea donde esta la carpeta central

Lo inicias con 
```
$ git init
$ git status
$ git rm 
$ git rm --cached
```
status nos dice el estado del trabajo en el momento
rm remueve el archivo del git
rm cached es memoria ram, no esta en la base de datos y sus cambios

git commit -m "Este es el primer commit de este archivo"

Pero debes decir quien eres, si no le dices por defecto te trae las variables de entorno

```
- accedes a un comando
-- vas a usar una palabra
```

git add . añades todo

git log
Nos muestra la historia del archivo
El numero largisimo es el nombre de ese commit


## ¿Qué es un Branch (rama) y cómo funciona un Merge en Git?

![alt text](https://static.platzi.com/media/public/uploads/branches_f9d7e237-6a15-4143-a4e9-cc5af06be833.PNG)

Cada commit es una nueva versión, esto en **master**

Experimentos nace de v3 y se crean nuevas cosas

Si se encuentra un bug, se podría crear una rama llamada Bugfiting o **Hotfix** haciendo pruebas en la rama actual y luegoson probados con la rama actual o **merge**, es decir, unes los cambios de una rama con otra

Acabados los experimentos, le pides que se fusione con la rama final, es decir que hagan merge

La rama de experimentos lo suelen llamar también **development**

A veces hay conflictos, donde se rompen archivos 

### Gitflow:

GitFlow es una una guía que nos da cierto estándares para manejar la ramificación de nuestros proyectos, es decir, que ramas debemos tener, cuándo y de dónde debemos crear nuevas ramas, cómo debemos nombrar dichas ramas y muchos otros conceptos que nos ayudaran a manejar mucho mejor nuestro repositorio; siendo esto muy importante cuando trabajamos en conjunto con varios desarrolladores.

Links:
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

https://danielkummer.github.io/git-flow-cheatsheet/

## Analizar cambios en los archivos de tu proyecto con Git

$ git show

Muestra la historia de cambios
diff muestra la diferencia entre la version anterior y la nueva

Vamos a añadir un tercer estado

El git commit te va a sacar un editor de codigo en la linea de comandos usando VIM,, en WSL es "nano"

Nada de los hashtags va a ir en el Git

$ git diff v1 v2
Priomero va la version original y luego la mas nueva

### Resumen de comandos:
```
$ git init //inicializar el repositorio
$ git add nombre_de_archivo.extencion //Agregar el archivo al repositorio
$ git commit -m “Mensaje”// Agregamos los cambios para el repositorio
$ git add .// Agregar los cambios de la carpeta en la que nos encontramos agregar todo
$ git status // visualizar cambios
$ git log nombre_de_archivos.extencion //historico de cambios con detalles
$ git push //envia a otro repositorio remoto lo que estamos haciendo
$ git pull //traer repositorio remoto
$ ls //listado de carpetas en donde me encuentro es decir dir en windows
$ pwd //ubicacion actual
$ mkdir //make directori nueva carpeta
$ touch archivo.extencion//crear archivo vacio
$ cat archivo.extencion//muestra el contenido del archivo
$ history //historial de comandos utilizados durante esa sesion
$ rm archivo.extencion //eliminacion de archivo
$ comando --help //ayuda sobre el comando
$ checkout //traer cambios realizado
$ git rm --cached archivo.extencion//se usa para devolver el archivo que se tiene en ram cuando escribimos git add lo devuleve a estado natural mientra esta en staging
$ git config --list //muestra la lista de configuracion de git
$ git config --list --show-origin//rutas de acceso a la configuración de git
$ git log archivo.extencion //muestra la historia del archivo
```

## ¿Qué es el staging y los repositorios? Ciclo básico de trabajo en Git

![alt text](https://static.platzi.com/media/public/uploads/capture1_44e940e0-77b2-4f04-b76d-d7637b4ca7a7.PNG)


Un directorio y carpeta es lo mismo, cuando accedes por consola e iniicas un git init

Se crea un área de memoria ram llamada staging, es donde irás añadiendo los cambios y se cre el rapositorio, encontrado en la carpeta .git, donde están los cambios

Una vez hagas esos cambios, los agregas al stagin area usando el comando git add

Al usar el add, el archivo vive en staging pero espera que sea enviado al repositorio

Al usar commit, el archivo ahora se va a lrepositorio, cuyo nombre es master. Entonces aquí tendremos todos los cambios que hagamos.

Estados del archivo:

En un inicio está en untracked, o sin rastrear. 

Una vez haces el git add, entra al estado tracked y hace parte de staging y chequea los cambios

Una vez le das add, sabe que hay cambios y se van a stagging

Si hay cambios y no le das a git add no está en staging

En el repositorio se le añade los indicadores del commit, y todos pueden ver los cambios que se hicieron

Puede haber un cambio en el repositorio pero no en tu carpeta

Entonces irás a esa rama, y harás el comando checkout, que trae los últimos cambios hacia tu carpeta

![alt text](https://static.platzi.com/media/user_upload/estados-git-0acb84f7-5080-4098-99d9-59012a3b8e86.jpg)


## Volver en el tiempo en nuestro repositorio utilizando reset y checkout

git reset te permite llegar a una versión anterior

git reset version --hard
Todo vuelve al estado anterior

git reset version --soft
volvemos a la versión pero lo que esté en stagging, sigue en stagging

Con git log, veremos que todo lo que hemos hecho se ha borrado

Con git diff, lo verde y + verás los  cambios que has hecho pero no añades y el resto anda en la memoria ram

git log --stat
Verás los cambios especificos que se hicieorn a partir del commit

git checkout v1
Puedes ver la version que quieras y vas a regresar a esa estado, no va a cambiar nada

Si haces un commit vas a borrar todo lo que tenias antes

si haces git checkout master vuelves a la ultima version con el ultimo commit

## Git reset vs Git rm

**git rm** eliminará archivos de git sin eliminar su historial de versiones

Así que para recuperr esos archivos, debes viajar en el tiempo al último commit antes de eliminarlos 

Para usarlo tienes:

git rm --cached
Elimina los archivos del repositorio local y de staging, pero los mantiene en el disco duro.
Básicamente deja de trackear el historial de esos archivos, por lo que pasarán a un estado de untracked

git rm --force
Elimina los archivos de Git y del disco duro. Git guarda los archivos y su existencia, pero es dificil acceder a ellos.


git reset ayuda a volver en el tiempo pero sin posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir.

Solo usalo en casos de emergencia
Para usargit reset puedes usar:

git reset --hard
Borra toda la información en staging (se va para siempre). Borra todo. Se borra la informacion de los commits y del staging.

git reset --soft
Mantiene los archivos en staging para que apliques unos ultimos cambios desde un commit anterior. Borra el historial y registros pero guarda los cambios en staging.

git reset HEAD
Saca los archivos del area de staging. Solo para que los últimos cambios de los archivos no se envíen al último commit. Lo solucionas volviendolos a añadir con git add

### Caso:
Imagina el siguiente caso:

Hacemos cambios en los archivos de un proyecto para una nueva actualización. Todos los archivos con cambios se mueven al área de staging con el comando git add. Pero te das cuenta de que uno de esos archivos no está listo todavía. Actualizaste el archivo, pero ese cambio no debe ir en el próximo commit por ahora.

¿Qué podemos hacer?

Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.

¡Al usar git rm lo que haremos será eliminar este archivo completamente de git! Todavía tendremos el historial de cambios de este archivo, con la eliminación del archivo como su última actualización. Recuerda que en este caso no buscábamos eliminar un archivo, solo dejarlo como estaba y actualizarlo después, no en este commit.

En cambio, si usamos git reset HEAD, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

Conclusión: Lo mejor que puedes hacer para salvar tu puesto y evitar un incendio en tu trabajo es conocer muy bien la diferencia y los riesgos de todos los comandos de Git.


# Flujo de trabajo básico en Git

Tienes un directorio de trabajo, donde están los archivos, ahi le das git init en la consola

Aparece un área de preparación o staging, lugar donde vas a enviar los archivos antes de enviar a la base de datos o repositorio local

Cuando quieres agregar una carpeta de tu archivo al repositorio, lo pones en la area de preparacion o staging con git add, le permite a git esto a darle un seguimiento 
 
Si haces cambios, git no los va a guardar, quedan en tu directorio de trabajo

Lo que queda en staging se puede perder si no me mandan al repositorio local, si no haces nada con ellos se van para proteger a de la memoria ram

Para prevenir debes enviarlos como la version final, lo haces con git commit

Envias todo lo que esta en staging al repositorio local

¿Que pasa en un equipo de trabajo?

Necesitas un servidor o repositorio remoto, donde todo el mundo le manda datos trabajados en local, suele ser github, gitlab o gitlocker.

en vez de dar git init, le damos git clone url, se trae una copia del master al directorio y crea la base de datos de todos los cambios en el repositorio local

sigues haciendos commits normal al repositorio local, pero cuando este listo para enviar al server de todos, usas git push

que pasa si quiero traer una actu de alguien pero ya lo clone, uso git fetch, me lo trae del repositorio pero no lo copia en los archivos, para que lo copie debo fusionarlos con la ultima version en repo local y el de mi directorio, eso lo hago con git merge

git pull, copia el repo local, la base local y el directorio

![alt text](https://static.platzi.com/media/user_upload/Flujo%20Git%20%281%29-4de33c4b-227a-4ca4-83c4-dc11843518e6.jpg)

## Introducción a las ramas o branches de Git

La rama inicial es master

En las ramas puedes hacer cambios sin afectar la principal rama

La rama maestra cambiara el blogpost pero otra rama trabajara el header

Luego las fusionaremos

Master es nuestra rama principal, contamos con una historia de commits, el mas reciente es la cabecera o HEAD, detatch head es una version anterior, vuelvec con un checkout del head del master

Creamos una rama llamada cabecera, esto creara una copia del último cmmit en otro lado, y todos los cambios en la rama no se verán en master hasta que se fucionen con merge

git commit -am hace git add, solo funciona con archivos que ya hicimos git add

La rama se va a crear desde el lugar donde estas

git show muestra los cambios, veo el head en el master

git branch cabecera 

Ahora con git show vemos que tenemos un head que le apunta al master y también a la cabecera pero seguimos em master

En c2 teniamos los cambios del blospost

Creamos una brach en cabecera con una copia exacta de c2

Empezamos a hacer cambios en la rama cabecera, y ya no se ve en la rama master, y el Head viene a estar allá en lugar del blogpost

git checkout rama 
cambian al ultimo comit de cada version

Head es un indicador de cual versión de commit estas viendo de los ultima version

![alt text](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202020-02-18%20a%20la%28s%29%2017.01.44-c4873db5-4330-4c63-8a79-d454a86123ff.jpg)

## Fusión de ramas con Git merge

