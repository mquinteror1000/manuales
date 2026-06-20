# Git Hub CLI 

## Instalacion
Para fedora, se encuentra en los repositorios oficiales
```bash
sudo dnf install gh
```
## Iniciar sesión en la consola
```bash
gh auth login
```

en el navegador [https://github.com/login/device/](https://github.com/login/device) 
y pegar el código de autenticación

```txt
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? SSH
? Upload your SSH public key to your GitHub account? /home/USER/.ssh/USER_KEY.pub
? Title for your SSH key: GitHub CLI
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: XXXX-XXXX
Press Enter to open https://github.com/login/device in your browser... 

✓ Authentication complete.
- gh config set -h github.com git_protocol ssh
✓ Configured git protocol
✓ SSH key already existed on your GitHub account: /home/USER/.ssh/USER_KEY.pub
✓ Logged in as USER

```
### mostrar los repositorios
```bash
gh repo list
```
Mostrar
NAME                                   DESCRIPTION                           INFO    UPDATED             



### crear repositorio de manera interactiva
el mas fácil
```bash
gh repo create
```
### Crear repositorio 

### Clonar un repositorio
```bash
gh repo clone my_repo
```
