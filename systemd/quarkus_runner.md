#quarkus #systemd 
<br>
# Crear una unidad de systemd para correr quarkus
El ejecutable graalvm de quarkus se sube al directorio
**/home/sampleuser/domain.net/**
el binario es **quarkus-app-1.0-runner**
este usuario cuenta con un script para actualizar el binario de  quarkus
/home/sampleuser/.local/bin/update_quarkus_binary
```bash
#! /bin/bash
# update tehe 
sudo cp /home/sampleuser/domain.net/quarkus-app-1.0-runner /opt/quarkus_dir/
```

con las instrucciones para copiar el binario a la carpeta /opt/quarkus_dir/
Seguramente el binario se coloca mediante rsync desde la maquina de desarrollo
y luego se ejecuta
```bash
ssh sampleuser@domain.net 'bash ~/update_quarus_binary'
```
para actualizar el binario
o alguna otra solución modificando el archivo sudoers
## usuario especial para manejar el servicio
Se crea un usuario sin privilegios de iniciar sesión para manejar el servicio
```
sudo useradd -r -s /sbin/nologin quarkususer
sudo chown -R quarkususer:quarkususer /opt/mquinteror.net

```
## Unidad de systemd
Unidad de systed definida en
/etc/systemd/system/quarkus_runner.service

```toml
[Unit]
After=network.target

[Service]
User=quarkususer
Group=quarkusruner

WorkingDirectory=/opt/quarkus_dir
ExecStart=/opt/mquinteror.net/quarkus-app-1.0-runner
# Políticas de reinicio automático en caso de fallos externos
Restart=always
RestartSec=5

# Límites de recursos opcionales para producción (Protección del servidor)
LimitNOFILE=65536

[Install]
WantedBy=multi-user.target

```
## Probar y habilitar el servicio
Probar que funcione correctamente
```bash
sudo systemctl start quarkus_runner.sevice
sudo systemctl status quarkus_runner.sevice
sudo systemctl stop quarkus_runner.sevice
```
Si todo está bien, se puede habilitar el servicio
```bash
sudo systemctl enable quarkus_runner.sevice
sudo systemctl start quarkus_runner.sevice
```
## Probar que el servidor funciones 
ya sea con curl 
o visitando la URL directamente