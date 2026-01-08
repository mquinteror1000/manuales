#ffmpeg #gpu 

Intentar usar aceleración por hardware # no esta funcionando
```bash
ffmpeg -hwaccel auto -i entrada.mkv -c:v h264 -preset fast -crf 23 -c:a copy salida.mp4
```