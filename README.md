# 🚚 Comandos de Docker 🚚

Estos comandos son los más básicos y principales para crear imagenes y contenedores en Docker.

## 💿 Descargar imagenes en Docker 

### Descarga una versión específica

```sh
docker pull <name_image>:<version>
docker pull node:16 #Ejemplo
```

### Para ver las imagenes que existen en Docker

```sh
docker images
```

### Eliminar una imagen específica según la versión de la imágen
```sh
docker image rm <name_image>:<version> 
docker image rm node:16 #Ejemplo
```

## 📦 Para contenedores

### Comando simplificado para crear un contenedor con su nombre

```sh
docker create <name_container>
docker create mongo #Ejemplo
```

### Comando completo para crear un contenedor con su nombre

```sh
docker container create <name_container>
docker container create mongo #Ejemplo
```

### Comando para ejecutar el contenedor con el id

```sh
docker start <id_container>
docker start 5j3b4u34uasdasd #Ejemplo
```

### Para verificar si está ejecutándose el contenedor

```sh
docker ps
```

### Comando para detener el contenedor

```sh
docker stop <id_container>
docker stop 5j3b4u34uasdasd #Ejemplo
```

### Muestra todos los contenedores que existen en nuestra máquina

El parámetro <code>-a</code> significa todos los contenedores

```sh
docker ps -a
```

### Comando para eliminar el contenedor

```sh
docker rm <name_container>
docker rm stock_container #Ejemplo
```

### Comando para crear el contenedor con su nombre y la imágen

El parámetro <code>--name</code> significa agregar el nombre al contenedor

```sh
docker create --name <name_container> <name_image>
docker create --name mongoDB mongo #Ejemplo
```

## 📍 Mapeo de Puertos en Docker

### Comando para crear el contenedor con puertos específicos

El parámetro <code>-p</code> significa los puertos para la máquina anfitrión y el contenedor

```sh
docker create -p<port_host>:<port_container> --name <name_container> <name_image>

docker create -p27017:27017 --name mongoDB mongo #Ejemplo
```

## 🔊 Logs en Docker

### Comando para ver todos los logs

```sh
docker logs <name_container>

docker logs mongoDB #Ejemplo
```

### Comando para seguir los logs en ejecución

El parámetro <code>--follow</code> significa mostrar los logs en tiempo real de ejecución del contenedor

```sh
docker logs --follow <name_container>

docker logs --follow mongoDB #Ejemplo
```

## 🏃 Utilización de Docker Run

El parámetro <code>-d</code> significa omitir los logs en ejecución del contenedor

```sh
docker run -d --name <name_container> -p<port_host>:<port_container> <name_image>

docker run -d --name mongoDB -p27018:27017 mongo #Ejemplo
```

## 🔐 Creación de un contenedor con variables de entorno

El nombre de las variables de entorno cambian segun la imagen a configurar al lanzar el contenedor

El parametro <code>-e</code> se refiere a una variable de entorno que se le pasara al contenedor.

En este caso las variables de entorno es de acuerdo a la imagen de MongoDB.

```sh
docker create --name <name_container> -p<port_host>:<port_container> -e <NAME_VARIABLE> <name_image>

docker create --name mongoDB -p27018:27017 -e MONGO_INITDB_ROOT_USERNAME=mario -e MONGO_INITDB_ROOT_PASSWORD=12345678 mongo #Ejemplo
```

