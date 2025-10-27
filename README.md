# docker-angular-ci

A docker image for building, testing and deploying Angular applications to AWS.

## Build It
```
docker build -t keytelematics/docker-angular-ci:latest .
```

## Build On ARM Macs
```
docker buildx build --platform linux/amd64 -t keytelematics/docker-angular-ci:18 --push .
```

## Run It
```
docker run -v <your_code_path>:/tests keytelematics/docker-angular-ci bash -x /tests/<your_build_script>
```