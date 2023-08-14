# tp_seminario_contenedores_07-08-2023
## Tp1 
## 1)- Creamos una carpeta contenedor, esta tendra dos carpetas una de php y otra de la base de datos

## 2)- creamos el contenedor de php este es el comando:
##      docker run -d -p 8088:80 -v C:\Users\gstnr\OneDrive\Escritorio\contenedores-repaso\php:/var/www/html php:apache-bullseye ---> posicionarse en la carpeta del archivo php 
     
## 3)- creamos el contenedor de mysl con este comando:
##     docker run -d -e MYSQL_ROOT_PASSWORD=root1 -v C:\Users\gstnr\OneDrive\Escritorio\contenedores-repaso\php:/docker-entrypoint-initdb.d -v C:\Users\gstnr\OneDrive\Escritorio\contenedores-repaso\sql:/var/lib/mysql mysql:debian --> posicionarse en carpeta contenedora de las dos carpetas php y mysql
    
## 4)- Luego, ejecutar el comando docker exec -it nombre-contenedor-php bash -> esto nos permitirá abrir el terminal del contenedor php para colocar los siguientes dos comandos:
## docker-php-ext-install mysqli
## docker-php-ext-enable mysqli

## en el archivo php, colocaremos la ip del servidor de mysql que podemos buscar utilizando el comando: docker inspect -f "{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}" ## nomre-contenedor-mysql

## este comando nos dará la ip que debemos reemplazar en el archivo php en la línea donde dice $servername="localhost"

## Una vez que ejecutemos estos dos comandos y hayamos cambiado el valor de $servername por la ip en el archivo php, reiniciaremos los contenedores y luego podremos abrir en el navegador la ## dirección http://localhost:8088/ para visualizar la página.
