# Comandos de Docker 

Estos siguientes comandos son los más básicos y principales para crear imagenes y contenedores en Docker.

## Descargar Imagen de Docker

### Descarga una version específica

```sh
docker pull <name_image>:<version>
docker pull node:16 #Ejemplo
```

### Para ver las imagenes que existen en docker

```sh
docker images
```

### Eliminar una imagen especifica segun la version de la imagen
```sh
docker image rm <name_image>:<version> 
docker image rm node:16 #Ejemplo
```

## Para contenedores

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

### Para verificar si esta ejecutandose el contenedor
```sh
docker ps
```

### Comando para detener el contenedor
```sh
docker stop <id_container>
docker stop 5j3b4u34uasdasd #Ejemplo
```

### Muestra todos los contenedores que existen en nuestra maquina

```sh
docker ps -a
```

### Comando para eliminar el contenedor

```sh
docker rm <name_container>
docker rm stock_container #Ejemplo
```

### Comando para crear el contenedor con su nombre y la imagen

```sh
docker create --name <name_container> <name_image>
docker create --name mongoDB mongo #Ejemplo
```

