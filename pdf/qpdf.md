#pdf #consola #herramienta

```bash
# rota el documento en sentido antihorario
qpdf doc_original.pdf --rotate=-90 doc_rotado.pdf
#rotal en sentido horario
qpdf doc_original.pdf --rotate=+90 doc_rotado.pdf
#rotar paginas especificas ( de la 10 a la 15 )
qpdf doc_rotado.pdf --rotate=+90:10-15 doc_rotado.pdf
```
