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

### cambios sobre un archivo 
git show archivo.txt

### ver los cambios entre 2 commits, commit2 debe ser el mas reciente, para leer de mejor manera los cambios
git diff commit1 commit2
