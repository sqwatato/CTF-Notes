- lists files and directory names
- recover deleted files
- extract metadata
```
usage: fls [-adDFlhpruvV] [-f fstype] [-i imgtype] [-b dev_sector_size] [-m dir/] [-o imgoffset] [-z ZONE] [-s seconds] image [images] [inode]
        If [inode] is not given, the root directory is used
        -a: Display "." and ".." entries
        -d: Display deleted entries only
        -D: Display only directories
        -F: Display only files
        -l: Display long version (like ls -l)
        -i imgtype: Format of image file (use '-i list' for supported types)
        -b dev_sector_size: The size (in bytes) of the device sectors
        -f fstype: File system type (use '-f list' for supported types)
        -m: Display output in mactime input format with
              dir/ as the actual mount point of the image
        -h: Include MD5 checksum hash in mactime output
        -o imgoffset: Offset into image file (in sectors)
        -P pooltype: Pool container type (use '-P list' for supported types)
        -B pool_volume_block: Starting block (for pool volumes only)
        -S snap_id: Snapshot ID (for APFS only)
        -p: Display full path for each file
        -r: Recurse on directory entries
        -u: Display undeleted entries only
        -v: verbose output to stderr
        -V: Print version
        -z: Time zone of original machine (i.e. EST5EDT or GMT) (only useful with -l)
        -s seconds: Time skew of original machine (in seconds) (only useful with -l & -m)
        -k password: Decryption password for encrypted volumes
```


```
fls image.dd # List files in the "image.dd" disk image
fls -l image.dd -i 12345 # List files in directory with inode 12345
fls -m image.dd -o 1035 # Extract file contents and metadata for file 1035
```

### Examples
`fls -o 2048 dds2-alpine.flag.img`
- `d/d 26417:      home`
	- `d/d` means its a directory and metadata says its a directory
- `r/r 12: .dockerenv`
	- `r/r` means its a file and metadata says its a file
- `V/V 32513:      $OrphanFiles`
	- `V/V` is for TSK virtual file (idk wtf that is)
