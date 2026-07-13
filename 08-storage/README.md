# Disk Space and Storage - Where Does Everything Go?

Your hard drive is where all your data lives. These commands help you figure out how much space you have, where your files are taking it all up, and how to manage your storage.

## The Basic Concepts

**Disk/Hard Drive** - The actual physical thing storing your data.

**Partition** - A chunk of your disk, like dividing it into sections.

**Filesystem** - How data is organized on a partition (ext4, NTFS, etc.).

**Mount** - Attaching a disk or partition to a folder so you can access it. Like plugging in a USB drive so it shows up as a folder.

## Checking Disk Space

**How much space is left?**
- `df -h` - Shows all your drives and how full they are. The `-h` makes it human-readable (GB instead of bytes).
- `df` - Same thing but in bytes. It's a lot of numbers.

**What's taking up all my space?**
- `du -sh /path` - Shows how big a folder is.
- `du -sh ~/*` - Show the size of everything in your home directory.
- `du -sh /home/` - How big is the entire home directory?

## Seeing Your Disks

- `lsblk` - Shows all your disks and partitions in a nice tree format.
- `fdisk -l` - Lists all disks and partitions (older style, more detailed).
- `blkid` - Shows what filesystems you have and their identifiers.

## Mounting and Unmounting

Sometimes you need to attach a disk or partition:

- `sudo mount /dev/sda1 /mnt` - Attach the partition to the /mnt folder so you can access it.
- `sudo umount /mnt` - Detach it when you're done.

## Formatting and Fixing

**Creating a new filesystem:**
- `sudo mkfs.ext4 /dev/sda1` - Format a partition as ext4 (a common filesystem).

**Checking for problems:**
- `sudo fsck /dev/sda1` - Check the filesystem for errors and try to fix them. Usually run this on an unmounted drive.

## What You'll Be Able To Do

- Find out how much disk space is left
- See what folders are using all your space
- Understand your disk and partition layout
- Mount USB drives or external disks
- Create and format new partitions
- Fix filesystem problems

Pro tip: If you're running out of space, `du -sh` is your friend. Find the big folders and figure out what's taking up room.
