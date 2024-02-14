https://play.picoctf.org/practice/challenge/246?page=6
- `if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):`
- so find pwd
- `print(chr(int("0x64", 16)) + chr(int("0x65", 16)) + chr(int("0x37", 16)) + chr(int("0x36", 16)))`
- pwd is de76
