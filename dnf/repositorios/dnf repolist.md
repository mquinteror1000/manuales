#linux #dnf #repositorios #software #repolist #enabled #disabled
DNF 4 <
Mostrar todos los repositorios
```bash
dnf repolist --all
```
Mostrará todos los repositorios clasificándolos en [enabled] y [diabled]`````

Mostrar solo los repositorios habilitados

```bash
dnf repolist --all | grep -v "inhablilitado"
dnf repolist --all | grep -v "disabled"
```

