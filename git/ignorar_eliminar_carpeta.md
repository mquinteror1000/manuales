#git #ignore #eliminar #carpeta
Como eliminar una carptea de git, cuando esta ya se agrego al repositorio
1. agregar la carpeta a al archivo **.gitignore** 
```bash
./mi_carpeta_oculta
# carpeta normal
mi_carpeta_normal/
```
2. Sí la carpeta ya se agregó
```bash
git rm  -r --cached mi_carpeta_normal
git rm -r --cached .mi_carptea_oculta
git commit -m "eliminando carpetas no deceadas"
git push
```
3. Verificar los resultados en el repositorio
