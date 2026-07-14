#quarkus #nginx 
Para esta ocasión necesito usar nginx como proxi inverso para un sitio
domain.net
en donde va a haver varios servidores ( Quarkus, un un weblogix, algun php y un cms publii )
Nginx tiene que redirigir las peticiones www.domain.net y doman.net a el puerto 8080
## instalar nginx
```bash
sudo dnf install nginx
sudo systemctl enable nginx
sudo systemctl start nginx
sudo systemctl status nginx
```

# Configurar el sitio
archivo de configuracion
/etc/nginx/conf.d/domain.net.conf
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
probar configuración e iniciar nginx
```bash
nginx -t
sudo systemctl restart nginx
```
## Aplicación de prueba
Se sube una aplicación de prueba y se ejecuta
```
./my_quarkus_app

```
# Verificar que se este ejecutando
acceder a http://domain.net/helloworld para ver que se ejecute
Si la respuesta es un bad Gateway
verificar que desde el usuario se pueda acceder a quarkus

```bash
curl -l http://127.0.0.1/helloworld
```
sí es el caso
Adecuar contexto de selinux
```bash
sudo setbool -p http_can_network_connect 1
sudo systemctl reload nginx
```
Volver a pro que ahora si http://domain.net/helloworl
responda el mensaje deseado

