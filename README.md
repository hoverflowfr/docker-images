# Hoverflow Docker Images

Custom Docker images built to be reusable across all of our projects.

## List of the images of this repository

- [PHP 7.3 + Vapor CLI](/php/7.3-cli/vapor) - A CLI-only PHP 7.3 that comes with Composer and Vapor CLI pre-loaded

## How to use the Docker images

### Using an image from Docker Hub

All of our Docker images are available on [our organization profile](https://hub.docker.com/u/hoverflow).

### Building an image

Clone this repository, head to the folder of the image you want to build and execute the following command :

```
docker build -t [image name]:[image version] .
```

For example, if you want to build the **PHP 7.3 + Vapor CLI** image, execute the following :


```
cd php/7.3-cli/vapor
docker build -t php7.3-cli-vapor:latest .
```