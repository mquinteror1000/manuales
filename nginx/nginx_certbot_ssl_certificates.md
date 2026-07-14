Configurar certificados ssl en nginx con certbot
## instalar certbot OL10
Los paquetes **certobot** y **python3-certbot-nginx**  si están disponibles en epel [oracle Epel packages ol 10](https://yum.oracle.com/repo/OracleLinux/OL10/1/developer/EPEL/x86_64/index.html)
El repositorio EPEL aunque esta instalado el paquete suele venir deshabilitado, verificar.
```bash 
sudo dnf install oracle-epel-release-ol10
sudo dnf repolist all
## epel suele estar desactivado
#ol10_u1_developer_EPEL   Oracle Linux 10.1 EPEL Packages for Development (x86_64)  disabled
```
activar epel
```bash 
sudo dnf config-manager --enable ol10_u1_developer_EPEL
## actualizar cache
sudo dnf makecake
```
Instalar los paquetes de certbot
```bash 
sudo dnf isntall certbot python3-certbot
```
## Solicitar los certificados
Se solicitan los certificados
para esta ejemplo para esta configuración de nginx
```nginx
server {
    listen 80;
    server_name domain.net www.domain.net;

    location / {
        proxy_pass http://127.0.0.1:8080; # Aquí apunta a tu app Quarkus
        
        # Estas cabeceras son importantes para que la app backend sepa de dónde viene la petición real
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
De la siguiente forma
```
sudo certbot --nginx -d domain.net -d www.domain.net
```
Si todo sale bien Certbot confirma la emisión de los certificados, los coloca en 

/etc/letsencrypt/live/domain.net/fullchain.pem
/etc/letsencrypt/live/domain.net/privkey.pem
Cambien modifica el archivo de configuracion de nginx
```nginx
server {
        server_name domain.net www.domain.net;
        location / {
                proxy_pass http://127.0.0.1:8080;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header X-Forwarded-Proto $scheme;
        }

    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/domain.net/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/domain.net/privkey.pem; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot


}
server {
    if ($host = www.domain.net) {
        return 301 https://$host$request_uri;
    } # managed by Certbot


    if ($host = domain.net) {
        return 301 https://$host$request_uri;
    } # managed by Certbot


        listen 80;
        server_name domain.net www.domain.net;
    return 404; # managed by Certbot

```