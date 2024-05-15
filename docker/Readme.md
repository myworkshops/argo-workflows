# Guía de Docker y Minikube para la imagen `whalesay`

Este archivo README describe los pasos para construir una imagen de Docker personalizada utilizando el archivo `Dockerfile.whalesay` y cargarla en un entorno Minikube.

## Paso 1: Construir la imagen Docker

Construye la imagen Docker usando el siguiente comando. Asegúrate de estar en el directorio raíz de tu proyecto donde docker/Dockerfile.whalesay está ubicado.

```bash
docker build --platform linux/amd64 -f docker/Dockerfile.whalesay -t whalesay:latest .
```

Este comando construye una imagen Docker con la etiqueta whalesay:latest utilizando el archivo especificado en el directorio docker.

## Paso 2: Cargar la imagen en Minikube

Una vez que la imagen está construida, el siguiente paso es cargar esta imagen en tu clúster Minikube. Esto te permitirá usar la imagen directamente sin necesidad de un registro de Docker. Utiliza el siguiente comando para cargar la imagen en Minikube:

```bash
minikube image load whalesay:latest
```

## Paso 3: Verificar la imagen en Minikube

Para asegurarte de que la imagen se ha cargado correctamente en Minikube, puedes listar las imágenes disponibles en Minikube con el siguiente comando:

```bash
minikube image ls
```
Busca whalesay:latest en la lista para confirmar que está allí.
