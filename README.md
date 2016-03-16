#Clase 2 Práctico DA2

##Temas
1. Git por consola
2. Github
3. Ejercicio github
4. Postman
5. Dudas

##Git por consola

###Intro GIT

###Comandos básicos

```bash
git init
git clone
git add 
git checkout
git commit
git fetch
git merge
git pull
git push
```

###Iniciando el repositorio
Hay dos maneras de utilizar Git en tus proyectos.

####```git init```

Esto permite seguir un proyecto existente en Git. Para ello, se debe acceder a la carpeta del proyecto, y correr el comando ```git init```.
Al ejecutar el comando, se crea un subdirectorio ```.git```, el que contendrá todos los archivos necesarios para mantener el repositorio. Luego de ejecutado este comando, ninguno de los archivos del proyecto se encuentran mantenidos por el repositorio.

####```git clone```

En caso de querer obtener un repositorio existente, se debe utilizar el siguiente comando.
```bash
git clone https://github.com/DisAplicaciones2ORT0316/Clase2.git
```

Al compararlo con otros sistemas de control de versiones, como Subversion, se puede apreciar la diferencia entre ```clone``` y ```checkout```. Esta diferencia es importante, ya que ```git clone``` trae una copia completa de casi toda la información almacenada en el repositorio. Esto quiere decir que, si el disco duro del servidor de repositorios se corrompe, cualquiera de los clones puede ser usado como respaldo para restaurarlo.

Este comando crea un directorio con el nomrbe del repositorio, y dentro de él coloca todos los archivos del mismo. En caso de querer personalizar el directorio que se va a crear, se agrega luego de la url del repositorio.

```bash
git clone https://github.com/DisAplicaciones2ORT0316/Clase2.git MiClase2
```

Los protocolos de transferencia de git pueden ser https, como el anterior, o con ssh, dependiendo de la preferencia del usuario.

###Guardando cambios en el repositorio

