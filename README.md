# GOLANG ENVIRONMENT BUILDER - REPOSITORY <h1> 
 
[![build](https://img.shields.io/github/workflow/status/lyscm/environments-golang/environment-golang%20-%20ci?logo=github)](https://github.com/lyscm/environments-golang/blob/master/.github/workflows/build-action.yml)
[![repo size](https://img.shields.io/github/repo-size/lyscm/environments-golang?logo=github)](https://github.com/lyscm/environments-golang)
[![package](https://img.shields.io/static/v1?label=package&message=golang&color=yellowgreen&logo=github)](https://github.com/lyscm/environments-golang/pkgs/container/environments%2Fgolang)

## Initiate package(s): <h2> 

Set parameters:

***Bash:***
```bash
OWNER=lyscm
CONTAINER_NAME=golang
TAG=ghcr.io/lyscm/environments/golang
```

***Powershell:***
```powershell
$OWNER="lyscm"
$CONTAINER_NAME="golang"
$TAG="ghcr.io/lyscm/environments/golang"
```

Remove any existing container:

```bash
docker stop $CONTAINER_NAME
docker rm $CONTAINER_NAME
docker pull $TAG
```

Run container:

```bash
docker run \
    -d \
    --name $CONTAINER_NAME \
    --restart unless-stopped \
    -v /var/run/docker.sock:/var/run/docker-host.sock \
    --net=host \
    --cap-add=SYS_PTRACE \
    --security-opt seccomp:unconfined \
    --privileged \
    $TAG
```