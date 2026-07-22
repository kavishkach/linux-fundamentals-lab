# Networking - Getting Your System Online
Networking is how your computer talks to other computers. Whether you're connecting to the internet, checking if a server is up, or copying files somewhere else, these commands make it happen.

## The Key Concepts
**IP Address** - Your computer's address on a network. Like a postal address but for the internet.

**Hostname** - A friendly name for your computer. Way easier to remember than an IP address.

**DNS** - Like a phone book that translates "google.com" into an actual IP address.

**Port** - Think of it as a door on your computer. Port 80 is usually for websites, port 22 is for SSH, etc.

## Checking Your Connection
**See what network you're on:**
- `ifconfig` or `ip addr` - Shows your IP address and network details.
- `hostname` - What's your computer's name on the network?

**Test if something's actually online:**
- `ping google.com` - Sends a quick message to google.com and waits for a response. If you get replies, you're connected.
- `ping -c 4 google.com` - Same thing but stop after 4 pings (otherwise it goes forever).

## Finding Stuff on the Network
- `nslookup google.com` - "Hey, what's Google's IP address?"
- `dig google.com` - Same thing but with more details.
- `whois google.com` - Find out who owns a domain.
- `traceroute google.com` - See every hop your data takes to reach Google. Cool for troubleshooting.

## Downloading and Copying
- `curl https://example.com` - Download a website or file and show it on screen.
- `wget https://example.com/file.zip` - Download a file and save it.
- `scp file.txt user@remote-computer:/path/` - Copy a file to another computer.
- `ssh user@remote-computer` - Log into another computer remotely.
- `sftp user@remote-computer` - Transfer files back and forth securely.

## Looking at Your Network Setup
- `netstat` - What connections do you have open right now?
- `ss -tuln` - Same info but newer and less confusing.
- `arp` - See devices connected to your local network.
- `route` - How does traffic get routed? (Advanced stuff)

## What You'll Get Out of This
- Check if you're actually connected to the internet
- Find IP addresses for websites and servers
- Copy files between computers securely
- Log into remote computers
- Troubleshoot network problems

Tip: If `ping` works but websites don't load, the problem is probably DNS. Try `nslookup` to see what's going on.
