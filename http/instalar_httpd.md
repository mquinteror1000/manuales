#httpd #servidor-web  #linux 
# Instalar httpd
Instalar httpd
```bash
dnf install httpd
```
habilitar e iniciar el servicio
```bash
systemctl enable httpd
systemctl start httpd
systemctl status httpd
```
instalar modulo ssl
```bash
dnf istall mod_ssl
```
configurar  el sertificado ssl