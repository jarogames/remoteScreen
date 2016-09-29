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
