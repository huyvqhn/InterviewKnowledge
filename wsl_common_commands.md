# WSL Common Commands

Quick reference for Windows Subsystem for Linux (WSL) commands and operations.

## WSL Management (PowerShell)

| Command | Purpose |
| --- | --- |
| `wsl --list --verbose` | List all WSL distributions and their versions |
| `wsl --list --online` | List available distributions for install |
| `wsl --install -d Ubuntu` | Install a specific distribution (e.g., Ubuntu) |
| `wsl --set-default-version 2` | Set WSL 2 as default for new installations |
| `wsl --set-version Ubuntu 2` | Convert existing distro to WSL 2 |
| `wsl --shutdown` | Shut down all running WSL instances |
| `wsl --terminate Ubuntu` | Terminate a specific distribution |
| `wsl --unregister Ubuntu` | Unregister and remove a distribution |
| `wsl --export Ubuntu C:\backup.tar` | Export a distribution to a file |
| `wsl --import MyDistro C:\MyDistro C:\backup.tar` | Import a distribution from file |
| `wsl -d Ubuntu` | Launch a specific distribution |
| `wsl -u root` | Launch as root user |
| `wsl --help` | Display help for WSL commands |

## File System Navigation

| Command | Purpose |
| --- | --- |
| `pwd` | Print working directory |
| `cd ~` | Change to home directory |
| `cd /mnt/c` | Navigate to C: drive from WSL |
| `cd /mnt/d` | Navigate to D: drive from WSL |
| `ls -la` | List files with details and hidden files |
| `ls -lh` | List files with human-readable sizes |
| `tree -L 2` | Show directory tree up to 2 levels deep |
| `find . -name "*.txt"` | Find all .txt files in current directory |
| `locate filename` | Find file by name (requires updatedb) |
| `updatedb` | Update file database for locate command |

## File Operations

| Command | Purpose |
| --- | --- |
| `cp file.txt file_copy.txt` | Copy a file |
| `cp -r directory/ directory_backup/` | Copy directory recursively |
| `mv oldname.txt newname.txt` | Move/rename file or directory |
| `rm file.txt` | Remove file |
| `rm -rf directory/` | Remove directory and contents |
| `mkdir newfolder` | Create new directory |
| `mkdir -p path/to/nested/dir` | Create nested directories |
| `touch newfile.txt` | Create empty file |
| `cat file.txt` | Display file contents |
| `head -n 20 file.txt` | Show first 20 lines |
| `tail -n 20 file.txt` | Show last 20 lines |
| `wc -l file.txt` | Count lines in file |
| `grep "pattern" file.txt` | Search for pattern in file |
| `grep -r "pattern" directory/` | Recursive grep search |
| `chmod 755 script.sh` | Change file permissions |
| `chown user:group file.txt` | Change file owner |

## Directory Operations

| Command | Purpose |
| --- | --- |
| `pwd` | Show current directory path |
| `ls` | List directory contents |
| `ls -la` | List with hidden files and details |
| `du -sh directory/` | Show directory size |
| `du -sh *` | Show size of all items in current directory |
| `df -h` | Show disk space usage |
| `cd -` | Go back to previous directory |
| `pushd directory/` | Push directory to stack and change |
| `popd` | Pop and return to previous directory |

## User & Permission Management

| Command | Purpose |
| --- | --- |
| `whoami` | Display current user |
| `id` | Show user and group IDs |
| `sudo command` | Run command as superuser |
| `sudo -i` | Switch to root shell |
| `sudo su - username` | Switch to another user |
| `passwd` | Change password for current user |
| `useradd -m username` | Create new user |
| `userdel -r username` | Delete user and home directory |
| `usermod -aG groupname username` | Add user to group |
| `groups username` | Show user's groups |
| `sudo visudo` | Edit sudoers file safely |

## Package Management (APT/Ubuntu)

| Command | Purpose |
| --- | --- |
| `sudo apt update` | Update package lists |
| `sudo apt upgrade` | Upgrade installed packages |
| `sudo apt install package` | Install a package |
| `sudo apt remove package` | Remove a package |
| `sudo apt purge package` | Remove package and config files |
| `sudo apt autoremove` | Remove unnecessary packages |
| `sudo apt search keyword` | Search for packages |
| `apt show package` | Show package details |
| `dpkg -l` | List installed packages |
| `dpkg -l \| grep keyword` | Find installed package by keyword |

## Popular Ubuntu Commands

| Command | Purpose |
| --- | --- |
| `snap install package` | Install a snap package |
| `snap remove package` | Remove a snap package |
| `snap list` | List installed snap packages |
| `snap refresh` | Update all snap packages |
| `flatpak install flathub package` | Install a Flatpak package |
| `flatpak run package` | Run a Flatpak application |
| `ufw enable` | Enable Ubuntu firewall |
| `ufw status` | Check firewall status |
| `ufw allow 22` | Allow port 22 (SSH) through firewall |
| `ufw deny 80` | Deny port 80 |
| `journalctl -u service` | View systemd service logs |
| `journalctl -f` | Follow system logs in real-time |
| `systemctl start service` | Start a systemd service |
| `systemctl stop service` | Stop a systemd service |
| `systemctl enable service` | Enable service to start on boot |
| `systemctl status service` | Check service status |
| `timedatectl` | Show/set system time and date |
| `timedatectl set-timezone America/New_York` | Set system timezone |
| `add-apt-repository ppa:repository` | Add a PPA repository |
| `apt-key add key.asc` | Add GPG key for repository |
| `update-alternatives --config editor` | Configure default editor |
| `gsettings set org.gnome.desktop.interface gtk-theme 'Adwaita'` | Set GNOME theme (if GUI) |
| `xdg-open file.pdf` | Open file with default application |
| `notify-send "Title" "Message"` | Send desktop notification |
| `screen -S session` | Start a new screen session |
| `screen -r session` | Reattach to screen session |
| `tmux new -s session` | Start tmux session |
| `tmux attach -t session` | Attach to tmux session |
| `crontab -e` | Edit cron jobs |
| `crontab -l` | List cron jobs |
| `at now + 1 hour` | Schedule command to run later |
| `rsync -av source/ dest/` | Sync files/directories efficiently |
| `scp file.txt user@host:/path/` | Secure copy to remote host |
| `ssh user@host` | Connect to remote host via SSH |
| `ssh-keygen -t rsa` | Generate SSH key pair |
| `ssh-copy-id user@host` | Copy SSH key to remote host |
| `mount /dev/sdb1 /mnt` | Mount a filesystem |
| `umount /mnt` | Unmount a filesystem |
| `fdisk -l` | List disk partitions |
| `lsblk` | List block devices |
| `blkid` | Show block device attributes |
| `parted /dev/sda print` | Show partition table |
| `mkfs.ext4 /dev/sdb1` | Format partition as ext4 |
| `fsck /dev/sdb1` | Check and repair filesystem |
| `tune2fs -l /dev/sdb1` | Show ext filesystem info |
| `swapon /dev/sdb2` | Enable swap partition |
| `swapoff /dev/sdb2` | Disable swap partition |
| `free -h` | Show memory and swap usage |
| `vmstat 1` | Show virtual memory statistics |
| `iostat -x 1` | Show I/O statistics |
| `sar -u 1` | Show CPU usage over time |
| `uptime` | Show system uptime and load |
| `w` | Show who is logged in |
| `last` | Show last logins |
| `who` | Show current users |
| `finger user` | Show user information |
| `chsh -s /bin/zsh` | Change default shell |
| `locale` | Show current locale settings |
| `localectl set-locale LANG=en_US.UTF-8` | Set system locale |
| `update-locale LANG=en_US.UTF-8` | Update locale for current user |
| `dpkg-reconfigure tzdata` | Reconfigure timezone |
| `apt-cache policy package` | Show package version info |
| `apt-mark hold package` | Prevent package from being upgraded |
| `apt-mark unhold package` | Allow package upgrades |
| `debsums -c` | Check package file integrity |
| `dpkg --get-selections` | List all installed packages |
| `apt-rdepends package` | Show reverse dependencies |
| `apt-cache depends package` | Show package dependencies |
| `apt-cache rdepends package` | Show reverse dependencies |
| `apt-file search filename` | Find package containing file |
| `apt-file list package` | List files in package |
| `dpkg -S filename` | Find package owning file |
| `dpkg -L package` | List files in installed package |
| `dpkg -c package.deb` | List contents of .deb file |
| `dpkg -i package.deb` | Install .deb package |
| `dpkg -r package` | Remove .deb package |
| `alien package.rpm` | Convert RPM to DEB (if alien installed) |
| `checkinstall` | Create .deb from source compilation |
| `make` | Build from source |
| `make install` | Install from source |
| `./configure` | Configure source build |
| `cmake .` | Generate build files with CMake |
| `gcc file.c -o executable` | Compile C program |
| `g++ file.cpp -o executable` | Compile C++ program |
| `python3 script.py` | Run Python 3 script |
| `pip3 install package` | Install Python package |
| `node script.js` | Run Node.js script |
| `npm install package` | Install Node.js package |
| `java -version` | Check Java version |
| `javac file.java` | Compile Java file |
| `java file` | Run Java program |
| `gradle build` | Build with Gradle |
| `mvn compile` | Compile with Maven |
| `docker run image` | Run Docker container |
| `docker build -t tag .` | Build Docker image |
| `docker ps` | List running containers |
| `kubectl get pods` | List Kubernetes pods |
| `terraform init` | Initialize Terraform |
| `ansible-playbook playbook.yml` | Run Ansible playbook |

## System Information

| Command | Purpose |
| --- | --- |
| `uname -a` | Show system information |
| `uname -r` | Show kernel release |
| `hostnamectl` | Show hostname and OS info |
| `lsb_release -a` | Show Linux distribution info |
| `cat /etc/os-release` | Display OS details |
| `lscpu` | Show CPU information |
| `free -h` | Show memory usage (human-readable) |
| `top` | Show running processes and resource usage |
| `htop` | Interactive process viewer (if installed) |
| `ps aux` | List all running processes |
| `systemctl status` | Show system status |
| `date` | Show current date and time |
| `uptime` | Show how long system has been running |

## Process Management

| Command | Purpose |
| --- | --- |
| `ps aux` | List all processes |
| `ps aux \| grep keyword` | Find process by keyword |
| `kill PID` | Terminate process by ID |
| `kill -9 PID` | Force terminate process |
| `killall processname` | Terminate all processes by name |
| `fg` | Bring background job to foreground |
| `bg` | Resume suspended job in background |
| `jobs` | List background jobs |
| `nohup command &` | Run command immune to hangups |

## Text Processing & Manipulation

| Command | Purpose |
| --- | --- |
| `cat file.txt` | Display file contents |
| `less file.txt` | View file with pagination |
| `more file.txt` | View file (older pagination) |
| `nano file.txt` | Open file in nano editor |
| `vim file.txt` | Open file in vim editor |
| `echo "text"` | Print text to stdout |
| `echo "text" > file.txt` | Redirect output to file (overwrite) |
| `echo "text" >> file.txt` | Append output to file |
| `sed 's/old/new/' file.txt` | Replace text (stream editor) |
| `awk '{print $1}' file.txt` | Print specific columns |
| `cut -d',' -f1 file.csv` | Extract columns from CSV |
| `sort file.txt` | Sort lines |
| `sort -u file.txt` | Sort and remove duplicates |
| `uniq file.txt` | Show unique lines |
| `tr 'a-z' 'A-Z' < file.txt` | Translate characters |

## Git Operations (if installed)

| Command | Purpose |
| --- | --- |
| `git config --global user.name "Name"` | Set global git user |
| `git config --global user.email "email@domain"` | Set global git email |
| `git clone <repo>` | Clone repository |
| `git status` | Show repository status |
| `git add file.txt` | Stage file for commit |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Commit staged changes |
| `git push` | Push commits to remote |
| `git pull` | Fetch and merge remote changes |
| `git branch -a` | List all branches |
| `git checkout -b branchname` | Create and checkout new branch |
| `git log --oneline` | Show commit history (compact) |
| `git diff` | Show uncommitted changes |

## Networking

| Command | Purpose |
| --- | --- |
| `ip addr show` | Show network interfaces and IPs |
| `ipconfig` (Windows) | Show Windows IP configuration |
| `ping hostname` | Test connectivity to host |
| `curl https://example.com` | Fetch URL contents |
| `wget https://example.com/file.zip` | Download file |
| `netstat -tlnp` | Show listening ports and processes |
| `ss -tlnp` | Modern netstat alternative |
| `nslookup example.com` | DNS lookup |
| `dig example.com` | Advanced DNS lookup |
| `traceroute example.com` | Trace route to host |
| `hostname -I` | Show local IP address |

## Environment & Variables

| Command | Purpose |
| --- | --- |
| `env` | Show all environment variables |
| `echo $PATH` | Show PATH variable |
| `export VAR=value` | Set environment variable |
| `export PATH=$PATH:/new/path` | Add to PATH |
| `echo $HOME` | Show home directory path |
| `source ~/.bashrc` | Reload bash configuration |
| `alias mycommand='long command'` | Create command alias |
| `unalias mycommand` | Remove alias |
| `type command` | Show command type/path |
| `which command` | Show full path to executable |

## Compression & Archives

| Command | Purpose |
| --- | --- |
| `tar -czf archive.tar.gz folder/` | Create gzip tar archive |
| `tar -xzf archive.tar.gz` | Extract gzip tar archive |
| `tar -tf archive.tar.gz` | List contents of archive |
| `zip -r archive.zip folder/` | Create zip archive |
| `unzip archive.zip` | Extract zip archive |
| `gzip file.txt` | Compress file with gzip |
| `gunzip file.txt.gz` | Decompress gzip file |

## Useful Shortcuts

| Shortcut | Purpose |
| --- | --- |
| `Ctrl+C` | Terminate current command |
| `Ctrl+Z` | Suspend current command |
| `Ctrl+A` | Move cursor to start of line |
| `Ctrl+E` | Move cursor to end of line |
| `Ctrl+R` | Search command history |
| `Tab` | Auto-complete commands/paths |
| `!!` | Repeat last command |
| `!keyword` | Run last command starting with keyword |
| `Up/Down Arrow` | Navigate command history |
| `Ctrl+U` | Clear line before cursor |
| `Ctrl+K` | Clear line after cursor |

## Bash Profile Configuration

Common locations to add aliases and functions:
- `~/.bashrc` — bash-specific configuration
- `~/.bash_profile` — login shell configuration
- `~/.profile` — general shell configuration

```bash
# Example: Add to ~/.bashrc
alias ll='ls -lah'
alias gs='git status'
alias gp='git push'
alias ll='ls -lah'
export PATH="$PATH:/usr/local/go/bin"
```

## WSL-Specific Tips

| Tip | Details |
| --- | --- |
| Access Windows from WSL | Use `/mnt/c`, `/mnt/d`, etc. to access Windows drives |
| Access WSL from Windows | Type `\\wsl$` in File Explorer or use `wsl` command in PowerShell |
| Windows executables in WSL | Run `.exe` files directly (e.g., `notepad.exe filename.txt`) |
| Clipboard operations | Install `xclip` to work with Windows clipboard in WSL |
| X11 forwarding | Use WSLg for GUI apps; requires WSL 2 with Windows 11 or later |
| Performance | WSL 2 is slower with Windows files; keep projects in Linux filesystem |
| Interoperability | Use `/proc/version` to detect if running in WSL |

## Performance & Optimization

```bash
# Check WSL version
wsl --version

# Show WSL instance details
wsl -l -v

# Optimize disk usage
wsl --shutdown
# Delete unnecessary files from /mnt/c
# Restart WSL
wsl

# Monitor resource usage
top
free -h
df -h
```

## Troubleshooting

| Issue | Solution |
| --- | --- |
| WSL won't start | Run `wsl --shutdown` then restart |
| Slow performance | Move project files from `/mnt/c` to `~` (Linux filesystem) |
| Permission denied | Use `sudo` or adjust file permissions with `chmod` |
| Package not found | Run `sudo apt update` first |
| DNS issues | Edit `/etc/resolv.conf` or restart WSL |
| Out of memory | Adjust WSL resource limits in `.wslconfig` |

## Resource Configuration (.wslconfig)

Create `C:\Users\YourUsername\.wslconfig` to customize WSL:

```ini
[wsl2]
memory=8GB
processors=4
swap=2GB
localhostForwarding=true

[interop]
enabled=true
appendWindowsPath=true
```
