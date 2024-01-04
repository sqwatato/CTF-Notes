https://play.picoctf.org/practice/challenge/285

- [[gunzip]] disk img
- [[mmls]] disk img
```
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)

```
- check 004 then 002 if need since 004 has uneven length and probably is the one of interest
- yup seems like it, [[fls]] shows me the common linux root folders
```
$ fls -o 411648 disk.flag.img 
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
```
- now check root and home
```
$ fls -o 411648 disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
```
- [[icat]] flag.txt.enc
```
$ icat -o 411648 disk.flag.img 1782
Salted__S�+%���+�O��k�ђ(A����c��
                                @]ԣ
L�ޢȤ7� ���؎$�'%%                                                                                                          
```
- encrypted huh
- I tried putting the output into [[CyberChef]] and use magic to decode but that didn't work
- i explored the disk with fls and then i thought of checking .ash_history
```
$ icat -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
```
- ayyyy now we know how the flag was encoded
- i've seen AES256 before and i also know [[openssl]] has some encryption algos, but i have no idea what that command does other than it encodes it
- so i ask by bestie bard to teach me about it
- we just run the same command but with the `-d` (decode) flag
	-  `icat __ > tmp`  to have file output be put in tmp 
	- enter in `unbreakblepassword1234567` as password
```
$ openssl aes256 -d -in tmp                       
enter AES-256-CBC decryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
206075B4FFFF0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:124:
picoCTF{h4un71ng_p457_1d02081e}%  
```