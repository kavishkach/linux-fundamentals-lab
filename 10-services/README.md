# Services - Programs That Never Stop

A service is a program that runs in the background and never stops. Your web server, database, SSH (for remote access) - all services. They start automatically when you boot the computer and keep running even if nobody's logged in.

## The Basics

**Service (Daemon)** - A program running in the background, doing its job quietly.

**Systemd** - The modern system for managing services. It handles starting, stopping, and monitoring everything.

## Controlling Services

**Start/stop/restart:**
- `sudo systemctl start ssh` - Turn on the SSH service.
- `sudo systemctl stop ssh` - Turn it off.
- `sudo systemctl restart ssh` - Turn it off and back on.
- `sudo systemctl reload nginx` - Reload configuration without stopping the service.

**Checking status:**
- `systemctl status ssh` - Is SSH running? What's it doing?
- `systemctl is-active ssh` - Just yes or no: is it running?
- `systemctl is-enabled ssh` - Will it start automatically on boot?

**Boot behavior:**
- `sudo systemctl enable ssh` - Start this service automatically when the computer boots.
- `sudo systemctl disable ssh` - Don't start it automatically anymore.

## Finding Services

- `systemctl list-units` - Everything that systemd is managing.
- `systemctl list-unit-files` - All available services.

## Looking at Logs

If something's broken, the logs tell the story:

- `journalctl -u ssh` - Show logs for the SSH service.
- `journalctl -f` - Watch logs as they happen in real-time.
- `journalctl -n 50` - Show the last 50 log entries.

## Common Services You'll See

- **ssh** - Remote login access
- **nginx** or **apache2** - Web servers
- **mysql** or **postgresql** - Databases
- **docker** - Container system
- **cron** - Runs scheduled tasks

## What You'll Learn

- Start and stop services when you need to
- Make services start automatically on boot
- Check if a service is working
- Read logs to figure out what went wrong
- Restart services after configuration changes

Pro tip: If you change a service's configuration, use `systemctl reload` if possible. It's gentler than `restart` and doesn't drop active connections.
