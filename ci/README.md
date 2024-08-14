# CI pipeline

## Ejecución del proyecto: devsecops-web-scaffolding-poc

## Pipeline

el pipeline en github Actions para la app de react la plantee de la siguiente forma basado en su ejecución y compilación

Ejecución:

- **on push branches paths:**  Al detectarse un push, este ejecutará una rama automaticamente si las ramas mencionadas se encuentran ahí y si el path afectado fue "src/" 

- **pull-request:** Al igual que on push, si este detecta que un pull request está abierto (opened), este se ejecutará de forma automatica en las ramas mencionadas (synchronize) y si tambien el path afectado es "src/"

## CI flow

Jobs:

- environment_definition: El Job esta encargado de asignar el entorno en que se está trabajando en base a la rama ejecutada, dependiendo el tipo de evento (event_type) y rama (ref_name) este asignara un valor en el output del job

-  Build App: contiene las tareas necesarias para descargar el repositorio, instalar las dependencias, realizar la ejecución de pruebas unitarias, realizar un escaneo de vulnerabilidades, ejecutar eslint para arreglar problemas en el codigo, crear un archivo compilado, subir un artefacto de los resultados de trivy y compilado.

el escaneo de vulnerabilidades con trivy scan romperá el pipeline si encuentra una vulnerabilidad critica en el repositorio

- el archivo de subida de trivy es unico y se va a mostrar en el pipeline como un adjunto

- al igual que el archivo de subida de trivy, el de compilación abarcará todo el contenido de la carpeta `build`