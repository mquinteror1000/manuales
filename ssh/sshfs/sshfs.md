#ssh #sshfs
Folder en el servidor remoto
```bash
mkdir -p /home/remote_user/remote_folder
```
Folder en el servidor local
```bash
mkdir -p /home/local_user/remote_foldeer
```
Instalar sshfs
 ```bash
 dnf install sshfs
 ```
Montar el folder remoto
```bash
sshfs remote_user@server:/home/remote_user/remote_folfer /home/local_user/remote_folder
```
Desmontar el sistema de archivos
```bash
fumount -u /home/local_user/remote_folder
```
 