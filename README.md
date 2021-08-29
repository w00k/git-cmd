# Comandos basicos de Git

### inicio del repositorio
git init 

### agrega el archivo o los archivos al repositorio 
git add file.txt file_v1.txt

### envia el archivo al repositorio control de versiones 
git commit -m "comentario"

### guardar todos los archivos con cambios
git add .

### status de mi base de datos local 
git status 

### cambios historicos hechos 
git show

### historia de un archivo 
git log file.txt 

### enviar cambios al repositorio remoto 
git push 

### traer los cambios de un repositorio remoto 
git pull

## Ver cambios 

### cambios sobre un archivo 
git show archivo.txt

### ver los cambios entre 2 commits, commit2 debe ser el mas reciente, para leer de mejor manera los cambios
git diff commit1 commit2

## Volver al pasado 

### volver a una version anterior, todos los cambios 
git reset COMMIT --hard

### volver a la version anterior, pero lo que esta en staging, sigue en staging, es decir lo que esta en git add se mantiene 
git reset COMMIT --soft

### cambios especificos en los archivos 
git log --stat 

### volver a un commit especifico de un archivo 
git checkout COMMIT archivo.txt 

### volver a la version mas actualizada
git checkout master archivo.txt 

## Eliminar archivos 

### git rm elimina archivos de Git sin eliminar su historia, lo podemos recuperar volviendo en el tiempo
git rm --cached // elimina del area de staging y del proximo commit 
git rm --force // elimina el archivo de git y del disco duro 

### git reset permite volver al pasado, sin la posibilidad de volver al futuro, borra la historia y no hay vuelta atras
git reset --soft // borramos todo el historial y registros de Git, pero guardamos los cambios que tenemos en staging 
git reset --hard // borra todo, borra el historial y registro de Git, incluido staging 
git reset HEAD // saca los archivos de staging, para no enviarlos en el commit, se pueden volver a agregar con git add .

## Trabajar con repositorios remotos

## para traer los cambios del repositorio remoto al local 
git fetch 

## para copiar los cambios del repositorio local al directorio de trabajo
git merge // se hace un git fetch, seguido de git merge 

## para traer los cambios del repositorios remotro y al directorio con un solo comando 
git pull

