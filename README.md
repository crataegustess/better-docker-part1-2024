# docker-deep-dive-2024
## Docker deep dive workbook

Welcome to your Docker deep dive course. You will find exercises and follow up questions in here.
The course will work best if we follow it through together so if you can curb your excitement for reading ahead.

## Helpful tips & references

- Base images can be found here: [https://hub.docker.com/](https://hub.docker.com/)
- Docker build documentation: [https://docs.docker.com/reference/cli/docker/build-legacy/](https://docs.docker.com/reference/cli/docker/build-legacy/)
- Docker run documentation: [https://docs.docker.com/reference/cli/docker/container/run/](https://docs.docker.com/reference/cli/docker/container/run/)
- Docker file syntax reference: [https://docs.docker.com/reference/dockerfile/](https://docs.docker.com/reference/dockerfile/) 

Building an image
For a basic build, adapt this command to match the exercise
`docker build -t docker-deep-dive/{exercise}/{original|better} -f {filename} .`

e.g.
```shell
docker build -t docker-deep-dive/ex2/original -f Dockerfile.original .
```
Listing your built images

```shell
docker images
docker images | grep docker-deep-dive/
```

Running up your images into containers

The basic command would be

```shell
docker run --name exercise2 --rm docker-deep-dive/ex2/original
```

However, different types of dockerfile & image may prompt more complex versions (spoilers!)

## Running docker on a mac

Due to licensing concerns with Docker Desktop (it's no longer for commercial use without a paid user account) it's worth looking into alternatives. [Rancher desktop](https://rancherdesktop.io/) can be installed using Kandji and will be kept up to date with Kandji controlled updates (where available). It is command-line heavy but we will be working with the docker cli for this course anyway.
