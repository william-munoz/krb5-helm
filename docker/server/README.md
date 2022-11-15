# Kerberos Server Image

I am using Rancher Desktop as a local environment.

## Docker Hub Authentication

```
docker login -u hachikoapp
Enter Password: ENTER_TOKEN
Login Succeeded
```

## Build the Image

```
cd docker/server/
docker build --platform linux/amd64 -t kuberos:0.0.3 .
```

## List the Imgage

```
docker image ls
REPOSITORY                TAG       IMAGE ID        CREATED               PLATFORM       SIZE         BLOB SIZE
kuberos                   0.0.1     a57a1f66945d    About a minute ago    linux/amd64    431.0 MiB    143.9 MiB
```

## Tag the Image

```
docker tag kuberos:0.0.3 hachikoapp/kuberos:0.0.3
docker tag kuberos:0.0.3 hachikoapp/kuberos:latest
```

## Push the Image

```
docker push hachikoapp/kuberos:0.0.3
docker push hachikoapp/kuberos:latest
```
