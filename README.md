# Comandos basicos de Git

1. Inicio del repositorio
```bash 
git init
```

2. Agrega el archivo o los archivos al repositorio 
git add file.txt file_v1.txt

3. Envia el archivo al repositorio control de versiones 
git commit -m "comentario"

4. Guardar todos los archivos con cambios en staging area
git add .

5. Guardo los archivos y hago commit, siempre que los archivos ya existan, no agrega los arvhicos nuevos
git commit -am "comentario"

6. Status de mi base de datos local 
git status 

7. Cambios historicos hechos 
git show

8. Historia de un archivo 
git log file.txt 

9. Enviar cambios al repositorio remoto 
git push 

10. Traer los cambios de un repositorio remoto 
git pull

## Ver cambios 

1. Cambios sobre un archivo 
git show archivo.txt

2. Ver los cambios entre 2 commits, commit2 debe ser el mas reciente, para leer de mejor manera los cambios
git diff commit1 commit2

## Volver al pasado 

1. Volver a una version anterior, todos los cambios 
git reset COMMIT --hard

2. Volver a la version anterior, pero lo que esta en staging, sigue en staging, es decir lo que esta en git add se mantiene 
git reset COMMIT --soft

3. Cambios especificos en los archivos 
git log --stat 

4. Volver a un commit especifico de un archivo 
git checkout COMMIT archivo.txt 

5. Volver a la version mas actualizada
git checkout master archivo.txt 

## Eliminar archivos 

1. Git rm elimina archivos de Git sin eliminar su historia, lo podemos recuperar volviendo en el tiempo
git rm --cached // elimina del area de staging y del proximo commit 
git rm --force // elimina el archivo de git y del disco duro 

2. Git reset permite volver al pasado, sin la posibilidad de volver al futuro, borra la historia y no hay vuelta atras
git reset --soft // borramos todo el historial y registros de Git, pero guardamos los cambios que tenemos en staging 
git reset --hard // borra todo, borra el historial y registro de Git, incluido staging 
git reset HEAD // saca los archivos de staging, para no enviarlos en el commit, se pueden volver a agregar con git add .

## Trabajar con repositorios remotos

1. Tara traer los cambios del repositorio remoto al local 
git fetch 

2. Para copiar los cambios del repositorio local al directorio de trabajo
git merge // se hace un git fetch, seguido de git merge 

3. Para traer los cambios del repositorios remotro y al directorio con un solo comando 
git pull

## Merge

1. El merge se realiza desde la rama que uno se traera los cambios, no de donde estan los cambios.
git merge branch_donde_estan_los_cambios

## Agregar un repositorio remoto 

1. Agregar un rpositorio remoto al repositorio local
git remote add origin URL_REPO

2. Revisar las versiones de origin y main 
git remote -v 

3. Antes de enviar los cambios al repositorio remoto, hay que hacer un merge, por tanto hay que hacer un:
git pull origin main --allow-unrelated-histories 

4. Ahora podemos subir los cambios
git pull origin main 

## Tags y versiones en Git

1. Ver toda la historia de mi proyecto, con lineas de ramas y commits 
git log --all --graph --decorate --oneline

1.1 Crear un alias, con el comando mas cool para ver la historia del repositorio 
alias arbolito="git log --all --graph --decorate --oneline"

2. Crear tag
git tag -a v0.1 -m "resultado de las primeras clases del curso" 6f4e648

3. Ver tags creados
git tag

4. Obtener el hash y el tag asociado, el uso del tag es que siempre este en el servidor remoto, para que los colacolboradores pueden ver en que estado esta la version.
git show-ref --tags

5. Publicar el tag en el repositorio remoto
git push origin --tags 


