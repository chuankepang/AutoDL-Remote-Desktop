# AutoDL-Remote-Desktop
Remote Desktop for AutoDL with VNC (Virtual Network Computing) and SSH

## Step.1

```

# 安装基本的依赖包
apt update && apt install -y libglu1-mesa-dev mesa-utils xterm xauth x11-xkb-utils xfonts-base xkb-data libxtst6 libxv1

# 安装libjpeg-turbo和turbovnc (#为官方教程，目前因文件服务器关闭实效)
# export TURBOVNC_VERSION=2.2.5
# export LIBJPEG_VERSION=2.0.90
# wget http://aivc.ks3-cn-beijing.ksyun.com/packages/libjpeg-turbo/libjpeg-turbo-official_${LIBJPEG_VERSION}_amd64.deb
# wget http://aivc.ks3-cn-beijing.ksyun.com/packages/turbovnc/turbovnc_${TURBOVNC_VERSION}_amd64.deb
# dpkg -i libjpeg-turbo-official_${LIBJPEG_VERSION}_amd64.deb
# dpkg -i turbovnc_${TURBOVNC_VERSION}_amd64.deb
# rm -rf *.deb
sudo apt install libjpeg-turbo8 libjpeg-turbo8-dev
sudo apt install turbovnc

# 启动VNC服务端，这一步可能涉及vnc密码配置（注意不是实例的账户密码）。另外如果出现报错xauth未找到，那么使用apt install xauth再安装一次
rm -rf /tmp/.X1*  # 如果再次启动，删除上一次的临时文件，否则无法正常启动
USER=root /opt/TurboVNC/bin/vncserver :1 -desktop X -auth /root/.Xauthority -geometry 1920x1080 -depth 24 -rfbwait 120000 -rfbauth /root/.vnc/passwd -fp /usr/share/fonts/X11/misc/,/usr/share/fonts -rfbport 6006

# 检查是否启动，如果有vncserver的进程，证明已经启动
ps -ef | grep vnc

```

## Step.2
```

Windows：https://autodl-public.ks3-cn-beijing.ksyuncs.com/tool/AutoDL-SSH-Tools.zip
ssh

```

## Step.3
```

TurboVNC-2.2.5
127.0.0.1:6006

```
