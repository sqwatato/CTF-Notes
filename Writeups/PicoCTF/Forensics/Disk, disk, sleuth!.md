https://play.picoctf.org/playlists/16?m=120

- Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image
- start by using [[gunzip]] to unzip it
- `mmls dds1-alpine.flag.img`
	- [[mmls]] the img to see contents
```
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000262143   0000260096   Linux (0x83)
```
- seems like `002` is our target
- `fls -o 2048 dds1-alpine.flag.img`
	- use [[fls]] to see files/folders
```
d/d 10161:      home
d/d 11: lost+found
r/r 12: .dockerenv
d/d 2033:       bin
d/d 8129:       boot
d/d 6097:       dev
d/d 16257:      etc
d/d 28449:      lib
d/d 22353:      media
d/d 24385:      mnt
d/d 26417:      opt
d/d 24386:      proc
d/d 26418:      root
d/d 24387:      run
d/d 26419:      sbin
d/d 20321:      srv
d/d 20322:      sys
d/d 20323:      tmp
d/d 24388:      usr
d/d 20324:      var
V/V 32513:      $OrphanFiles
```
- well they asked us to use [[srch_strings]], so `srch_strings -o 2048 dds1-alpine.flag.img`
- it prints out everything, so lets limit it to pico with [[grep]]
- `srch_strings -o 2048 dds1-alpine.flag.img | grep pico`
- ez