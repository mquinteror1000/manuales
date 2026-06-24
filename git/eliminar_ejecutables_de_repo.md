#git #repo #gitignore
#Eliminar ejecutables de un repositorio
En caso de haber olvidado la regla de girignore para no subir ajecutables
```bash
*
!*.*
!.gitignore
```
### Limpiar la cache
```bash
git rm -r --cached .
```
### Volver a agregar los archivos

```bash
git add .
```
### Verificar que se respete el nuevo gitignore

```bash
git git commit -m "no execi"
git push origin main
```
## Purgar ejecutables del historial
### intalar git filter repo

```bash
sudo dnf install git-filter-repo
```
### Purgar

```bash
#git filter-repo --path my_executable_path --invert-path

martin@pc-bdx-mqr:~/devel/gtkmm_gui_apps$ git filter-repo --path 001_hello_world_gui/mi_app --invert-paths --force
NOTICE: Removing 'origin' remote; see 'Why is my origin removed?'
        in the manual if you want to push back there.
        (was git@github.com:mquinteror1000/gtkmm_gui_apps.git)
Parsed 8 commits
New history written in 0.04 seconds; now repacking/cleaning...
Repacking your repo and cleaning out old unneeded objects
HEAD is now at aebba68 ejecutables en **/build y mantener el directorio
Enumerating objects: 45, done.
Counting objects: 100% (45/45), done.
Delta compression using up to 8 threads
Compressing objects: 100% (44/44), done.
Writing objects: 100% (45/45), done.
Total 45 (delta 13), reused 2 (delta 0), pack-reused 0 (from 0)
Completely finished after 0.09 seconds.

# para otro binario que tambien estaba en el repo
martin@pc-bdx-mqr:~/devel/gtkmm_gui_apps$ git filter-repo --path 003_occi_sample/mi_app_gtkmm --invert-paths --force
Parsed 8 commits
New history written in 0.01 seconds; now repacking/cleaning...
Repacking your repo and cleaning out old unneeded objects
HEAD is now at a5557f0 ejecutables en **/build y mantener el directorio
Enumerating objects: 44, done.
Counting objects: 100% (44/44), done.
Delta compression using up to 8 threads
Compressing objects: 100% (32/32), done.
Writing objects: 100% (44/44), done.
Total 44 (delta 12), reused 38 (delta 11), pack-reused 0 (from 0)
Completely finished after 0.05 seconds.

# para directorios se usa --path-glob
```
### Volver a refrescar la chache
```bash
git rm -r --chached .
git add .
git commit -m "remoded binanys from cache repo"

```
Todavia no me convence
