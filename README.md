# Comandos basicos de Git

1. Inicio del repositorio
```bash 
git init
```

2. Agrega el archivo o los archivos al repositorio 
```bash 
git add file.txt file_v1.txt
```

3. Envia el archivo al repositorio local, control de versiones 
```bash 
git commit -m "comentario"
```

4. Guardar todos los archivos con cambios en staging area
```bash
git add .
```

5. Guardo los archivos y hago commit, siempre que los archivos ya existan, no agrega los arvhicos nuevos
```bash
git commit -am "comentario"
```

6. Status de mi base de datos local 
```bash
git status 
```

7. Cambios historicos hechos 
```bash
git show
```

8. Historia de un archivo 
```bash 
git log file.txt 
```

9. Enviar cambios al repositorio remoto 
```bash 
git push 
```

10. Traer los cambios de un repositorio remoto 
```bash 
git pull
```

## Ver cambios 

1. Cambios sobre un archivo 
```bash 
git show archivo.txt
```

2. Ver los cambios entre 2 commits, commit2 debe ser el mas reciente, para leer de mejor manera los cambios
```bash 
git diff commit1 commit2
```

## Volver al pasado 

1. Volver a una version anterior, todos los cambios 
```bash 
git reset COMMIT --hard
```

2. Volver a la version anterior, pero lo que esta en staging, sigue en staging, es decir lo que esta en git add se mantiene 
```bash 
git reset COMMIT --soft
```

3. Cambios especificos en los archivos 
```bash 
git log --stat 
```

4. Volver a un commit especifico de un archivo 
```bash 
git checkout COMMIT archivo.txt 
```

5. Volver a la version mas actualizada
```bash
git checkout master archivo.txt 
```

## Eliminar archivos 

1. Git rm elimina archivos de Git sin eliminar su historia, lo podemos recuperar volviendo en el tiempo
```bash 
git rm --cached // elimina del area de staging y del proximo commit 
git rm --force // elimina el archivo de git y del disco duro 
```

2. Git reset permite volver al pasado, sin la posibilidad de volver al futuro, borra la historia y no hay vuelta atras
```bash 
git reset --soft // borramos todo el historial y registros de Git, pero guardamos los cambios que tenemos en staging 
git reset --hard // borra todo, borra el historial y registro de Git, incluido staging 
git reset HEAD // saca los archivos de staging, para no enviarlos en el commit, se pueden volver a agregar con git add .
```

## Trabajar con repositorios remotos

1. Tara traer los cambios del repositorio remoto al local 
```bash 
git fetch 
```

2. Para copiar los cambios del repositorio local al directorio de trabajo
```bash 
git merge // se hace un git fetch, seguido de git merge 
```

3. Para traer los cambios del repositorios remotro y al directorio con un solo comando 
```bash 
git pull
```

## Merge

1. El merge se realiza desde la rama que uno se traera los cambios, no de donde estan los cambios.
```bash 
git merge branch_donde_estan_los_cambios
```

## Agregar un repositorio remoto 

1. Agregar un rpositorio remoto al repositorio local
```bash 
git remote add origin URL_REPO
```

2. Revisar las versiones de origin y main 
```bash 
git remote -v 
```

3. Antes de enviar los cambios al repositorio remoto, hay que hacer un merge, por tanto hay que hacer un:
```bash 
git pull origin main --allow-unrelated-histories 
```

4. Ahora podemos subir los cambios
```bash
git pull origin main 
```

## Tags y versiones en Git


1. Ver toda la historia de mi proyecto, con lineas de ramas y commits 
```bash 
git log --all --graph --decorate --oneline
```

1.1 Crear un alias, con el comando mas cool para ver la historia del repositorio 
```bash 
alias arbolito="git log --all --graph --decorate --oneline"
```

2. Crear tag
```bash
git tag -a v0.1 -m "resultado de las primeras clases del curso" 6f4e648
```

3. Ver tags creados
```bash 
git tag
```

4. Obtener el hash y el tag asociado, el uso del tag es que siempre este en el servidor remoto, para que los coladores pueden ver en que estado esta la version.
```bash 
git show-ref --tags
```

5. Publicar el tag en el repositorio remoto
```bash 
git push origin --tags 
```

6. Borrar un tag 
```bash 
git tag -d dormido
```

## Ramas

1. Muestras las ramas 
```bash 
git show-branch 
git show-branch --all
```

2. Ver desde una app la historia del repositorio
```bash 
gitk 
```

## Merge

1. Primero ingregar a la rama base para el merge (la rama base, se trae los cambios de la rama con cambios y se hace el merge y se sube)
```bash
git checkout main
```

2. Traigo los cambios del repositorio en internet a local 
```bash
git pull origin main
```

3. Traigo los cambios desde la rama a la rama 
```bash 
git merge header
```

4. Subo los cambios
```bash 
git push origin main
```

## Pull Request

El *pull request* lo revisa el lider del equipo o el devops (generalmente, en casos excepcionales el lider de desarrollo). 

## Forks o Bifurcaciones
Es una caracter’stica œnica de GitHub en la que se crea una copia exacta del estado actual de un repositorio directamente en GitHub, Žste repositorio podr‡ servir como otro origen y se podr‡ clonar (como cualquier otro repositorio), en pocas palabras, lo podremos utilizar como un git cualquiera
.
Un fork es como una bifurcaci—n del repositorio completo, tiene una historia en comœn, pero de repente se bifurca y pueden variar los cambios, ya que ambos proyectos podr‡n ser modificados en paralelo y para estar al d’a un colaborador tendr‡ que estar actualizando su fork con la informaci—n del original.
.
Al hacer un fork de un poryecto en GitHub, te conviertes en due–@ del repositorio fork, puedes trabajar en Žste con todos los permisos, pero es un repositorio completamente diferente que el original, teniendo alguna historia en comœn.
.
Los forks son importantes porque es la manera en la que funciona el open source, ya que, una persona puede no ser colaborador de un proyecto, pero puede contribu’r al mismo, haciendo mejor software que pueda ser utilizado por cualquiera.
.
Al hacer un fork, GitHub sabe que se hizo el fork del proyecto, por lo que se le permite al colaborador hacer pull request desde su repositorio propio.
Trabajando con m‡s de 1 repositorio remoto
Cuando trabajas en un proyecto que existe en diferentes repositorios remotos (normalmente a causa de un fork) es muy probable que desees poder trabajar con ambos repositorios, para Žsto puedes crear un remoto adicional desde consola.

```bash 
git remote add <nombre_del_remoto> <url_del_remoto> 
git remote upstream https://github.com/freddier/hyperblog
```

Al crear un remoto adicional podremos, hacer pull desde el nuevo origen (en caso de tener permisos podremos hacer fetch y push)

```bash 
git pull <remoto> <rama>
git pull upstream master
```

ƒste pull nos traer‡ los cambios del remoto, por lo que se estar‡ al d’a en el proyecto, el flujo de trabajo cambia, en adelante se estar‡ trabajando haciendo pull desde el upstream y push al origin para pasar a hacer pull request.

```bash 
git pull upstream master
git push origin master
```

## Rebase

Solo para los repositorios locales, mala practica para los repositorios remotos.

1. Desde el branch con todos los cambios, se hace el rebase. Cambia la historia del branch tomando el ultimo commit de master y le pega los cambios del repositorio local, por eso es una mala practica.

```bash 
git rebase master
```

2. Posteriormente, hay que hacer un rebase desde master, sino se hacer se genera un error super raro (confiemos en Freddy)
```bash 
git rebase experimento
```

## Stash 

Es para guardar cambios en memoria para usarlos despues.

1. Guarda las modificaciones 
```bash 
git stash 
```

2. Regresa a las modificaciones 
```bash 
git stash pop 
```

3. Ver la lista de stash 
```bash 
git stash list
```

4. Mover el stash a un branch 
```bash 
git stash branch english-version
```

5. Borrar el stash guardado sin commitear todavia
```bash 
git stash drop
```

## Limpiar el espacio de trabajando

1. Para limpiar el espacio de trabajo es necesario hacer primero una revision de lo que se va a borrar. 
```bash 
git clean --dry-run
```

2. Para ejecutar el borrado usamos clean, pero ojo, a Git no le interesan las carpetas, solo los achivos que no esten en el historial. 
```bash 
git clean -f
```

## Traer un commit desde otra rama

1. Para traer un commit desde otra rama es necesario ingresdar a la rama que se usara vcomo base y ejecutar el siguiente comando
```bash 
git cherry-pick hash
```

## Reconstruir un commit

1. Para recontruir un commit, es necesario tener un commit y agregar cambios a ese commit (sin hacer otro commit).
```bash 
git commit --amend 
```

## Git Reset & Relog

1. Relog te muestra todo el log, incluso de elementos elimiunados.
```bash 
git relog
```

2. Reset te deja el workplace con la historia del cierto Header o commit.


SOFT
```bash 
git reset HEAD@{4}
```

HARD
```bash
git reset --HARD c894650
```

## Buscar 

1. Para buscar en archivos, hay que estar en la rama correcta y usar grep.
```bash 
git grep <a buscar >
```

2. Buscar conociendo la linea exacta.
```bash 
git grep -n <a buscar>
```

3. Cantidad de veces que esta una palabra en los archivos.
```bash 
git grep -c <a buscar>
```

4. Buscar en los commits.
```bash 
git log -S "cabecera"
```

## Comandos utiles 

1. Ver los commits con los comentatios como principal
```bash 
git shortlog
```

2. Todas las personas que han hecho commits, incluso lo que han eliminado. 
```bash 
git shortlog -sn --all
```

3. Todas las personas que han hecho commits, omitiendo los merge.
```bash 
git shortlog -sn --all --no-merges
```

4. Generar alias en mi configuracion de Git 
```bash 
git config --global alias,stats "shortlog -sn --all --no-merges"
git stats 
```

5. Quien hizo que?
```bash 
git blame -c archivo 
```

6. Abrir el manual de cierto comando.
```bash 
git blame --help
```

7. Ver los branch remotos 
```bash 
git branch -r
```


