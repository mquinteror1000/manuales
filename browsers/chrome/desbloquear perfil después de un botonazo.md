#chrome #profile #bloqued 
Después de un cierre repentino suele bloquearse el perfil de google chrome

```bash
google-chrome-stable 
[5635:5635:0214/151155.135944:ERROR:chrome/browser/process_singleton_posix.cc:363] The profile appears to be in use by another Google Chrome process (123224) on another computer (172-1-8-58.lightspeed.lbcktx.sbcglobal.net).  Chrome has locked the profile so that it doesn t get corrupted.  If you are sure no other processes are using this profile, you can unlock the profile and relaunch Chrome.
[5635:5635:0214/151155.136015:ERROR:chrome/browser/ui/views/message_box_dialog.cc:199] 
```

```bash
cd --
rm .config/google-chrome/SingletonLock
```


