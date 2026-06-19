#service #vnc #remote_desktop


## Instalacion de tigervnc
```bash
dnf install tigervnc-server
```

Configurar el display(s) para el usuaPrio(s)
```bash
sudo vim /etc/tigervnc/vncserver.users
```

```txt
# :2=andrew
# :3=lisa
:1=myusername
```
Agregar password de conexión vnc al usuario
```bash
su -l myuser
smbpasswd
#***
#***
# viewonly password -> no
```

Archivo de configuracion en el $HOME del usuario
```bash
vim ~/.vnc/config
```

```txt
session=gnome-xorg
geometry=1920x1080
```

Habilitar el servicio en el firewall

```bash 
sudo firewall-cmd --add-service=vnc-server --permanent 
sudo firewall-cmd --reload
```

Finalmente
Iniciar el servicio de manera manual 
o 
Configurar vncservier en systemd [[systemd_unit vncserver]]
## Inicio manual
```
vncserver -fg :1
```