# Ejercicio GIT - GITHUB
Veremos un poco de lo que hemos ido aprendiendo en este modulo de GIT - GITHUB.
*Para la creación de este archivo README.md me he apoyado con el siguiente editor: [Editor.md](https://pandao.github.io/editor.md/en.html "Editor.md")*

## Primeros pasos:
1. Crearemos un repositorio en GITHUB.
	- Para esto pinchamos en el signo de **suma (+)** que se encuentra en la parte superior derecha y presionaremos en **"New repository"**.

	-![](https://github.com/SantiagoomC/branches/blob/master/1.jpg?raw=true)

	- Luego nos aparecerán las siguientes opciones, de las cuales nos centraremos en el **Nombre del repositorio** y sí deseas puedes activar la opciones del archivo **README** para que se cree junto con el repositorio, sino, sólo presionaremos en **"Create repository"**.

	![](https://github.com/SantiagoomC/branches/blob/master/2.jpg?raw=true)

	- Después de la creación del **repositorio** aparecerá la siguiente ventana, donde podrás ver el link de tu repositorio y algunos comandos basicos para que lo puedas clonar y empezar a trabajar con él.

	![](https://github.com/SantiagoomC/branches/blob/master/3.jpg?raw=true)

2. Clonar el repositorio:
	- Para clonar el repositorio lo que haremos es: Primero ir a alguna carpeta donde queramos guardar todo el trabajo que estaremos haciendo, estando allí presionamos click derecho y luego en la opción que dice: **"Git Bash Here"**, hay de tener en cuenta que ya el programa **GIT** lo deberemos de tener instalado.

	- Luego de haber realizado los pasos anteriores, nos aparecerá la siguiente ventana y acá es donde empezaremos con los primeros comandos: 
	El primero será **git clone [nombreDelRepositorio] ** con el fin de clonar el repositorio a nuestro ordenador.
	-Luego de manera opcional podemos escribir el comando **ls** con este podremos saber que carpetas tenemos en la dirección donde clonamos el repositorio o donde estemos nos encontremos. 
	-Para ingresar a la carpeta que clonamos o la que necesitemos; desde la terminal escribimos **cd [nombreDeLaCarpeta]** en este caso será **"cd devjumpers/"**
	![](https://github.com/SantiagoomC/branches/blob/master/TerminalGit.jpg?raw=true)

------------

### Pasos para el README.md

**Acerca de los archivos [README](https://docs.github.com/es/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes "README")**

Para la creación del archivo **README.md** haremos lo siguiente: Escribimos el comando **touch** seguido del nombre que queremos asignar al archivo en este caso será **README.md** quedando **touch README.md**
Nueamente y de manera opcional, para comproborar que archivos se haya creado, podemos escribir **ls** en la terminal y comprobar que se encuentre allí.

Para editar este archivo me apoyé de dos programas, el primero es **Visual Studio Code** y el segundo sería el editor/pagina: **[Editor.md](https://pandao.github.io/editor.md/en.html "Editor.md")** el cual me brinda la estructura para pegarla en **Visual Studio Code**.

------------

## .GITIGNORE
Documentación [GIT - GITIGNORE](https://git-scm.com/docs/gitignore "GIT - GITIGNORE").

Para este punto de la actividad debemos de hacer lo siguiente:
- Investigar sobre **.gitignore**.
- Crear en el repositorio local un fichero llamado **privado.txt**.
- Crear en el repositorio local una carpeta llamada **privada**.

**Sobre .gitignore:** El propósito principal del archivo **.gitignore** es evitar que archivos innecesarios o generados automáticamente (por ejemplo, archivos de compilación, registros o archivos temporales) sean rastreados por Git. Esto ayuda a mantener el repositorio limpio y evitar conflictos innecesarios.

Para hacer uso de este deberemos de crear un archivo con el nombre **.gitignore** dentro de este escribiremos por cada línea los archivos que vayamos a evitar que sean rastreados por GIT.

**Para la creación de los archivos haremos lo siguiente:** 
En la carpeta del repositorio abrimos **Git Bash**
- Para la carpeta: Escribiremos el comando **mkdir privada**
- Para los otros archivos: Podemos escribir en una sola linea **touch .gitignore privado.txt** o sino por cada archivo escribimos **touch .gitignore** y luego **touch privado.txt**

Luego de haber seguido los pasos anteriores los archivos ya deberían de estar dentro del repositorio:

![](https://github.com/SantiagoomC/branches/blob/master/gitignore.jpg?raw=true)

Ya para culminar este punto, agregaremos los archivos dentro del .gitignore, podemos hacerlo desde **Visual Stuido Code** y por cada línea escribiremos los archivos, por lo que debería de quedar:
- Línea 1: privado.txt
- Línea 2: privada

Y podremos ya generar los pasos correspondiente para el push.

------------
## RAMAS, FICHEROS, MERGE, CONFLICTOS

#### Para esta parte de la actividad se estarán realizando varios puntos:

##### Añadir fichero y rama:

1. Añadir fichero **1.txt** al repositorio local.
	- Este lo haremos desde la rama master/main desde git bash usando el comando **touch 1.txt**
2.  Crear una rama con el nombre** v0.2**. Y posiciónate en dicha rama.
	-  Para este punto lo que haremos para agilizar un paso, escribiremos el comando **git checkout -b v0.2**, el cual creara la rama con el nombre **v0.2** y nos posicionará en dicha rama al mismo tiempo.
3. Añadir un fichero **2.txt** en la rama **v0.2** y subir los cambios al reposiorio remoto.
	- Para crear el nuevo fichero usaremos el comando **touch 2.txt** y posterior a esto usaremos ** git add . ** para agregar los nuevos archivos al área de preparación, luego los vamos a usar **git commit -m "[comentario]"** para realizar el commit y guardar los cambios en el repositorio local y para finalizar enviamos los cambios al repositorio remoto utilizando el comando **git push origin -u v0.2**.

##### Merge directo:

1.  Posicionarse en la rama **master/main** y hacer un merge de la **rama v0.2** en la **rama master**.
	- Para posicionarnos en una rama diferente usaremos el comando **git checkout [nombre de la rama]**, por lo que escribimos **git checkout master**, ya para hacer el merge escribimos **git merge [rama a fusionar]**, por lo que quedaría **git merge v0.2**

##### Merge con conflicto:

*Nota: Estos puntos los podemos hacer de varias formas, uno sería desde algún editor de texto como **Visual Studio Code**, ingresando directamente al **bloc de notas** o desde la misma consola de **git bash**.*

1. En la rama **master** poner **Hola** en el fichero **1.txt** y hacer commit.
	- Desde la rama **master** y estando en git bash escribimos lo siguiente: 
		**echo "Hola" > 1.txt** y finalizamos con un commit.
2.  Posicionarse en la rama **v0.2** y poner **Adios** en el fichero **"1.txt"**; y hacer commit.
	- Luego de haber realizado el paso anterior, nos vamos a posicionar en la rama **v0.2** usando el comando **git checkout v0.2**, escribimos "Adios"con el comando **echo "Adios" > 1.txt"** y hacemos commit.
3. Posicionarse de nuevo en la rama **master** y hacer un merge con la rama **v0.2**
	- Nuevamente ingresamos en la rama master usando el comando **git checkout master** y haremos el merge: **git merge v0.2**, esto generará un conflicto debido a que desde dos ramas diferentes hemos trabajado sobre el mismo documento **1.txt**, por lo que si ingresamos a **Visual Studio Code** veremos algo como esto:

	![](https://github.com/SantiagoomC/branches/blob/master/mergeConConflicto.jpg?raw=true)

	Donde tenemos dos opciones, la primera es que podemos modificar el archivo a nuestra convenencia, en mi caso he dejado el **"Hola"** en la línea #1 y el **"Adios"** en la línea #3 , o también podemos presionar en la opción que dice **"Accept Both Changes"** *(Aceptar ambos cambios)*. 

##### Arreglar conflicto:

Para arreglar el conflicto lo que debemos de hacer es: modificar el archivo como lo vimos en el paso anterior, luego de que esté como necesitamos, vamos a hacer un commit, por lo que primero usamos **git add .** y luego **git commit -m ""** y de está manera ya habremos solucionado el conflicto.


##### Listado de ramas
1. Investigas los comandos: **- -merged** y **- -no-merged**:
	- Listar ramas fusionadas: **git branch - -merged** Este comando mostrará una lista de las ramas que han sido fusionadas en la rama actual. Son las ramas cuyos cambios ya han sido incorporados en la rama actual mediante una fusión (merge) exitosa.
	- Listar ramas no fusionadas: **git branch - -no-merged** Este comando mostrará una lista de las ramas que no han sido fusionadas en la rama actual. Son las ramas cuyos cambios aún no se han incorporado en la rama actual mediante una fusión (merge).

	*Nota: Debemos ejecutar estos comandos mientras estamos en la rama de la cual queremos saber dicha información.*

2. Listar las ramas con merge y las ramas sin merge.
	- Estando en la rama **master** y ejecutando ambos comandos **- -merged** y **- -no-merged** nos registra lo siguiente:

	![](https://github.com/SantiagoomC/branches/blob/master/listaMaster.jpg?raw=true)
	- Estando en la rama **v0.2** y ejecutando ambos comandos **- -merged** y **- -no-merged** nos registra lo siguiente:

	![](https://github.com/SantiagoomC/branches/blob/master/listaV2.jpg?raw=true)

Cuando ejecutamos ambos comandos en las diferentes ramas que disponemos, observamos que la respuesta de estos comandos es difente, con base al comando **- -merged** vemos que en la rama **master**, nos registra: **master y debajo v0.2**.

Esto es porqué la rama v0.2 ya ha sido fusionada con la master, a diferencia de la respuesta que nos brinda estando en la rama **v0.2** que sólo da como respuesta el mismo nombre de la rama: **v0.2** porqué no hemos realizado ningún merged a esta rama.

Ahora, si observamos la respuesta que nos brinda el comando  **- -no-merged** también vemos diferencia en ambas ramas. En la rama **master** observamos que la respuesta está vacía debido a que la única rama que disponemos ya ha sido fusionada con éxito y no tenemos otra rama y sí observamos la respuesta desde la rama **v0.2** veremos que sólo está el nombre de la rama **master** debido a que no la hemos usado para fusionarla estando en  la rama **v0.2**.




------------

## Compañeros Devjumps

|  NOMBRE | GITHUB  |
| :------------: | :------------: |
|  Esteban Garcia | [github.com/egarcia9543](https://github.com/egarcia9543 "github.com/egarcia9543")  |
| Isabella E  |[github.com/i-echeverri22](https://github.com/i-echeverri22 "github.com/i-echeverri22") |
| Jeremmy Rojas  |[github.com/J-Rojas29](https://github.com/J-Rojas29 "github.com/J-Rojas29") |
| Jhonatan Toro   |[github.com/jtorova5](https://github.com/jtorova5 "github.com/jtorova5") |
| Michell  |[github.com/michell20](https://github.com/michell20 "github.com/michell20") |
|  Stiven Berrio | [github.com/StivenBerrio](https://github.com/StivenBerrio "github.com/StivenBerrio")  |


## Colaborador
|  NOMBRE | GITHUB  |
| :------------: | :------------: |
|  Stiven Berrio | [github.com/StivenBerrio](https://github.com/StivenBerrio "github.com/StivenBerrio")  |

