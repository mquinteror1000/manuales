#samba #smbclientcd 
```bash
smbclient -L server -U %
smbclient //server.domanin/shared_folder -U user
```
Respuesta
```bash
Password for [SAMBA\user]:
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D     
```