## Docker

1. To create Docker
`docker build -f ./docker/Dockerfile --rm -t mmselfsup:torch1.9.0-cuda11.1-cudnn8 .`

2. To start running a Docker
`docker run --gpus all --shm-size=8g -it mmselfsup:torch1.10.0-cuda11.3-cudnn8 /bin/bash`
Note: must specify `--gpus all`
`docker run --gpus all --shm-size=8g --cap-add=SYS_ADMIN -it -v /media/ntu/volume2/s121md302_06/data:/mmselfsup/data --network host mmself`

3. Run Docker with admin permission
`docker run --gpus all -it --cap-add=SYS_ADMIN deep-colorization:latest /bin/bash`

4. Limit GPU power in Docker
`nvidia-smi -i 0 -pl 180`
