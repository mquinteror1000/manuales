## Instalación en fedora
Instalación
```bash
dnf install syncthing
```
Configurar el servicio en la sesión de usuario , Desaconsejado usar root
 ```bash
systemctl --user enable syncthing.service
systemctl --user start syncthing.service
systemctl --user status syncthing.service
 ```
 Acceder a la interfaz gráfica de usuario
 ```txt
 http://localhost:8384
 ````
 Configurar contraseña de usuario
 ```txt
 Acciones / Ajustes / Interfaz Grafica de usuario
 ```
 Obtener el QR de identificador único de equipo
 ```txt
 Acciones / mostrar ID
 ```
 