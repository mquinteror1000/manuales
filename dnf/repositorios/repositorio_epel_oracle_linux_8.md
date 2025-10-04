#epel #dnf #oracle #linux_8 #ol8
# Configuracion del repositorio epel en oracle linux_8
Instalar el paquete **oracle-epel-release-el8**
```bash
dnf install oracle-epel-release-el8
```
Habilitar el repositorio EPEL
```bash
dnf config-manager --enable ol8_epel
# a mmi me funciono
dnf config-manager --set-enabled ol8_developer_EPEL
```
Verificar que se encuentre habilitado
 ```bash
 dnf repolist

```
 