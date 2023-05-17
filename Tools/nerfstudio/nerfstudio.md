# NeRFStudio

## Docker Install

ref: [Use docker image](https://docs.nerf.studio/en/latest/quickstart/installation.html#use-docker-image)

ref: [dromni/nerfstudio](https://hub.docker.com/r/dromni/nerfstudio/tags)

```
docker pull dromni/nerfstudio:0.2.2
```

**启动docker**
```
docker run --gpus all -v /home/rtx/workspace/docker_workspace:/workspace/ -v /home/rtx/.cache/:/home/user/.cache/ -p 7007:7007 --rm -it --shm-size=12gb dromni/nerfstudio:0.2.2 
```

nerfstudio的docker版本默认支持colmap






