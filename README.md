Para clonar el repositorio en local usé el comando git clone + la clave ssh del repositorio
Para crear el archivo README.md usé el comando "touch README.md"
Para escribir esto usé el comando nano "README.md"
Para guardar estos cambios usaré "git add ."
Para hacer el commit usaré git commmit -m "commit inicial"
Para hacer el push a la rama remota usaré "git push origin main"



Pregunta: Si has clonado el repositorio que parte del comando anterior puedo omitir.

Si ya has clonado tu repositorio tienes que omitir el comando git clone... ya que este comando sirve exclusivamente para clonar tu repositorio en local.



Pregunta: el fichero y el directorio privado debe de subir al repositorio si se encuentra añadido al fichero .gitingnore. 

No, ya que al añadir el nombre de los archivos que no queremos que sean subidos al github al archivo .gitignore, ni estos archivos ni sus contenidos son subidos al repositorio en remoto.



Pregunta: Si ejecutado las acciones add y commit, que realiza cada una sobre el/los ficheros.

La acción add añade los cambios realizados al repositorio y la acción
commit realiza una especie de punto de guardado al que poder volver en cualquier momento desde tu control de versiones.



Pregunta: ¿Qué es un tag sobre un repositorio git, en nuestro caso Github?.

Es una etiqueta con la que referenciamos a un commit en específico



Pregunta: Cuando estamos trabajando con ramas, cual es su fin, y sentido en organizaciones pequeñas/medianas/grandes.

El principal fin de las ramas de Git es el de que los colaboradores de un proyecto en común puedan realizar cambios en una especie de copia de seguridad que se pueda unir a la rama principal con el fin de no afectar el trabajo de sus compañeros.