Este es el primer video de la serie “Crear un blog con Firebase y Angular” pero además de los puntos principales (Angular y Firebase), mencionaré algunos tips que les serán de ayuda.

## ¿Qué debes tener instalado?

### NodeJS

Nos permite utilizar Javascript del lado del servidor y nos permite también utilizar varios paquetes, módulos o librerías para poder ejecutar diferentes acciones, como:Crear un servidor de desarrollo.Ejecutar tareas de minificación de código.Para verificar que **NodeJS** esté instalado, en la terminal de su sistema operativo (Mac y Linux busquen su terminal y en Windows pueden usar Git Bash o PowerShell)  deberán escribir y luego presionar enter a lo siguiente:

> node -v

### NPM

Para ejecutar diferentes acciones utilizando **NodeJS** ustedes podrán utilizar **NPM**, el cual es el **Node Package Manager**, el cual me permitirá instalar los diferentes paquetes/módulos/librerías que ustedes necesiten.Para verificar que tengan instalado **NPM** deben escribir y luego presionar enter a lo siguiente:

> npm -v

Ahora, para poder instalar de forma global un paquete (esto significa que puedas ejecutar los comandos de ese paquete desde cualquier lugar en tu terminal), debes escribir el comando `npm install` agregando `-g` que significa `global`

> npm install -g NOMBRE-DEL-PAQUETE

### Angular CLI

Dentro de los paquetes necesarios, nosotros utilizaremos **Angular CLI** o **Angular Command Line Interface**, el cual me deja disponible una lista de comandos para poder ejecutar desde mi terminal y estos comandos están relacionados a que pueda crear un proyecto con **Angular** (ejecutar mi servidor de desarrollo, crear componentes, etc).Dentro de los comandos que tendrás disponible los que usaré son los siguientes:

#### ng new NOMBRE-DEL-PROYECTO

Me permite crear un nuevo proyecto pero además, si le agrego opciones extra, puedo personalizar la creación de mi proyecto. Para la serie, creare el proyecto con el siguiente comando:

> ng new blog-angular-firebase --style scss --routing

La opción `--style scss`, me permite decirle que usare SASS como preprocesador, el cual me ayudará a crear CSS de una forma mas rapida y la opción `--routing`, me permite generar el archivo de rutas dentro de mi proyecto (esto se puede hacer manualmente).Si necesitan ver cuantas otras opciones tiene el comando `ng new` pueden escribir en la terminal lo siguiente:

> ng new --help