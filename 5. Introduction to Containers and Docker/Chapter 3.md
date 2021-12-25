# Docker Images
A Docker image is built up from a series of layers

Each layer represents an instruction in the image's Dockerfile.

Each layer excepts the very last one is read-only

# Docker Volumes


    # -v or --volume
    docker run -d --name=devtest -v devtest-vol:app nginx:latest

    # --mount
    docker run -d --name=devtest2 --mount source=devtest2-vol,target=/app nginx:latest

    docker ps

    docker volume inspect devtest-vol



# Docker Networks