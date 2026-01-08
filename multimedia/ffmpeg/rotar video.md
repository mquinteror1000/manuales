#ffmpeg #rotar #video 
```
ffmpeg -i video.mp4 -vf "transpose=1" video_rotado.mp4
```

| valor | resultado          |
| ----- | ------------------ |
| 1     | 90 sentido horario |
| 2     | 90 antiohorario    |
|       |                    |
Antes [[verificar que se tenga acceso a la gpu intel]]

```bash
ffmpeg -hwaccel vaapi \
       -hwaccel_device /dev/dri/renderD128 \
       -hwaccel_output_format vaapi \
       -i entrada.mp4 \
       -vf "transpose_vaapi=dir=clock" \
       -c:v h264_vaapi \
       -b:v 5M \
       salida_rotada.mp4
```

```bash
LIBVA_DRIVER_NAME=iHD ffmpeg -hwaccel vaapi \
       -hwaccel_device /dev/dri/renderD128 \
       -hwaccel_output_format vaapi \
       -i entrada.mp4 \
       -vf "transpose_vaapi=dir=clock" \
       -c:v h264_vaapi \
       -b:v 5M \
       salida_rotada.mp4
```

Sin inflar
```bash
LIBVA_DRIVER_NAME=iHD ffmpeg -hwaccel vaapi \
       -hwaccel_device /dev/dri/renderD128 \
       -hwaccel_output_format vaapi \
       -i entrada.mp4 \
       -vf "transpose_vaapi=dir=clock" \
       -c:v h264_vaapi \
       -qp 26 \
       salida_optimizada.mp4
```