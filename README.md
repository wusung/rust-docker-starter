# rust-docker-starter

This turtoial show how to create and develop a rust program with Docker without installing any rust environments.

## Start rust container

Create a cargo project with `cargo new` command
```shell
docker run -v $PWD:/src rust:alpine env USER=$USER cargo new /src/app
```


## Add a Dockefile

```
FROM rust:alpine

WORKDIR /usr/src/app
COPY ./app .

RUN cargo install --path .

CMD ["target/release/app"]
```

## Build 

```shell
Docker build -t rusty .
```


## Run

``` Run
docker run --rm --name rusty rusty
```
