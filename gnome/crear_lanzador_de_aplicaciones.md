#lanzador-de-aplicaiones #gnome #acceso_dorecto

### para todos los usuarios
/usr/share/applications/

### Para el usuario local

~/.local/share/applications


```ini
[Desktop Entry]
Name=MiApp
Comment=Aplicación personalizada para Fedora
Exec=env JAVA_HOME=/usr/lib/jvm/java-17-openjdk /opt/miapp/miapp.sh %F
Icon=/opt/miapp/icon.png
Terminal=false
Type=Application
Categories=Utility;
StartupWMClass=miapp
NoDisplay=false
```