# detectron2
    docker run --gpus all -it \
    --shm-size=8gb --env="DISPLAY" \
    --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
    --name=detectron2 detectron2:v0
    
# tf2.1.0
    docker run --gpus all -it \
    --shm-size=16gb \
    --env="DISPLAY" \
    --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
    --volume /:/host \
    --name=tf2.1.0 \
    tensorflow/tensorflow:2.1.0-gpu-py3

# dependencies
## cuda
    apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/3bf863cc.pub 
## apt
    apt update && apt upgrade -y
    apt install -y git zsh curl nano gedit python3-pip python-pip
    pip3 install -U pip
#### ohmyzsh
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    cat /host/home/z/.oh-my-zsh/themes/max.zsh-theme > /root/.oh-my-zsh/themes/max.zsh-theme
### CONDA
#### install
    https://www.anaconda.com/products/distribution
#### copy from local to docker
    cp /host/home/z/Downloads/Anaconda3-2022.05-Linux-x86_64.sh .
