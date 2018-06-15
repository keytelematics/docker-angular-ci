# docker-angular-ci

A docker image for building, testing and deploying Angular applications to AWS.

## Build It
```
docker build -t keytelematics/docker-angular-ci .
```

## Run It
```
docker run -v <your_code_path>:/tests keytelematics/docker-angular-ci bash -x /tests/<your_build_script>
```