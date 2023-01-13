# Odoo

## Guía instalación Postgres


Creamos un proyecto en PyCharm que contenga un archivo "docker-compose.yml", este archivo debe estar 
configurado para una imagen PostgresSQL:

```
version: '3.1'
services:
  db:
    image: postgres:13
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=odoo
      - POSTGRES_USER=odoo
    ports:
      - "5432:5432" 
```

Después en la terminal del IDE escribimos el siguiente comando para iniciar el servicio:

{% filename %}docker-compose up{% endfilename %}

Para conectar el proyecto a postgres vamos a Database(PyCharm Professional Edition) pulsamos el + 
--> Data Source --> PostgreSQL. Se nos abrirá una pestaña en la que debemos añadir el puerto correspondiente 
al docker-compose iniciado con la contraseña y el usuario de postgres añadidos anteriormente. Hacemos un test 
connection para comprobar si funciona, si es así aplicamos los cambios.

![Captura test de conexión](https://user-images.githubusercontent.com/91198318/212316885-cec47e95-c041-473a-8357-d24bc0fbb2de.png)



