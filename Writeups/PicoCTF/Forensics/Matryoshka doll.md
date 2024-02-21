https://play.picoctf.org/practice/challenge/129?page=2

- first try using [[exiftool]] to see if there's anything special
	- `exiftool doll.jpg`
- try to see if any hidden data, stego, so visit https://georgeom.net/StegOnline/upload [[Forensics#^3da997]] to browse [[Bit Planes]] and [[LSB]]
	- nothing found
- going to [[CyberChef]],  try to extract files/data!
![[Screenshot 2024-02-20 at 6.05.10 PM.png]]
- scrolling down, we see `extracted_at_0x4286c.zip`, fishy
- downloading the zip and unzipping it, we get another doll picture, so we can try it again ig
- wow another zip file
- there seems to be a lot of nested embedded files, so we are going to use [[binwalk]] to extract them all
	- `binwalk -Me dolls.jpg`
	- -Me means recursively extract
- we end up with a flag.txt: `picoCTF{96fac089316e094d41ea046900197662` (urs prob different)
	- there is a hidden character at the end, so delete it and replace with } to get flag