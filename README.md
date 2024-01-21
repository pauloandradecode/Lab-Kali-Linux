# Lab-Kali-Linux

## Labs

### Lab 1: Crea la imagen

```bash
docker build -t username/container_name:version .
```

Esto creara el contenedor de Kali linux en un ambiente aislado al de tu equipo.

### Lab 2: Crea el contenedor

```bash
docker network create pentest
docker run -it --name kali --network pentest -h kali paulo866/kali-custom:0.0.1
```

### Lab 3: Ingresa al contenedor

Ingresa al contenedor del servidor esclavo.-

```bash
docker exec -it kali bash
```

## Docker

### Crear imagen

Para crear la imagen de Kali personalizada, utilizamos el siguiente comando.-

```bash
docker build -t kali-custom -f ./Dockerfile .
```

Agregar la imagen de Kali al repositorio local.-

```bash
docker tag kali-custom:0.0.1 paulo866/kali-custom:0.0.1
```

> Donde paulo866 es el nombre de usuario del repositorio y kali-custom es el nombre de la imagen.

Agregamos un comentario a la imagen de kali.-

```bash
docker commit -m "Comentario" kali-custom:0.0.1 paulo866/kali-custom:0.0.1
```

Subir la imagen de Kali al repositorio local.-

```bash
docker push paulo866/kali-custom:0.0.1
```

> Donde paulo866 es el nombre de usuario del repositorio y kali-custom es el nombre de la imagen.

### Crear y correr contenedor

Para crear y correr el contenedor de Jenkins Master utilizamos el siguiente comando.-

```bash
docker compose up -d
```
