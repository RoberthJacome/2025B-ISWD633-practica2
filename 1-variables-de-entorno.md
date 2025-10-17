# Variables de Entorno
### ¿Qué son las variables de entorno?
Valores dinámicos definidos en el sistema operativo que afectan el comportamiento de los programas y procesos, <br>
permitiendo que estos se configuren de manera diferente según el entorno de ejecución sin modificar el código fuente.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

docker run -d --name contenedor_tactico -e username=Roberth -e role=admin

<img width="1186" height="76" alt="image" src="https://github.com/user-attachments/assets/ca283a70-9005-42fe-8de6-98b0000eaf5b" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# docker run -d --name contenedor_tactico2 mysql:latest

### ¿El contenedor se está ejecutando?
# Por ahora no.

### Identificar el problema
# docker logs -n 10 contenedor_tactico2

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
docker run -d --name mysql_server -e MYSQL_ROOT_PASSWORD=123456 mysql:8

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 

### ¿Qué bases de datos existen en el contenedor creado?
<img width="1321" height="1419" alt="image" src="https://github.com/user-attachments/assets/36a7df7d-38df-41f6-ac40-f57b2cfe53df" />

