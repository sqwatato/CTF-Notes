- password cracking besty


- `hashcat -m 0 -a 0 hash.txt wordlist.txt`

- `hashcat`: This is the main command to run the Hashcat program (on Windows, use hashcat.exe).
- `-m 0`: This is the option for the hash type. In this case, 0 represents MD5. The value here would change depending on the hash type you are trying to crack. For instance, -m 1000 would be used for NTLM hashes.
- `-a 0`: This is the attack mode. In this case, 0 stands for "straight" mode, a dictionary attack.
	- modes:
		- `0` is straight
		- `3` brute force (mask)
- `hash.txt`: This file contains the hash or hashes you're trying to crack. It should be a text file with one hash per line.
- `wordlist.txt`: This is your dictionary or list of potential passwords. Like the hash file, this should be a text file with one entry per line.

- `hashcat -m 0 -a 0 hash.txt 'SKY-HQNT-?d?d?d?d'`
	- try all pwd that start with `SKY-HQNT-` and end with 4 digit num
	- `?l = abcdefghijklmnopqrstuvwxyz`
	- `?u = ABCDEFGHIJKLMNOPQRSTUVWXYZ`
	- `?d = 0123456789`
	- `?h = 0123456789abcdef`
	- `?H = 0123456789ABCDEF`
	- `?s = «space»!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~`
	- `?a = ?l?u?d?s`
	- `?b = 0x00 - 0xff`