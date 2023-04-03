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

RUN wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN echo "deb [arch=amd64] https://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list
RUN apt-get update && \
    apt-get install -y google-chrome-stable && \
    apt-get clean -y

ENTRYPOINT ["/entrypoint.sh"]