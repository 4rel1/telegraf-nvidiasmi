# telegraf-nvidiasmi
Docker container for nvidia gpu monitoring with Telegraf

## Disclaimer
This `Dockerfile` is the merge between the two used by [nvidia](https://gitlab.com/nvidia/cuda/tree/ubuntu18.04/10.1) and [telegraf](https://github.com/influxdata/influxdata-docker/blob/09d9c5d6d85ff1ffb129b40fd8b9b52ddb55c3ba/telegraf/1.8/Dockerfile) to craft their containers. Is nothing more than a PoC. Today it works, do not expect that tomorrow it will. 

## Build
To build your local version
```bash
docker build . -t telegraf-nvidiasmi
```
## Pull
Pull the upstream version on dockerhub
```bash
docker pull mconcas/telegraf-nvidia
```

## Usage
Start Telegraf agent with the nvidia runtime, and monitor your local nvidia GPU
```bash
docker run -d [--net=possible-net] --hostname=$HOSTNAME --name=telegraf --runtime=nvidia -v $PWD/telegraf.conf:/etc/telegraf/telegraf.conf:ro mconcas/telegraf-nvidia-runtime telegraf
```

