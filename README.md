# Bash Commands Cheatsheet

> Essential bash commands. If this repo helped you in any way, consider giving it a star ⭐

## Table of Contents
- [Basic Command Structure](#basic-command-structure)
- [File Navigation & Management](#file-navigation--management)
- [File Viewing & Editing](#file-viewing--editing)
- [System Information](#system-information)
- [File Permissions](#file-permissions)
- [Process Management](#process-management)
- [Environment & Variables](#environment--variables)
- [Network](#network)
- [Package Management](#package-management-ubuntudebian)
- [Repository Commands](#repository-commands)
- [Useful Combinations](#useful-combinations)
- [Script-Related](#script-related)
- [Common Use Cases](#common-use-cases)
- [Safety Notes](#safety-notes)

## Basic Command Structure
```bash
command [options] [arguments]    # General syntax
command --help                  # Get help for any command
man command                     # Show manual page
info command                   # Detailed documentation
```

## File Navigation & Management
```bash
pwd                            # print working directory
ls -la                         # list all files with details
cd /path/to/dir               # change directory
mkdir -p dir1/dir2            # create nested directories
rm -rf dir                    # remove directory recursively (use with caution!)
cp -r src/ dest/              # copy directories recursively
mv old_name new_name          # move/rename files
touch file.txt                # create empty file
find . -name "*.py"           # find files by pattern
tree                          # display directory structure
```

## File Viewing & Editing
```bash
cat file.txt                  # display file content
less file.txt                 # view file with pagination
head -n 5 file.txt           # show first 5 lines
tail -f file.log             # follow log file updates
grep "pattern" file          # search text in file
nano file.txt                # simple text editor
vim file.txt                 # advanced text editor
diff file1 file2             # compare files
```

## System Information 
```bash
top                          # process viewer
htop                         # enhanced process viewer
df -h                        # disk space usage
free -h                      # memory usage 
ps aux | grep python        # find python processes
which python3               # locate command
uname -a                    # system information
lsb_release -a             # distribution info
uptime                     # system uptime
lscpu                      # CPU information
```

## File Permissions 
```bash
chmod +x script.sh          # make script executable
chmod 755 file             # set permissions (rwxr-xr-x)
chown user:group file      # change file owner
chmod -R 644 dir          # recursively change files
chmod -R 755 dir          # recursively change directories
stat file                 # display file status
```

## Process Management 
```bash
ps aux                     # list all processes
kill -9 PID               # force kill process
bg                        # send process to background
fg                        # bring process to foreground
nohup command &           # run command after terminal closes
jobs                      # list background jobs
pgrep process_name        # find process ID
pkill process_name        # kill process by name
```

## Environment & Variables
```bash
export PATH=$PATH:/dir    # add to PATH
echo $HOME               # print environment variable
source ~/.bashrc         # reload bash configuration
env                      # show all environment vars
printenv                 # print environment
set                      # show all shell variables
```

## Network
```bash
ping google.com          # test connectivity
curl http://site.com     # http request
wget http://site.com     # download file
sudo netstat -tulpn      # show active ports
ssh user@hostname        # ssh connection
ifconfig                 # network interface config
ip addr                  # modern interface config
dig domain.com          # DNS lookup
traceroute domain.com   # trace packet route
```

## Package Management (Ubuntu/Debian)
```bash
sudo apt update          # update package list 
sudo apt upgrade         # upgrade installed packages
sudo apt install pkg     # install package
sudo apt remove pkg      # remove package
sudo apt autoremove      # clean unused packages
apt search pkg           # search for package
apt show pkg            # show package details
```

## Repository Commands
```bash
git init                 # initialize repository
git clone url           # clone repository
git status              # check status
git add .               # stage all changes
git commit -m "msg"     # commit with message
git push origin main    # push to remote
git pull               # update local repository
```

## Useful Combinations
```bash
command1 | command2      # pipe output
command > file.txt       # redirect output to file
command >> file.txt      # append output to file
command1 && command2     # run if previous succeeds
command1 || command2     # run if previous fails
time command            # measure execution time
```

## Script-Related
```bash
#!/bin/bash             # shebang line
set -e                  # exit on error
set -x                  # debug mode
$1, $2                  # script arguments
$?                      # last command exit status
$#                      # number of arguments
$$                      # process ID of the script
$@                      # all arguments
$0                      # script name
```

## Common Use Cases
```bash
# Find and replace in files
find . -type f -name "*.txt" -exec sed -i 's/old/new/g' {} +

# Monitor system resources
watch -n 1 'free -h; echo; df -h'

# Search command history
history | grep "command"

# Compress/Extract
tar -czf archive.tar.gz dir/    # compress
tar -xzf archive.tar.gz         # extract

# Find large files
find / -type f -size +100M -exec ls -lh {} \;
```

## Safety Notes
- Always double-check before using `rm -rf`
- Use `rm -i` for interactive deletion
- Back up important files before using `chmod -R` or `chown -R`
- Test scripts in isolated environment first
- Use `sudo` with caution
- Create backup before system changes: `cp file{,.bak}`
- Use `--dry-run` when available to test commands

## License

MIT License - Feel free to share and modify with attribution.

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

Please ensure your PR:
- Follows consistent formatting
- Includes clear descriptions
- Tests all commands
- Updates Table of Contents if needed

Feel free to submit issues and enhancement requests!
