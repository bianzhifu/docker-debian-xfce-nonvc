# docker-debian-xfce-nonvc


```
docker run -itd --name xfce --restart always \
    -p 5901:5901 \
    -p 6081:6081 \
    -e VNC_PASSWORD=youpassword \
    -e VNC_RESOLUTION=1920*1080 \
    -e VNC_COL_DEPTH=24 \
    bianzhifu/docker-debian-xfce-nonvc
```
