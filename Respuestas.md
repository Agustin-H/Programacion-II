1. ¿Qué es git?
Git es un software de control de versiones diseñado por Linus Torvalds, pensando en la eficiencia y la confiabilidad del mantenimiento de versiones de aplicaciones cuando éstas tienen un gran número de archivos de código fuente
2. ¿Por qué queremos utilizar git?
por que queremos controlar los cambios de nuestros proyectos a medida que van evolucionando 
3. ¿Qué es el bash que instala git?
El bash, es una herramienta de tipo consola que básicamente te permite manipular y gestionar todo el proceso a realizar con el proyecto. Es de aclarar que la explicación inicial se hace basada en Windows, sin embargo su funcionalidad es igual en cualquier sistema operativo
4. Describa los estados (working directory, staging area, repository)
working directory: el directorio de trabajo de un proceso es un directorio de un sistema de archivos jerárquico, si lo hay, asociado dinámicamente con cada proceso. A veces se le llama el directorio de trabajo actual, p. la función getcwd de BSD, o simplemente el directorio actual.
staging area: son archivos en Staging. Viven dentro de Git y hay registro de ellos porque han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando git commit.
repository:  Un repositorio o “repo” es un directorio donde se almacenan los archivos de tu proyecto. Puede estar ubicado en el almacenamiento de GitHub o en un repositorio local en tu computadora. Puedes almacenar archivos de código, imágenes, audios o todo lo relacionado con el proyecto en el repositorio
5. Describa el flujo para crear un nuevo repositorio git. 
Para crear nu repositorio Git, donde monitorizamos los archivos de un proyecto, tenemos que realizar una operación previa. Es la inicialización del repositorio Git que queremos crear en la carpeta de tu proyecto y es una operación que deberás realizar una única vez para este proyecto.
Así pues, antes que nada (antes de enviar cualquier archivo al repositorio), creo el repositorio Git con el comando "git init".
Una vez has inicializado el repositorio, podrás observar que se ha creado una carpeta en tu proyecto llamada ".git" . Si ves esa carpeta en tu proyecto es que el repositorio se ha inicializado correctamente y que ya tienes convertida esa carpeta en un repositorio de software Git
6. Describa el flujo para agregar un archivo simple al repositorio.
En tu computadora, mueve el archivo que deseas cargar a GitHub en el directorio local que se creó cuando clonaste el repositorio.
Abre la Git Bash.
Cambia el directorio de trabajo actual por tu repositorio local.
Prepara el archivo para confirmarlo para tu repositorio local.
Confirma el archivo que has preparado en tu repositorio local.
Sube los cambios en tu repositorio local a GitHub.
7. Describa el flujo para cambiar el archivo agregado y guardar los cambios en el repositorio.
Supongamos que añades un nuevo archivo a tu proyecto, un simple README. Si el archivo no existía antes y ejecutas git status, verás el archivo sin rastrear de la siguiente manera:
$ echo 'My Project' > README
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    README

nothing added to commit but untracked files present (use "git add" to track)
8. ¿Cómo hago para ignorar un archivo o carpeta?
creo en mi preyecto un archivo con el nombre .gitignore
9. Explique qué es un branch. Dé un pequeño ejemplo de cómo haría uno. 
En Git, es simplemente el apuntador a la rama local en la que tú estés en ese momento, en este caso la rama master ; pues el comando git branch solamente crea una nueva rama, pero no salta a dicha rama.
10. ¿Qué hago con `git add .`?
La forma más habitual de invocar el comando git-add es: git add 
Este comando añade al índice cualquier fichero nuevo o que haya sido modificado:
11. ¿Cómo cambiamos de un branch a otro?
Para moverse entre ramas usamos el comando "git checkout" seguido del nombre de la rama que queremos que sea la activa.
git checkout experimental
12. Investigue qué es Markdown y responda todas las preguntas anteriores en este lenguaje (con el nombre de archivo RESPUESTAS.md). Súbalo al repositorio.