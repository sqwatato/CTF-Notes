- `ls -ld`
![[Screenshot 2024-02-20 at 11.34.02 PM.png]]
```
-  is a regular file
d is a directory (yes, directories are actually just special files!)
l is a symbolic link (a file that transparently points to another file or directory)
p is a named pipe (also known as a FIFO. You will get very familiar with these this module!)
c is a character device file (i.e., backed by a hardware device that produces or receives data streams, such as a microphone)
b is a block device file (i.e., backed by a hardware device that stores and loads blocks of data, such as a hard drive)
s is a unix socket (essentially a local network connection encapsulated in a file)
```