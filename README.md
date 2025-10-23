# ***Primeros pasos***

Para clonar el repositorio en local usé el comando git clone + la clave ssh del repositorio
Para crear el archivo README.md usé el comando "touch README.md"
Para escribir esto usé el comando nano "README.md"
Para guardar estos cambios usaré "git add ."
Para hacer el commit usaré git commmit -m "commit inicial"
Para hacer el push a la rama remota usaré "git push origin main"


Pregunta: Si has clonado el repositorio que parte del comando anterior puedo omitir.

Respuesta: Si ya has clonado tu repositorio tienes que omitir el comando git clone... ya que este comando sirve exclusivamente para clonar tu repositorio en local.

# ***Añadir archivos al .gitignore***

Creamos el achivo "privado .txt" "touch privado.txt"

Creamos la carpeta "privada" "mkdir privada"

Añadimos el archivo y la carpeta al .gitignore:{
    echo "privado.txt" >> .gitignore
    echo "/privada" >> .gitignore
    git add .
    git commit -m "añadido fichero .gitignore"
}

Pregunta: el fichero y el directorio privado debe de subir al repositorio si se encuentra añadido al fichero .gitingnore. 

Respuesta: No, ya que al añadir el nombre de los archivos que no queremos que sean subidos al github al archivo .gitignore, ni estos archivos ni sus contenidos son subidos al repositorio en remoto.

# ***Añadir un archivo de texto***


Añadimos fichero 1.txt al repositorio local:{
    touch 1.txt
    git add .
    git commit -m "añadido 1.txt"
}

Pregunta: Si ejecutado las acciones add y commit, que realiza cada una sobre el/los ficheros.

Respuesta: La acción add añade los cambios realizados al repositorio y la acción
commit realiza una especie de punto de guardado al que poder volver en cualquier momento desde tu control de versiones.


# ***Crear un tag***

Creamos una etiqueta: "git tag v0.1"

Subimos los cambios al repositorio remoto: "git push --tag origin main"

Pregunta: ¿Qué es un tag sobre un repositorio git, en nuestro caso Github?.

Respuesta: Es una etiqueta con la que referenciamos a un commit en específico

# ***Crear una rama***

Creamos una rama "git branch v0.2"

Nos colocamos en la rama creada "git checkout v0.2"

Añadimos un fichero en la rama v0.2:{
    touch 2.txt
    git add .
    git commit -m "añadido 2.txt"
}

Subimos los cambios al remoto "git push origin v0.2"

Nos colocamos en la rama main otra vez "git checkout main"

Hacemos merge de la rama nueva en la main "git merge v0.2 -m "merge v0.2 sin conflictos""

Pregunta: Cuando estamos trabajando con ramas, cual es su fin, y sentido en organizaciones pequeñas/medianas/grandes.

Respuesta: El principal fin de las ramas de Git es el de que los colaboradores de un proyecto en común puedan realizar cambios en una especie de copia de seguridad que se pueda unir a la rama principal con el fin de no afectar el trabajo de sus compañeros.

# ***Merge directo***


Subimos los cambios al remoto "git push origin v0.2"

Nos colocamos en la rama main otra vez "git checkout main"

Hacemos merge de la rama nueva en la main "git merge v0.2 -m "merge v0.2 sin conflictos""

Pregunta: Se tendrían que producir conflictos en esta acción. 

Respuesta: No, ya que estás añadiendo los cambios realizados en la segunda rama a la primera, y al estar la primera vacía, no da conflictos.

# ***Merge con conflicto***
En la rama main ponemos Hola en el fichero 1.txt y hacemos commit:{
    git checkout master
    echo "Hola" >> 1.txt
    git add .
    git commit -m "hola en 1.txt"
}

Nos posicionamos en la rama v0.2, ponemos Adios en el fichero 1.txt y hacemos commit:{
    git checkout v0.2
    echo "Adios" >> 1.txt
    git add .
    git commit -m "adios en 1.txt"
}


No posicionamos de nuevo en la rama main y hacemos un merge con la rama v0.2:{
    git checkout master
    git merge v0.2
    vim 1.txt
    git add .
    git commit -m "arreglado merge en 1.txt"
}


# ***Listado de ramas***
Listamos las ramas con merge y las ramas sin merge:{
    git branch --merged
    git branch --no-merged
}


# ***Arreglar conflicto***
Arreglamos el conflicto anterior y hacemos un commit:{
    nano 1.txt
    git add .
    git commit -m "arreglado merge en 1.txt"
}



# ***Borrar rama***
Creamos un tag v0.2 con "git tag v0.2"


Borrar la rama v0.2 con "git branch -d v0.2"


# ***Listado de cambios***
Listar los distintos commits con sus ramas y sus tags:{
    git config --global alias.list 'log --oneline --decorate --graph --all'
    git list  
}






Entrega:
    Guarda el documento con el nombre README.md dentro de la carpeta de la actividad a3.
    Haz commit y push al repositorio de la asignatura.    
    Se deberá entregar la url al commit en el repositorio privado GitHub de la asignatura , apuntando al README.md . Debemos subir también al repositorio todos los archivos implicados en la elaboración de la actividad ( imágenes, etc ).  La url debe tener la siguiente estructura: https://github.com/<usuario>/imw/blob/<id del commit>/<ut>/<actividad>/README.md
    ⚠️ Al subir la url, es importante crear un enlace. Es decir, poner un href a la url anterior, y no pegar el texto tal cual.