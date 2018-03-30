# Docker PHP Base Image

Forked from [malitta/docker-images](https://github.com/malitta/docker-images), updated to include php7.1

Lightweight image containing the bare necessities for running a PHP app over HTTP/HTTPS. This is intended to be used as a base image for your app specific Dockerfiles. See [docker-images](https://github.com/malitta/docker-images) repository for extensions of this image. Or [read this](https://github.com/malitta/docker-images/kb/extending-image.md) for a quick introduction on how this image can be extended to suit your app. 

## Contains

- Ubuntu ([rolling](https://hub.docker.com/_/ubuntu/))
	- Supervisor
	- Vim
- PHP 7.1
	- Composer
- Apache 2.4 (HTTP/1.1)

## Usage

Note: The default virtualhost file points to `/var/www/public`

#### Extending the Dockerfile

Create a `Dockerfile` and add other dependencies that your app requires. [See here](/) for addons that you can use if you are planning to have a seperate Dockerfile for development.

```
FROM jover/php-base

RUN apt-get install -y php7.1-pgsql	

COPY . /var/www
```

#### Running a container

`docker run -dit -p 8080:80 -v $(pwd):/var/www --name mywebapp jover/php-base`

Visit `localhost:8080` from the browser and you should see the _PHP Version Info_ page.