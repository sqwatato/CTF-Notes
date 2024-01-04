https://play.picoctf.org/practice/challenge/186?page=1

- nothing seems sussy in the actual picture
- use [[exiftool]] to see meta data of image
- in the license section, 
```
...
XMP Toolkit : Image::ExifTool 10.80
License     : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights      : PicoCTF
...
```
- License looks sus since it should usually indicate owner
- turns out it's encoded in [[base64]], decoding it with [[CyberChef]] we get the flag