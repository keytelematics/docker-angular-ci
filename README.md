# docker-angular-ci

A docker image for building, testing and deploying Angular applications to AWS.

## Base Image

This image is built on `eclipse-temurin:8-jre-noble` (OpenJDK 8 on Ubuntu 24.04 LTS). It previously used `openjdk:8-jre`, but that image was deprecated and its tags removed from Docker Hub, so builds against it now fail outright. `eclipse-temurin` is the maintained successor to the official `openjdk` images, and the `-noble` variant pins the underlying Ubuntu release so the base doesn't silently shift on future pulls.

## Build It
```
docker build -t keytelematics/docker-angular-ci:latest .
```

## Build On ARM Macs
```
docker buildx build --platform linux/amd64 -t keytelematics/docker-angular-ci:node24 --push .
```

## Run It
```
docker run -v <your_code_path>:/tests keytelematics/docker-angular-ci bash -x /tests/<your_build_script>
```