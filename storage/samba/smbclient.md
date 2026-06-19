#samba #smbclient #samba-client #probar
## Intalación de  samba-client
instalation
```bash
sudo dnf install samba-client
```

```bash
smbclient -L server -U %
# modo interactivo
smbclient //server.domanin/shared_folder -U user
```
Respuesta
```bash
Password for [SAMBA\user]:
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D     
```

