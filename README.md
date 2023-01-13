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

```
$ docker-compose up
```

Para conectar el proyecto a postgres vamos a Database(PyCharm Professional Edition) pulsamos el + 
--> Data Source --> PostgreSQL. Se nos abrirá una pestaña en la que debemos añadir el puerto correspondiente 
al docker-compose iniciado con la contraseña y el usuario de postgres añadidos anteriormente. Hacemos un test 
connection para comprobar si funciona, si es así aplicamos los cambios.

![Captura test de conexión](https://user-images.githubusercontent.com/91198318/212316885-cec47e95-c041-473a-8357-d24bc0fbb2de.png)

Debemos comprobar que el puerto utilizado, en nuestro caso el ```5432```, esté libre y no haya ningún servicio ejecutándose en él. Para ello podemos utilizar los siguientes comandos:

```$ ps aux``` : Una variante del comando ps que muestra información detallada sobre todos los procesos en el sistema. La opción "a" incluye todos los procesos del sistema, no solo los que son propiedad del usuario actual. La opción "u" muestra información de usuario para cada proceso, como el tiempo de CPU y el uso de memoria. Y la opción "x" incluye procesos que no están asociados con un terminal.

```$ netstat``` : Nos muestra información sobre las conexiones de red y las estadísticas de protocolo de un sistema.

```$ service stop``` o ```$ service start``` : Se utilizan para controlar el estado de los servicios que se están ejecutando en el sistema, el primero detiene un servicio específico y el segundo lo inicia.



