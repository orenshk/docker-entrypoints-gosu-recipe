# docker-entrypoints-gosu-recipe
Simple example of using entrypoint in shell mode and gosu to drop root priviliges.

This container creates a user as root, then calls the `entrypoint.sh` script which runs `top` as a non-priviliged user. The idea is to use entrypoint.sh to run priviliged container config before dropping priviliges.

It uses the shell form of the ENTRYPOINT keyword so that command line arguments to docker run are ignored, see [docker reference](https://docs.docker.com/engine/reference/builder/#shell-form-entrypoint-example)

## build and run

```sh
docker build -t test-ep .
docker run -it --rm --name test test-ep
```
