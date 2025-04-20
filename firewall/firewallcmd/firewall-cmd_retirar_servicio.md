#firewall #firewalld #firewall-cmd  #servicio 
### remover un servicio de firewalld
retirar http de firewallcmd
```bash
firewall-cmd --permanent --remove-service=http --zone=public
```
verificar zonas habilitadas del firewall
```bash
firewall-cmd --list-services
firewall-cmd --list-all
```
reiniciar el serivicio de firewalld
```bash
firewall-cmd reload
```
volver a verificar los servicios y asegurarse que ya no este http
```bash
firewall-cmd --list-services
```
