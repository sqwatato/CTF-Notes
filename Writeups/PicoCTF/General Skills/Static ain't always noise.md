https://play.picoctf.org/practice/challenge/163

- running `cat` on the sh file, u will see that to run it, u needa do `sh ltdis.sh <file name>` 
- u run the command with static as the file name
- it outputs
```
Attempting disassembly of static ...

Disassembly successful! Available at: static.ltdis.x86_64.txt

Ripping strings from binary with file offsets...

Any strings found in static have been written to static.ltdis.strings.txt with file offset
```
- doing `cat static.ltdis.strings.txt` 