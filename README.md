Git hub commands
================

Iniciando el repositorio
  - Creamos repo en github
  - Le asignamos un nombre, no seleccionar en "crear README.md", eso lo hacemos aparte en local
  - Una vez creado el repo en github volvemos a nuestra pc
  - Buscamos el directorio de nuestro proyecto por la terminal (ej: /Documents/Code/Class04)
  - Dentro de la raiz d nuestro directorio escribimos "git init"
  - Luego de crear los archivos iniciales (ej: index y bootstrap files) hacemos un "git status"
  - El git status nos mostrara los cambios en el directorio. Agregamos los cambios a un commit usando "git add --all"
  - Una vez agregados los cambios, comiteamos usando "git commit" o la version corta 'git commit -m "commit inicial" '
  - Ahora vamos a agregar github a nuestro directorio para poder subir los cambios al repositorio web: git remote add origin "direcciondegit"
    - ej: git remote add origin git@github.com:matiasmoya/class04.git"
    - Esta direccion la podemos copiar desde el menu a la derecha en el repo de github
  - Una vez agregado el remote a nuestro directorio podemos pushear los cambios
    - git push origin master

Cada vez q hagan cambios relevantes, hagan commits. Cuando tengan algo funcional o esten por cerrar algo, pusheen los cambios al repositorio asi podemos revisarlos, contribuirles, etc.

Pueden pushear tantos commits como quieran, no es necesario (ni tampoco ideal) hacer push por cada commit. Hagan commits en cada cambio relevante q hagan, por si necesitan volver atras en el tiempo y deshacerlo, o simplemente tener un seguimiento de los cambios bien documentado.

Obteniendo repositorios
=======================

Para copiar un repositorio en nuestras maquinas, podemos clonarlos:
  - Para clonar el repositorio de la clase 4 de pequenio podemos ingresar a 
    - http://github.com/pequege/class04
  - En el menu de la derecha podemos copiar el ssh si estamos como colaboradores, o el http si solo queremos copiar los archivos en nuestra pc.
  - Una vez copiado, vamos a la carpeta donde queremos descargar la carpeta "class04", x ejemplo en /Documents/Clases/
  - Una vez que estemos (desde la terminal) en /Documents/Clases vamos a escribir:
    - git clone https://github.com/pequege/class04.git (si no tenemos el ssh)
    - o sino:
    - git clone git@github.com:pequege/class04.git (si tenemos el ssh)

  Con esto ya tendremos la carpeta class04 en nuestra carpeta clases, con el git iniciado y los commits de pequeño.

Actualizando repositorios
=========================

Para poder actualizar repositorios que hayamos clonados, o descargar cambios de un repo que tengamos en github se utiliza el comando PULL
  - Para pulear los cambios realizados en class04 de pequeño, vamos a ir a nuestra carpeta en terminal (ej: Documents/Clases/class04/) y una vez que estemos alli vamos a escribir:
    - git pull origin master

Dependiendo si clonamos el repositorio con ssh o http, seran los permisos que tengamos
  - ssh nos permite pullear y pushear cambios (leer y escribir)  
  - http nos permite solamente pulear cambios (solo leer)

Agregando repositorios remotos
==============================

Si lo que queremos es agregar repositorios remotos (por ejemplo un repo git limpio sin nada, a donde subir los cambios de nuestro git local), se añade el repositorio con el commando REMOTE ADD

Imaginemos este caso:
Creamos una carpeta clasejemplo en Documents/Clases, luego nos fuimos por terminal a inciar git en esta carpet a (cd Documents/Clases/clasejemplo) y escribimos "git init" para incializar git y controlar todos los cambios LOCALMENTE.

Luego creamos los CSS, index.html y archivos necesarios para nuestro proyecto.

Hicimos un commit indicando que comenzamos el proyecto y que creamos esos archivos. (git add --all -> git commit)

Seguimos trabajando, e hicimos otros commits. Ahora decidimos que es hora de subir nuestros cambios a github para que el resto d la clase pueda ver nuestro codigo y colaborar en el desarrollo.

Creamos un repositorio en github.com, ahora vamos a agregarlos a nuestro repositorio local

Cuando creamos el repositorio en github, en el menu de la derecha nos aparece la direccion SSH de nuestro repositorio para que lo podamos agregar como remoto:
  - git@github.com:matiasmoya/clasejemplo

Ahora vamos, desde la terminal, a nuestro directorio Documents/Clases/clasejemplo y escribimos :
  - git remote add origin git@github.com:matiasmoya/clasejemplo
  - Donde dice origin puede ir cualquier cosa, es el "tag name" de nuestro repositorio remoto, que lo vamos a usar para los comandos push y pull

podemos comprobar que se agrego correctamente escribiendo "git remote -v"
Nos deberia aparecer origin y la direccion 2 veces (fetch y push) lo que significa que podemos pullear y pushear a este repositorio.

Para subir nuestros cambios, ahora que tenemos el permiso push, vamos a escribir:
  - git push origin master
  - El primer nombre despues de push es "a donde" y el segundo es "desde donde". master es nuestra rama principal por defecto en este ejemplo

Listo, vayan al repositorio en github y van a poder ver que los archivos y los commits se subieron correctamente!
Nota: no pueden hacer push ni pull si no hicieron commit de todos los cambios. Si hay archivos que estan sin seguimiento o modificados y no fueron agregados a un commit, git no les deberia permitir hacer uso de estos comandos.

Tener archivos sin commits se dice que son archivos que estan en "staging", y que estan en espera de entrar en algun commit.

No pueden tener archivos en staging para usar push o pull.
