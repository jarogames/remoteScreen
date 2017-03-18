Terminals
==========


 * Use `terminator` it has ` -l layoutname` option for startup

* nice possiblity to redirect is `exec > /dev/pts/nn`

* Hint with terminal ` ssh -t edie 'screen -S panel1'`

* Very nice thing - `script -f /dev/pts/24` - could be more elaborated - file over ssh

   ** `script -f | ssh p34 "cat > /dev/pts/12" ` leaves no output on home terminal
   **  `tail -f typescript | ssh p34 "cat > /dev/pts/22"` and `script -f` after WORKS
   
`tail -f ~/typescript | ssh p34 "cat > /dev/pts/22" & script -f ~/typescript`

`tail -f ~/typescript | ssh fedo "cat > /dev/pts/33" & script -f ~/typescript`

`tail -f ~/typescript | ssh p34 "cat > /dev/pts/22" & script -f ~/typescript`
