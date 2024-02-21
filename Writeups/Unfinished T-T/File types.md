https://play.picoctf.org/practice/challenge/268?page=8

This file was found among some files marked confidential but my pdf reader cannot read it, maybe yours can.
- first we use [[file]] to check if it really is a pdf
```
➜  CTF file Flag.pdf 
Flag.pdf: shell archive text
```
- clearly not a pdf
- [[shar]] file
- unpack it with `sh Flag.pdf`
	- it failed
- try with `unshar`
