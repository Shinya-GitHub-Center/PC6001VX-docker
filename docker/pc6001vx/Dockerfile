FROM debian:stable-slim
ARG USERNAME=default
ARG GROUPNAME=default
ARG UID=1000
ARG GID=1000
RUN groupadd -g $GID $GROUPNAME && \
    useradd -m -s /bin/bash -u $UID -g $GID $USERNAME
RUN usermod -aG audio $USERNAME
WORKDIR /home/$USERNAME
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Tokyo
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y vim less tree jq && \
    apt-get install -y build-essential libx11-dev mesa-common-dev libopengl-dev \
    libsdl2-dev qtcreator qt6-base-dev qt6-multimedia-dev \
    qt6-5compat-dev libavformat-dev libavcodec-dev libswscale-dev
WORKDIR /home/$USERNAME/workdir
