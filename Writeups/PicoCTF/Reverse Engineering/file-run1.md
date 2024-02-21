https://play.picoctf.org/practice/challenge/266?page=7

- first we check what kind of file it is with [[file]]
```txt
run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=a468f05064d2f1ffa0047ba7295de4995176da15, for GNU/Linux 3.2.0, not stripped
```
- seems like a linux file
- https://fareedfauzi.gitbook.io/ctf-playbook/reverse-engineering
- ELF file ^^^
- lets try running it to see how it works first (hence the name file-run)
- to run it, first make it executable with `chmod +x run` and then run it with `./run`
	- you need a linux machine, I am using a VM with Kali on my M1 Mac
- ez