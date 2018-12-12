# Guía de uso de GitHub 🐱📓

## Agregar nombre y correo personal a la configuración.
```
$ git config --global user.name “<nombre>”
$ git config --global user.email “<email>”
```

## Mostrar listado de Git y sus funciones.
```
$ git help
```

Mostrar en el navegador y más a detalle de la función
```
$ git help <nombre_función>
```

## Inicializara Git para monitorear el proyecto.
```
$ git init
```

## Agregar un repositorio.
```
$ git remote add origin https://github.com/AlexAndrei04/<nombre.repositorio>.git
```

## Estado del proyecto.
```
$ git status
```

## Agregar archivos a la sala de espera.
Agregar todo los archivos
```
$ git add .
```

Agregar un archivo en específico
```
$ git add <ruta_archivo>
```

## Clonar repositorio de GitHub a local.
```
$ git clone <ruta_git>.git
```

## Conectar de repositorio GitHub a local.
```
$ git remote add origin <nombre_repo>.git
```

## Eliminar conexión del repositorio Github con local.
```
$ git remote remove origin
```

## Checar conexión de repositorios locales con remotos.
```
$ git remote -v
```

## Muestra los cambios creados
```
$ git diff
```

Mostrar diferencias entre dos commits por medio de su hash. De preferencia poner el como primer hash el que se va a comparar y el segundo como el hash principal
```
$ git diff <hash> <hash>
```

## Se guardan los cambios con un mensaje para identificarlos.
```
$ git commit (Se abre sección para agregar mensaje)
$ git commit -m “<mensaje>” (Parámetro para que no se abra en un sección aparte)
```

En caso de que se haya olvidado agregar un detalle al último commit, se puede unificar de la siguiente manera:
```
$ git commit --amend
```

## Muestra una lista de todos los commits con su respectiva información.
```
$ git log
```

Para mostrar los commits en una sola línea.
```
$ git log --oneline
```

Para mostrar los commits en una sola línea en forma de gráfica.
```
$ git log --oneline --graph
```

Para mostrar los commits en una sola línea decorados.
```
$ git log --oneline --decorate
```

Para mostrar los commits de todas las ramas en una sola línea.
```
$ git log --oneline --decorate --all
```

En caso de generar un archivo, con el siguiente comando se puede realizar
```
$ git log > <nombre>.txt / generamos un archivo con los commits
```

## Mostrar información acerca de algo en especifico.
```
$ git show <hash>
$ git show <tag>
$ git show <commit>
```

## Viajar entre ramas o deshacer modificaciones.
```
$ git checkout  -- <archivo> (Lo hace únicamente a uno).
```

Para cambiar a la rama que deseamos
```
$ git checkout <nombre_branch>
```
ó
```
$ git checkout <código_SHA>
```

## Revertir los cambios de un commit, alternando los  cambios agregados por los eliminados.
```
$ git revert --no-commit <hash>
```

Termina de hacer la reversión y hace un commit.
```
$ git revert --continue
```

## Similar a checkout a diferencia que deshace los commits.
Deshace el commit, pero los cambio se quedan en el stage. No modifica el código.
```
$ git reset --soft <hash>
```

Deja el código al commit seleccionado, borrando el commit y todos los cambios hechos, quitandolos del stage area.
```
$ git reset --hard <hash>
```

En caso de deshacer el último commit, hacer lo siguiente, dónde “HEAD” indica que es el último commit realizado
```
$ git reset HEAD <archivo>
```

## Construir alias
Para los comandos hay que hacerlos dentro de comillas simples.
```
$ git config --global alias.<nombre.alias> ‘<comandos.git>’
```

Ejemplo de uso.
```
$ git config --global alias.lodag 'log --oneline --decorate --all --graph'
```

Obtiene todo los ajustes de un parámetro de una expresión regular
```
$ git config --global --get-regexp <parametro>
```

Ejemplo de uso. Mostrará todos los alias que se han creado
```
$ git config --global --get-regexp alias
```

Eliminará el alias.
```
$ git config --global --unset alias.<nombre.alias>
```

## Checar las ramas que tenemos.
Muestra todas las ramas.
```
$ git branch
```

Muestra todas las ramas hasta las remotas.
```
$ git branch --all
```

Pasándole como parámetro el nombre, generará una nueva rama con ese respectivo nombre.
```
$ git branch <nombre.branch>
```

Se crea y se cambia a la rama nueva.
```
$ git checkout -b <nombre.branch>
```

Renombrar una rama.
```
$ git branch -m <nombre.branch-viejo> <nombre.branch-nuevo>
```

Eliminar una rama.
```
$ git branch -d <nombre.branch>
```

Muestra todas las funciones posibles de las ramas.
```
$ git branch -d <nombre.branch>
```

Fusionar la ramas secundarias con la maestra. Se tiene que estar en la rama maestra para hacerlo.
```
$ git merge <nombre.branch>
```

Fusiona commits de ramas alternativas con la rama maestra
``` 
$ git rebase
```

Puedes fusionar commits, cambiarlos de posición. De preferencia hacerlo en ramas alternas y que no se hayan hecho push. El número indica la cantidad de commits a seleccionar.
```
$ git rebase - i HEAD~2
```

Carga los archivos locales a Github con la rama maestra.

**-f** / para forzar la carga.
```
$ git push origin master
```

Sincroniza lo que se tenga en local con el repositorio remoto.
```
$ git pull origin master
```

Eliminar rama de GitHub
```
$ git push --delete origin <nombre_rama>
```

## Cambiar el mensaje del commit.
```
$ git commit --amend -m "<mensaje_commit>"
```

Para especificar el commit
```
$ git commit --amend -m "<mensaje_commit>" "<code.sha>" 
```

## Crear una tag anotada para un commit
Muestra todas tags creadas
```
$ git tag
``` 

Se crea una tag.
```
$ git tag <nombre.tag>
```

Ejemplo de la creación de una tag.
```
$ git tag v1.0
```

Crear una tag exacta de un cierto commit
```
$ git tag v0.1.0 <code.sha>
```

Eliminar una tag
```
$ git tag -d v0.1.0
```

Mostrar las tags de predeterminada versión. Donde por ejemplo, mostrará todas las etiquetas de la versión 1
```
$ git tag -l “v1.*.0”
```

Crear un tag anotado
```
$ git tag -a v
```

Carga el tag al repositorio
```
$ git push origin v1.0
```

Cargar todas las tags al repositorio
```
$ git push origin --tags
```

## Guardar cambios sin generar commits

Guarda el directorio de trabajo. Se pueden acumular los directorios.
```
$  git stash
```

Recupera el directorio.
```
$ git stash apply
```

Para eliminar un directorio
```
$ git stash drop
```

El “save” puede ser opcional pero sirve para darle un mensaje al stash.
```
$ git stash save “<mensaje>”
```

Muestra todos los stash 
```
$ git stash list
```

## Workflows
Trae las ramas y modificaciones del repositorio remoto
```
$ git fetch origin
```
