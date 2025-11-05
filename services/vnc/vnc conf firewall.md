#vnc #service #remote_desktop  #firewall-cmd 
Agregar VNC al firewall
```bash 
sudo firewall-cmd --add-service=vnc-server --permanent 
sudo firewall-cmd --reload
```
