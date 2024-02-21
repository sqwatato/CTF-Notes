https://play.picoctf.org/practice/challenge/267?page=8
Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"?
```txt
➜  CTF ./run
zsh: permission denied: ./run
➜  CTF chmod +x run
➜  CTF ./run       
Run this file with only one argument.
➜  CTF ./run -h
Won't you say 'Hello!' to me first?
➜  CTF ./run Hello!
The flag is: picoCTF{F1r57_4rgum3n7_be0714da}%  
```
- a linux executable, check with `file run`
- to run with hello, type hello after it
- ez
