#ssh #clave_publica #pesonalizada #github

Crear la clave pública
```bash
mkdir -p ~/.ssh/github/
ssh-keygen -t ed25519 -C "github mquinteror1000" -f ~/.ssh/github/my_github_ssh_key
```
Agregar la clave al agente ssh
```bash
ssh-add ~/.ssh/github/my_github_ssh_key
```
editar el archivo de configuración ssh
```bash
touch ~/.ssh/config
chmod 600 ~/.ssh/config
vim ~/.ssh/config
```
Agregar el contenido
```bash
Host github.com 
HostName github.com
User git
IdentityFile ~/.ssh/github/my_github_ssh_key
IdentitiesOnly yes
```
Verificar la conexion
```bash
ssh -T git@github.com
```
