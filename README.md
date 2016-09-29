# REMOTE SCREEN from notebook to static PC


## * synergy

   I used earlier ... basically synergyc and synergyd are fine to send the keyboard and mouse

## * x11vnc_onewin

  X2X instead of synergy.
  
  Uses file ``` ~/.x11vnc_clients```, where the remotes are defined. Zenity asks for pc and direction
  
 Then opens the x2x on remote via ssh using direction ...
  
 creates ```~/.x2x_connected``` on remote as a lockfile
 
```bash
ssh -X $PC34 'if [ -e ~/.x2x_connected ]; then echo ALREADY RUNS..remove .x2x_connected on $PC34; else  touch ~/.x2x_connected;x2x -east -from $DISPLAY -to :0; rm ~/.x2x_connected; fi'

```

## * shootvnc

 new way - remote infinitelly waits for vnc (autovncviewer :  vncviewer -fullscreen  -passwd /home/ojr/.vncpassword edie:1)
 
 ```shootvnc```  starts and kills Xtightvnc; xmonad-session; x2x;
 
  ```.bashrc``` contains definition COMMAND_PROMPT, that shows current DISPLAY
  
  ```bash
  export PROMPT_COMMAND='if [ "$DISPLAY"  != ":0.0" ]; then echo -ne "\033[31;1m$DISPLAY\033[0m:"; fi '
  ```
 
 
