# Comandos basicos de Git

1. Inicio del repositorio
git init 

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


