- check permissions with `sudo -l`
**Understanding Permissions:**

- Files and directories have permissions for three user classes: owner, group, and others.
- Each class has three permission types: read, write, and execute.
- Permissions are represented in two ways:
    
    - Symbolic notation (e.g., `rwxr-xr-x`)
    - Octal notation (e.g., `755`)
    

**Viewing Permissions:**

- Use the `ls -l` command to list file details, including permissions.

**Common Permissions:**

- `r`: Read permission allows viewing content.
- `w`: Write permission allows modifying content.
- `x`: Execute permission allows running the file as a program (for files).

**Changing Permissions:**

- Use the `chmod` command to change permissions.
    
    - Symbolic notation:
        
        - `+`: Add permission.
        - `-`: Remove permission.
        - `=`: Set specific permission.
        
    - Octal notation:
        
        - Three digits represent permissions for owner, group, and others.
        - Each digit is the sum of permission values (4 for read, 2 for write, 1 for execute).
        
    

**Ownership and Groups:**

- Use the `chown` command to change file ownership.
- Use the `chgrp` command to change file group.
- Use the `id` command to find your user ID and group ID.

**Common Commands:**

- **Change file permissions:**
    
    - Symbolic: `chmod ugo+r myfile.txt` (add read to all)
    - Octal: `chmod 644 myfile.txt` (read/write for owner, read for group/others)
    
- **Change owner:** `chown username:groupname myfile.txt`
- **Change group:** `chgrp groupname myfile.txt`
- **Show current permissions:** `ls -l myfile.txt`
- **Set default permissions:** `umask 022` (sets default to 644 for files)

**Security Tips:**

- Use the most restrictive permissions necessary.
- Avoid giving write access to unnecessary users.
- Be cautious with `chmod` commands, especially with root privileges.