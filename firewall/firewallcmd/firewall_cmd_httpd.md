#firewall #firewalld #firewall-cmd #port #internet
# abrir puetos para httpd 80 y 443
Instalar firewallcmd
```bash
dfn isntall firewallcmd
```
Iniciar servicio firewalld
```bash
systemctl enable firewalld
systemctl start firewalld
```
Verificar es estado del servicio
```bash
systemctl status firewalld
```
Agregar  reglas de firewall
```bash
firewall-cmd --permanent --add-port=80/tcp
firewall-cmd --permanent --add-port=443/tcp
```
opción indicando el nombre del servicio
```bash
firewall-cmd --permanent --add-service=http 
firewall-cmd --permanent --add-service=https
```
Recargar el servicio
```bash
firewall-cmd --reload
```
Listar los servicios abiertos
```bash
firewall-cmd --list-all
```