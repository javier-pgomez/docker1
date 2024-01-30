# Ejercicios Docker

## Construcción de imagen
### A partir de la siguiente aplicación flask, se deberá realizar lo siguiente:

Creación de Dockerfile para generar una imagen docker que tenga la app embebida.
La imagen debe cumplir con los siguientes requisitos:

Crearse a partir de la imagen "python:3.7-alpine"

Debemos instalar mediante "apk add" los siguientes paquetes:

```gcc musl-dev linux-headers curl mysql-client mysql-dev```

Copiar el fichero "requirements.txt" y ejecutar "pip install -r" apuntando a ese mismo fichero

Copiar el fichero "app.py" en el directorio /app y que este directorio sea la zona de trabajo.

Exponer el puerto 5000

Contener las siguientes variables:

FLASK_APP=app.py

FLASK_ENV=development

FLASK_RUN_HOST=0.0.0.0

MYSQL_USER=patito

MYSQL_PASSWORD=patodegoma

MYSQL_HOST=mysql-db

MYSQL_DB=mysql-database

Nuestro comando de entrada de imagen debe ser "flask run"

## Subir imagen

Para subir nuestra imagen una vez creada mediante el comando "docker build" necesitaremos crear una cuenta en docker hub.

Cuando dispongamos de nuestra cuenta, es importante que el nombre que le demos a la imagen en local coincida con el nombre de nuestro usuario y el nombre de imagen que deseemos, por ejemplo, en mi caso mi usuario es "jaweewo" por lo que usaremos: ```docker build -t jaweewo/flask-app:latest .```

## Testear imagen

Una vez creada, independientemente de si la tenemos en dockerhub o solo en local, lanzamos un contenedor de esta imagen y probamos a acceder via web al puerto 5000.

Deberia daros un error de conexión a la BBDD.

## Continuación de proyecto en rama mysql