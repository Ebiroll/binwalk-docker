# binwalk-docker

Docker container with all extra tools installed to get the most out of binwalk.


## Binwalk

https://github.com/ReFirmLabs/binwalk

https://github.com/ReFirmLabs/binwalk/blob/master/INSTALL.md




## Docker Hub

The original repo is automatically built by Docker Hub.

https://hub.docker.com/repository/docker/sheabot/binwalk


## Buiild command
To build the dockerfile with podman

podman build -T binwalk .

## Run

These commands mount the current working directory as a volume into the container at `/workspace` which is the $WORKDIR in the container. This allows binwalk to operate on files in the current directory.

Podman
```
docker run -it --rm -v "$(pwd):/workspace" -w /workspace binwalk /bin/bash
```


## Install

The `binwalk.sh` script can be installed somewhere on $PATH to make running this containerized version of binwalk transparent.

```
install -m 0755 binwalk.sh /usr/local/bin/binwalk
```

Example:

```
binwalk -e firmware.bin
```
