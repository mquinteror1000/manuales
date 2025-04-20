#samba #servicio #samba 
### instalar samba
instalar el servidor
```bash
dnf install samba
````
Definir la carpeta a compartir
```bash
/home/myuser/data
```
permisos
```bash
chmod -R 0775 /home/myuser/data
chown -r myuser:myuser /home/myuser/data
```
Archivo de configuracion
```bash
[data]
        comment=data
        path=/home/mquinteror/data
        valid users=mquinteror
        read only = No
        browseable = Yes
        writable = Yes
        create mask = 0777
        directory mask= 0777

```
Habilitar los usuarios
```bash
smbpasswd -a myuser
smbpasswd -e myuser
```
permitir el servicio en el [[firewall_cmd_httpd]]firewall el servicio samba
habilitar el servicio[[service_status]]
```bash
systemctl status smb nmb
```
