### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
# COMPLETAR
docker network create mi_red_postgres

docker run -d --name contenedor-postgres \
-e POSTGRES_PASSWORD=123456 \
-e POSTGRES_USER=admin \
-e POSTGRES_DB=info \
--network mi_red_postgres \
postgres:15-alpine3.21

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

# COMPLETAR
docker run -d --name cliente-pgadmin \
-e PGADMIN_DEFAULT_EMAIL=admin@admin.com \
-e PGADMIN_DEFAULT_PASSWORD=123456 \
--network mi_red_postgres \
-p 8080:80 \
dpage/pgadmin4

La figura presenta el esquema creado en donde los puertos son:

- a: 8080 = Puerto externo del cliente pgAdmin (para acceder desde el navegador).
- b: 80 = Puerto interno del contenedor pgadmin4.
- c: 5432 = Puerto interno del contenedor de postgres.

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN
<img width="1912" height="811" alt="image" src="https://github.com/user-attachments/assets/54d09fa3-7c35-4bdf-b254-5a4c9f24547b" />


### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

## Desde el servidor postgresl
CREATE DATABASE info;

\c info;

CREATE TABLE personas (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100)
);

INSERT INTO personas (nombre) VALUES
('Roberth Jácome'),
('Juan Pérez');

### Acceder al servidor

### Conectarse a la base de datos info
# COMPLETAR
docker exec -it contenedor-postgres psql -U admin -d info

### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
SELECT * FROM personas;

<img width="971" height="642" alt="image" src="https://github.com/user-attachments/assets/651d8440-49a6-4b71-96b0-ee4815a811d4" />

