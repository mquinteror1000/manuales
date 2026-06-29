#nginx #oci
# Usar nginx para regirigir un domiio sencillo a otro dentro de la red pfsense+nginx
En este caso lo que quiero hacer es que una url sencilla como [db1.mydomain.mx](https://db1.mydomain.mx) lleve
a una mas compleja como [https://mydb.adb.us-ashburn-1.oraclecloudapps.com](https://mydb.adb.us-ashburn-1.oraclecloudapps.com)
Para esto en la red hay un pfsense este reolvera [db1.mydomain.mx](db1.mydomain.mx) a la ip de un servidor roky con nginx el cual redigirá a el domio completo on una redirección permanente 301 de HTTP
i## Isntalar y configurar nginx
```bash
sudo dnf install nginx
sudo systemctl enable --now nginxi
```
## Crear el sitio virtual
