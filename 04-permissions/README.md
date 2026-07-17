# File Permissions - Keeping Your Stuff Secure

Permissions are Linux's way of deciding **who can do what with a file or folder**.

Think of it like a house:

* The owner has the main key
* A group may have limited access
* Everyone else may have little or no access

Permissions help protect files from being read, changed, deleted, or executed by the wrong users.

## The Three Permission Types

**Read (`r`)** - Can you view it?

* For files: Read the file contents
* For folders: List the files inside

```bash
cat notes.txt
ls projects/
```

**Write (`w`)** - Can you change it?

* For files: Edit or add content
* For folders: Create, rename, or delete files

```bash
echo "Hello" >> notes.txt
touch projects/test.txt
```

**Execute (`x`)** - Can you use or enter it?

* For files: Run it as a program or script
* For folders: Enter the folder and access its contents

```bash
./script.sh
cd projects/
```

## The Three Permission Levels

**Owner (`u`)** - The user who owns the file

**Group (`g`)** - A group of users sharing permissions

**Others (`o`)** - Everyone else on the system

You may also see:

**All (`a`)** - Owner, group, and others together

## Reading Permissions

Use:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 sahan developers 120 notes.txt
```

The permission part is:

```text
-rw-r--r--
```

Break it like this:

```text
- | rw- | r-- | r--
    Owner  Group Others
```

This means:

* Owner can read and write
* Group can only read
* Others can only read

The first character shows the file type:

```text
- = Regular file
d = Directory
l = Symbolic link
```

## Changing Permissions with `chmod`

`chmod` means **change mode**.

### The Easy Way - Text Method

Add execute permission:

```bash
chmod +x script.sh
```

Give only the owner execute permission:

```bash
chmod u+x script.sh
```

Give the owner read and write permission:

```bash
chmod u+rw file.txt
```

Remove write permission from the group:

```bash
chmod g-w file.txt
```

Remove all permissions from others:

```bash
chmod o-rwx secret.txt
```

Give everyone read permission:

```bash
chmod a+r file.txt
```

Symbols to remember:

```text
u = Owner
g = Group
o = Others
a = All

+ = Add permission
- = Remove permission
= = Set exact permission
```

## The Number Method

Permissions also use numbers:

```text
r = 4
w = 2
x = 1
```

Add them together:

```text
rwx = 7
rw- = 6
r-x = 5
r-- = 4
--- = 0
```

The three numbers represent:

```text
Owner | Group | Others
```

### Common Permission Numbers

```bash
chmod 755 script.sh
```

```text
Owner  = rwx
Group  = r-x
Others = r-x
```

Good for scripts and public directories.

```bash
chmod 644 file.txt
```

```text
Owner  = rw-
Group  = r--
Others = r--
```

Good for normal text files, HTML files, and configuration files.

```bash
chmod 700 private-folder/
```

```text
Owner  = rwx
Group  = ---
Others = ---
```

Only the owner can access it.

```bash
chmod 600 secret.txt
```

```text
Owner  = rw-
Group  = ---
Others = ---
```

Good for SSH keys, passwords, and sensitive files.

## Changing Ownership

Check the owner and group:

```bash
ls -l file.txt
```

Example:

```text
-rw-r--r-- 1 sahan developers 120 file.txt
```

Here:

* `sahan` is the owner
* `developers` is the group

Change the owner:

```bash
sudo chown newuser file.txt
```

Change both owner and group:

```bash
sudo chown user:group file.txt
```

Change only the group:

```bash
sudo chgrp newgroup file.txt
```

Change ownership of a folder and everything inside:

```bash
sudo chown -R user:group project/
```

Be careful with `-R` because it changes everything inside the folder.

## Practical Example - Make a Script Executable

Create a script:

```bash
nano hello.sh
```

Add:

```bash
#!/bin/bash

echo "Hello Linux"
```

Check the permissions:

```bash
ls -l hello.sh
```

You may see:

```text
-rw-r--r--
```

Try to run it:

```bash
./hello.sh
```

You may get:

```text
Permission denied
```

Add execute permission:

```bash
chmod +x hello.sh
```

Check again:

```bash
ls -l hello.sh
```

Now you may see:

```text
-rwxr-xr-x
```

Run it:

```bash
./hello.sh
```

Output:

```text
Hello Linux
```

## Small Practice Lab

Create a practice folder:

```bash
mkdir permission-lab
cd permission-lab
```

Create a file:

```bash
touch notes.txt
```

Check its permissions:

```bash
ls -l notes.txt
```

Set normal file permissions:

```bash
chmod 644 notes.txt
```

Remove read permission from others:

```bash
chmod o-r notes.txt
```

Give the group write permission:

```bash
chmod g+w notes.txt
```

Check after every change:

```bash
ls -l notes.txt
```

Try to understand how the permission string changes.

## Common Permission Problems

**Script gives Permission denied**

```bash
chmod +x script.sh
```

**Cannot edit a file**

```bash
ls -l file.txt
```

Check whether the file belongs to another user.

```bash
sudo chown $USER:$USER file.txt
```

**Cannot enter a folder**

```bash
ls -ld folder/
chmod u+x folder/
```

**SSH private key permission error**

```bash
chmod 600 private-key.pem
```

## Important Permissions to Remember

```text
755 = Scripts and public directories
644 = Normal files
700 = Private directories
600 = Sensitive files
```

Avoid this unless there is a real reason:

```bash
chmod 777 file.txt
```

`777` gives everyone full access. It may fix an error quickly, but it can create a security problem.

## What You'll Get Good At

* Reading permission strings
* Understanding owner, group, and others
* Changing permissions with `chmod`
* Using text and number methods
* Making scripts executable
* Changing ownership with `chown`
* Protecting private files
* Fixing common permission errors
