# Users and Groups - Managing Who Does What

Every Linux system has multiple users. Maybe it's just you on your laptop, or maybe you're managing a server where lots of people need access. Groups help you organize people and give them permissions all at once.

## The Key Ideas

**Users** - Think of them as login accounts. Each user has their own folder, preferences, and permissions.

**Root** - This is the boss user (user ID 0). Root can do literally anything on the system. Like sudo powers but actually being root.

**Regular users** - Everyone else (usually starting at user ID 1000). They can do stuff, but not everything.

**Groups** - Collections of users. Instead of giving permission to each person individually, you say "give it to the developers group" and boom, everyone in that group gets it.

## Finding Out Who You Are

- `whoami` - Just tells you your username. Useful when you're confused about who you are.
- `id` - Shows your user ID, group ID, and all the groups you're in.
- `groups` - Lists all groups you belong to.
- `groups john` - Shows what groups another user is in.

## Doing Stuff With Super Powers

- `sudo command` - Run one command as root (the boss). You usually need a password.
- `sudo -u john command` - Run a command as if you were john.
- `su` - Switch to root and stay there. Now every command is root.
- `su john` - Switch to being john instead.

## Creating and Managing Users

- `sudo useradd newuser` - Create a new account.
- `sudo userdel olduser` - Delete someone's account.
- `sudo usermod -aG groupname username` - Add a user to a group.
- `passwd` - Change your own password.
- `sudo passwd john` - Change someone else's password.

## Groups
- `sudo groupadd devteam` - Create a new group.
- `sudo groupdel devteam` - Delete a group.

## Looking at the Database

- `cat /etc/passwd` - See all users on the system.
- `cat /etc/group` - See all groups.

## What You'll Be Able To Do
- Figure out who you're logged in as and what groups you're in
- Create new user accounts for people
- Put users into groups so they share permissions
- Use `sudo` to do admin stuff without being root all the time
- Change passwords
- Understand the user and group system

One more thing: don't just give everyone `sudo` access. That's how bad things happen.
