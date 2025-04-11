#tranmission #cli #descargas #torrent
# Tansmission-cli

Descargar un archivo torrent
```bash
transmision-cli -f my_torrent.torrent
```

indicar la ubicación de la descarga
```bash
transmission-cli -w ~/Descargas/mytorrents/my_new_movie.mp4
```
uso típico
```bash
transmission-cli -f ~/Descargas/torrents/my_new_movie.torrent -w ~/Descargas/mytorrents/my_new_movie.mp4
```
Descarga desde un magnet
```bash
transmission-cli -f "magnet:?xt=urn:btih:98-..." -w ~/Descargas/mytorrents/my_new_movie.mp4
```
