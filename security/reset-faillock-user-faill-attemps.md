## Limpiar conteo de intentos fallidos para un usuario
Despues de que un usuario no se acuerda de su contraseña tres veces en oci, este se bloquea ya no puede iniciar sesion via tty con su contraseña, tal vez mediante ssh y lo tuviera configurado o por su desde root.
se muestro algo asi
```shellsession
[sudo] password for mquinteror:
Sorry, try again.
[sudo] password for mquinteror:
sudo: 3 incorrect password attempts

```

Si se intenta cambiar el password, tampoco lo acepta
```shellsession
New password:
Retype new password:
Password has been already used. Choose another.
passwd: Have exhausted maximum number of retries for service

```
se intentan cosas como 
eliminar el registro de **/etc/security/opasswd**
o retirarle el password al usuario `passwd -d mquinteror` para volver a intentar `passwd mquinteror`, lo acepta pero sigue la cosa igual
lo que funcionó
```bash
faillock --user mquinteror
faillock --user mquinteror --reset
```
