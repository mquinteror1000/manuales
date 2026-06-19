#dnf #paquete #libreria #consulta #herramienta 
**dnf provides** permite preguntarle a dnf que paquete instala un paquete o librería.

útil cuando un programa solicita la instalación de una librería.

## Ejemplo:
Tras tratar de ejecutar un Appimage me dice que no encuentra la libreria **libfuse.so.2** :
```bash
/LibreOffice-fresh.full-x86_64.AppImage 
dlopen(): error loading libfuse.so.2

AppImages require FUSE to run. 
You might still be able to extract the contents of this AppImage 
if you run it with the --appimage-extract option. 
See https://github.com/AppImage/AppImageKit/wiki/FUSE 
for more information

```

```bash
dnf provides "libfuse.so.2"
## Carga los repositorios
Repositories loaded.
fuse-libs-2.9.9-24.fc43.i686 : File System in Userspace (FUSE) v2 libraries
Repo         : fedora
Matched From : 
Provide      : fuse-libs = 2.9.9-24.fc43

```
ahora puedo instalar **fuse-libs** para ejecutar mi Appimage:

