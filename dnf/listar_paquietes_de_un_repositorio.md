#dnf #list #paquetes

Listar los paquetes de un repositorio en especifico
```bash
dnf list --available --repo=google-chrome
# mostrara lo siguiente
Actualizando y cargando repositorios:
Repositorios cargados.
Paquetes disponibles
google-chrome-beta.x86_64     144.0.7559.31-1  google-chrome
google-chrome-canary.x86_64   145.0.7619.0-1   google-chrome
google-chrome-stable.x86_64   143.0.7499.192-1 google-chrome
google-chrome-unstable.x86_64 145.0.7587.4-1   google-chrome

```
tambien podemos

buscar un paquete del repositorio de fedora

```bash
dnf list --available --repo=fedora | less
:/python
n
n
noh
para buscar entre los paquetes relacionados con python
```
