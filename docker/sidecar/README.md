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
cd docker/sidecar/
docker build --platform linux/amd64 -t krb_sidecar:0.0.5 .
```

## List the Imgage

```
docker image ls
REPOSITORY                TAG       IMAGE ID        CREATED               PLATFORM       SIZE         BLOB SIZE
kuberos                   0.0.1     a57a1f66945d    About a minute ago    linux/amd64    431.0 MiB    143.9 MiB
krb_sidecar               0.0.1     4e9c74c25af6    27 seconds ago    linux/amd64    391.7 MiB    134.9 MiB
```

## Tag the Image

```
docker tag krb_sidecar:0.0.5 hachikoapp/krb_sidecar:0.0.5
docker tag krb_sidecar:0.0.5 hachikoapp/krb_sidecar:latest
```

## Push the Image

```
docker push hachikoapp/krb_sidecar:0.0.5
docker push hachikoapp/krb_sidecar:latest
```
