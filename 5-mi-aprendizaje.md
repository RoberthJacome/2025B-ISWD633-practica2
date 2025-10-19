# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Antes:
Pensaba que los contenedores no necesitaban parámetros adicionales para inicializarse.

No comprendía como podían interactuar los contenedores en una misma computadora.

Mi análisis de puertos para hacer que interactue mi computadora con los contenedores era bajo.


Después:
Aprendí que cada tipo de contenedor puede tener variables de entorno para ser creado, algo que también le aporta seguridad.

Comprendí como interactuan los contenedores a través de puertos.

Comprendí los tipos de redes que se pueden crear en una misma ccomputadora, además de sus diferencias y operaciones.


Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).
Los Docker Secrets son una característica de Docker Swarm que permite almacenar y distribuir datos confidenciales de forma segura a los contenedores que los necesitan.

En lugar de poner contraseñas o claves directamente:

En variables de entorno (ENV) o dentro de un archivo en la imagen (inseguro) los secrets permiten que esos datos se almacenen cifrados y se entreguen solo a los servicios autorizados, en memoria (no en disco).

Creación del secreto:

Se guarda el dato sensible (por ejemplo, una contraseña) dentro del gestor de secretos del nodo manager de Swarm.

Asignación del secreto a un servicio:
Se indica qué contenedores pueden acceder al secreto.

Montaje en el contenedor:
Docker monta el secreto dentro del contenedor como un archivo temporal en /run/secrets/.

Uso en la aplicación:
La aplicación puede leer ese archivo (no una variable de entorno) para obtener el valor secreto.
