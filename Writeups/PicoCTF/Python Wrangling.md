https://play.picoctf.org/practice/challenge/166?page=1

- running `python ende.py` will result in it telling you to use the flags
- running `python ende.py -h` with the help flag will tell you `To decrypt a file named 'pole.txt', do: '$ python ende.py -d pole.txt'`
- using that information, running `python ende.py -d flag.txt.en`
	- It will ask you for a password, which is located in `pw.txt`
	- Entering it will give you the flag