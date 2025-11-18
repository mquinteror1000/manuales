#mpv #multimedia #sonido
varias veces se ha desconfigurado el dispositivo de salida de audio en mpv, provocando que  no ose escuche y teniendo que seleccionar el dispositivo manualmente cada vez

### Listar los dispositivos de audio
```
mpv --audio-device=help

List of detected audio devices:
  'auto' (Autoselect device)
  'pipewire' (Default (pipewire))
  'pipewire/alsa_output.pci-0000_00_1f.3.analog-stereo' (Built-in Audio Analog Stereo)
  'pulse/alsa_output.pci-0000_00_1f.3.analog-stereo' (Built-in Audio Analog Stereo)
  'alsa' (Default (alsa))
  'alsa/pipewire' (PipeWire Sound Server)
  'alsa/sysdefault:CARD=PCH' (HDA Intel PCH, ALC293 Analog/Default Audio Device)
  'alsa/front:CARD=PCH,DEV=0' (HDA Intel PCH, ALC293 Analog/Front output / input)

```

### archivo de configuración de mpv
** ~/.config/mpv/mpv.conf **
```
audio-device=pipewire/alsa_output.pci-0000_00_1f.3.analog-stereo

```
Reemplazar por 
```
audio-device=alsa/pipewire
```