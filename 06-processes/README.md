# Processes - What's Actually Running on Your Computer
A process is basically a program that's running right now. Every time you start something, it becomes a process. Your terminal is a process. Firefox is a process. That annoying thing using all your CPU? Probably a process.

## The Basics
**Process ID (PID)** - Every process gets a unique number. Think of it like an ID badge.

**Foreground** - The program you're actively using. It's talking to your terminal right now.

**Background** - Something running quietly in the background. You can still use your terminal.

## Seeing What's Running
- `ps` - Shows the processes you're currently running.
- `ps aux` - Shows everything that's running on the whole system. It's a lot.
- `top` - Opens a live dashboard showing what's eating your CPU and memory. Press `q` to close it.
- `htop` - Same as `top` but prettier and easier to use.
- `pgrep firefox` - Find the process ID for Firefox (or any other program).

## Running Things in the Background
If you have a command that takes forever, you can run it in the background:

- `long_command &` - Start it and get your terminal back immediately.
- `Ctrl+Z` - Pause what you're doing.
- `bg` - Resume it in the background.
- `fg` - Bring it back to the foreground.
- `jobs` - See what's running in the background.

## Killing Things
Sometimes a program stops responding or just needs to die:
- `kill 1234` - Gently ask process 1234 to quit.
- `kill -9 1234` - Kill it with fire. It dies immediately.
- `killall firefox` - Kill all Firefox processes at once.
- `Ctrl+C` - Stop whatever's in the foreground. Usually works.

## Priority Stuff
Some processes are more important than others. You can tell Linux to give a process more or less CPU time:

- `nice -n 10 command` - Run something with lower priority (so it doesn't hog everything).
- `renice -n 5 -p 1234` - Change the priority of an already-running process.

## What You'll Learn
- See what programs are actually running
- Find a specific process by name
- Kill programs that are frozen
- Run commands in the background so you can keep working
- Keep your system from grinding to a halt

Pro tip: Use `htop` if it's installed. It's way better than `top` for beginners.
