FROM archlinux:latest

RUN pacman -Sy --noconfirm \
    bash \
    sudo \
    curl \
    vim \
    git \

RUN useradd -m -s /bin/bash codespace && echo "codespace ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && echo "codespace:gg" | chpasswd
USER codespace
WORKDIR /home/codespace
