https://play.picoctf.org/playlists/14?m=107
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`

- to connect we use [[netcat]], `nc jupiter.challenges.picoctf.org 14291`
- running it prints a ton of text
```
[...]
I don't think this is a flag either
Not a flag either
Again, I really don't think this is a flag
Not a flag either
This is defintely not a flag
[...]
```
- so lets store it in a file and save the text so we can search through it separately
- `nc jupiter.challenges.picoctf.org 14291 > tmp.txt`
	- connect and store output into tmp.txt
- now we can use [[grep]] to search for the flag
- `cat tmp.txt| grep pico`
- yay