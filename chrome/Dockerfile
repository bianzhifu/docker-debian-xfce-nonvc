FROM bianzhifu/docker-debian-xfce-nonvc:bullseye

LABEL description="Debian Xfce4 chrome desktop environment." \
    author="bianzhifu, <bianzhifu@foxmail.com>"

WORKDIR /

ENV DEBIAN_FRONTEND=noninteractive \
    NO_VNC_PORT=6081 \
    VNC_PORT=5901 \
    VNC_PASSWORD=1234 \
    DISPLAY=:1 \
    VNC_RESOLUTION=1280x800 \
    VNC_COL_DEPTH=24

EXPOSE $VNC_PORT $NO_VNC_PORT

RUN apt-get update && \
    apt-get install fonts-liberation libu2f-udev xdg-utils -y && \
    apt-get clean -y

RUN wget -qO- https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb -O /google-chrome-stable_current_amd64.deb
RUN dpkg -i /google-chrome-stable_current_amd64.deb
RUN rm -f /google-chrome-stable_current_amd64.deb

ENTRYPOINT ["/entrypoint.sh"]