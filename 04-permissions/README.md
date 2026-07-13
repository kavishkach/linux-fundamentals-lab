# File Permissions - Keeping Your Stuff Secure

Permissions are basically Linux's way of saying "who gets to do what with this file." Think of it like a house - you own it, your family might have keys to some rooms, and strangers definitely don't get in everywhere.

## The Three Permission Types

**Read (r)** - Can you look at the file?
- For files: You can read the contents
- For folders: You can list what's inside

**Write (w)** - Can you change it?
- For files: You can edit or delete it
- For folders: You can create or delete files in it

**Execute (x)** - Can you run it?
- For files: You can run it as a program
- For folders: You can actually enter the folder

## The Three Permission Levels

**Owner (u)** - That's you, the person who created it
**Group (g)** - A team of people who share permissions
**Others (o)** - Everyone else on the system

## Actually Changing Permissions

When you do `ls -l`, you see something like `-rw-r--r--`. That's the permission string.

**The easy way (text):**
- `chmod +x script.sh` - Make it executable (add x)
- `chmod -w file.txt` - Remove write permission
- `chmod u+rw file.txt` - Give the owner read and write
- `chmod o-rwx file.txt` - Strip all permissions from others

**The number way:**
- `chmod 755 script.sh` - Owner: all permissions, everyone else: read and execute
- `chmod 644 file.txt` - Owner: read and write, everyone else: just read
- `chmod 700 secret.txt` - Owner only: full access

The numbers work like this: r=4, w=2, x=1. So rwx = 7, rw = 6, r-x = 5

**Changing who owns it:**
- `chown newuser file.txt` - Give it to someone else
- `chown user:group file.txt` - Change both owner and group
- `chgrp newgroup file.txt` - Just change the group

## What You'll Get Good At

- Looking at permissions and understanding what they mean
- Changing who can do what with your files
- Making scripts executable
- Protecting sensitive files from prying eyes
- Setting up proper permissions on shared folders

Protip: 755 is super common for scripts, and 644 is typical for regular files. Most of the time you'll just use those.
