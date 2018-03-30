# Docker Lumen Base Image

Forked from [malitta/docker-images](https://github.com/malitta/docker-images), updated to include php7.1

Lightweight image containing the bare necessities for running a [Lumen](https://lumen.laravel.com) app over HTTP/HTTPS. This is intended to be used as a base image for your app specific Dockerfiles. [Read this](https://github.com/malitta/docker-images/kb/extending-image.md) for a quick introduction on how this image can be extended to suit your app. 

## Contains

This is an extension of [jover/php-base](https://hub.docker.com/r/jover/php-base). In addition, this image contains:

- PHP extensions
	- mcrypt
	- mbstring

## Usage

#### Extending the Dockerfile

Create a `Dockerfile` and add other dependencies that your app requires. [See here]() for addons that you can use if you are planning to have a seperate Dockerfile for development.

```
FROM jover/lumen

RUN apt-get install -y php7.1-pgsql	

COPY . /var/www/
```

#### Running a container

Run the following command from the root of your application directory 

`docker run -dit -p 8080:80 -v $(pwd):/var/www --name mywebapp jover/lumen`

Visit `localhost:8080` from the browser and you should see your application.