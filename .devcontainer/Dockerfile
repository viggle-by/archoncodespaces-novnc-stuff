FROM archlinux:latest

RUN pacman -Sy --noconfirm \
    bash \
    sudo \
    curl \
    vim \
    git \
    && pacman -Scc --noconfirm && pacman -S base-devel libglvnd libxkbcommon pixman gnutls jansson && git clone https://github.com/any1/wayvnc.git /workspaces/archoncodespaces-novnc-stuff/wayvnc && cd /workspaces/archoncodespaces-novnc-stuff/wayvnc && meson build
ninja -C build

RUN useradd -m -s /bin/bash codespace && echo "codespace ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && echo "codespace:gg" | chpasswd
USER codespace
WORKDIR /home/codespace
