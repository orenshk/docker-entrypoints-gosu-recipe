# docker-entrypoints-gosu-recipe
Simple example of using entrypoint in shell mode and gosu to drop root priviliges.

This container creates a user as root, then calls the `entrypoint.sh` script which runs `top` as a non-priviliged user. The idea is to use entrypoint.sh to run priviliged container config before dropping priviliges.

## build and run
docker build -t test-ep .
docker run -it --rm --name test test-ep
