# Working with Files and Directories in Linux

So you want to get around your Linux system and actually do stuff with files? That's what this is all about. Whether you're creating new folders, copying files around, or just peeking at what's inside a file, these are the commands you'll use every single day.

## The Basics You'll Use All The Time

**Making stuff:**
- `touch myfile.txt` - Creates an empty file. Super handy when you just need a blank file to start with.
- `mkdir myfolder` - Makes a new folder. Simple as that.
- `mkdir -p folder1/folder2/folder3` - Creates a bunch of nested folders all at once. The `-p` means "create parent folders if they don't exist."

**Copying and moving:**
- `cp file.txt file_copy.txt` - Copies a file. Now you have two.
- `cp -r folder1 folder2` - Copies an entire folder and everything inside it. The `-r` means "recursive" - it goes into all the subfolders too.
- `mv oldname.txt newname.txt` - Moves or renames a file. Same command does both!

**Deleting (be careful!):**
- `rm file.txt` - Deletes a file forever. No trash bin, it's gone.
- `rm -r folder1` - Deletes a folder and everything in it. Again, gone for good.

**Looking at files:**
- `cat file.txt` - Shows the entire file contents right on your screen.
- `less file.txt` - Opens the file so you can scroll through it page by page. Press `q` to quit.
- `head file.txt` - Shows just the first 10 lines. Great if a file is huge.
- `tail file.txt` - Shows the last 10 lines. Useful for checking recent entries in log files.

**Finding stuff:**
- `find . -name "*.txt"` - Searches for all .txt files starting from where you are.
- `which python` - Finds where the Python program lives.

## What You'll Learn

After working through this section, you'll be able to:
- Create files and folders without touching a mouse
- Copy and move files around like you know what you're doing
- Check out what's inside files without opening them in an editor
- Find files hiding somewhere in your system
- Delete stuff (so be careful!)

Just remember: in Linux, there's usually no undo for file deletion. So triple-check before you hit enter on an `rm` command!
