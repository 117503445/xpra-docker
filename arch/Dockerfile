FROM greyltc/archlinux-aur

RUN pacman -Syu --noconfirm xorg-server-xvfb fluxbox
# RUN echo "Server = https://mirrors.ustc.edu.cn/archlinux/\$repo/os/\$arch" > /etc/pacman.d/mirrorlist
RUN aur-install xpra-git

WORKDIR /workspace/
COPY entrypoint.sh entrypoint.sh
ENTRYPOINT ["./entrypoint.sh"]