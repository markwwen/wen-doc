# aws gpu instance setting

## Instance setting
1. Install the nvidia driver
    - The nvidia driver should be nvidia 367.
2. Install the docker
3. Install the nvidia docker
4. run a container (load the `/home/ubuntu/projects` directory into it)
    ```
    nvidia-docker run -v /home/ubuntu/projects:/home/ubuntu/projects -it [image name] /bin/bash
    # more specificly
    nvidia-docker run -v /home/ubuntu/projects:/home/ubuntu/projects -it --rm tensorflow/tensorflow:latest-gpu-py3 /bin/bash
    ```
5. use this command to watch the gpu
    ```
    watch -n 0.5 nvidia-smi
    ```