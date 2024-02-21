https://play.picoctf.org/practice/challenge/322?page=9

- ton of files, want to cat every file and [[grep]] for pico in each one
- `find . -type f -exec cat {} \;`
- for each file, execute cat