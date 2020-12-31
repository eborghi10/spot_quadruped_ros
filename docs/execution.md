# Execution

- [Remote connection](#remote-connection)
- [Running everything](#running-everything)

## Remote connection

```sh
ssh spot@spot-nvidia.local

sudo apt-get install tigervnc-scraping-server
vncpasswd
x0vncserver -passwordfile ~/.vnc/passwd -display :0

sudo apt-get install tightvncserver
vncserver :1 -geometry 1024x768 -depth 24

[VNC] spot-nvidia.local:1
```

- `xstartup` file:

```no-lang
#!/bin/sh
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
startxfce4 &

[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &
```

- TODO: Automatically execute server <https://forums.developer.nvidia.com/t/ubuntu-internal-error-when-selecting-desktop-sharing-in-settings/72163/3>
- TODO: Create dummy screen <https://askubuntu.com/a/463000>

## Running everything

```sh
# Software bringup
roslaunch spotmicro_config bringup.launch

# Joystick teleop
roslaunch champ_teleop teleop.launch
```
