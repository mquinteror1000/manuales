#descargas #torrent #cli #tranmission 
# transmission_daemon
 instalacion
```
dnf install transmisison-daemon
systemctl enable transmission-daemon
systemctl status transmission-daemon
```
archivo de configuración
```bash
systemctl stop trasmission-daemon
vim /var/lib/transmission/coonfig/transmission-daemon/settings.json
```
Opciones de configuración
```json
"download-dir" : "/home/my_user/Downloads/downloaded_torrents"
"rpc-whitelist-enabled" : false
"rpc-autentication-required": true
"rpc-username": "my_username"
"rpc-password": "my_strong_password"
```
Agregar un archivo torrent
```bash
transmission-remote server:9091 -n "username:password" -a /route/to_your/file.torrent -w /home/my_user/Downloads/torrents
```