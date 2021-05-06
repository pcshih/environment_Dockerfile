# base image
FROM ubuntu:bionic

# to handle tzdata select zone problem
ENV DEBIAN_FRONTEND="noninteractive"

# to install some package(setup environment)
RUN \
apt-get update -y && \
apt-get install -y zsh wget git nano tzdata && \
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O - | zsh || true && \
apt-get install -y software-properties-common && \
add-apt-repository ppa:deadsnakes/ppa && \
apt-get update -y && \  
apt-get install -y python3.6 python3.6-dev python3-pip && \
apt-get install -y python3-opencv && \
ln -sf /usr/share/zoneinfo/Asia/Taipei /etc/localtime && \
dpkg-reconfigure -f noninteractive tzdata && \
pip3 install --upgrade pip && \
pip3 install torch==1.8.1+cpu torchvision==0.9.1+cpu torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html