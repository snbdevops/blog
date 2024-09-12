
### 1. **ls** - List directory contents
```bash
ls -l
```
Shows a detailed list of all files and directories in the current directory.

### 2. **cd** - Change directory
```bash
cd /home/user
```
Navigates to the `/home/user` directory.

### 3. **pwd** - Print working directory
```bash
pwd
```
Displays the current directory you are in.

### 4. **mkdir** - Make directory
```bash
mkdir myfolder
```
Creates a new directory named `myfolder`.

### 5. **rmdir** - Remove directory
```bash
rmdir myfolder
```
Deletes the `myfolder` directory (only if it is empty).

### 6. **touch** - Create an empty file
```bash
touch file.txt
```
Creates an empty file named `file.txt`.

### 7. **rm** - Remove file or directory
```bash
rm file.txt
```
Deletes `file.txt`. To remove directories and their contents recursively:
```bash
rm -r foldername
```

### 8. **cp** - Copy files and directories
```bash
cp file1.txt file2.txt
```
Copies `file1.txt` to `file2.txt`. To copy directories:
```bash
cp -r folder1 folder2
```

### 9. **mv** - Move or rename files
```bash
mv file1.txt file2.txt
```
Renames or moves `file1.txt` to `file2.txt`.

### 10. **cat** - Concatenate and display file contents
```bash
cat file.txt
```
Displays the contents of `file.txt`.

### 11. **more** - View file content interactively
```bash
more file.txt
```
Allows interactive file viewing, showing a screen of text at a time.

### 12. **less** - View file content interactively (more advanced than more)
```bash
less file.txt
```
Allows backward navigation in files.

### 13. **head** - Display the beginning of a file
```bash
head file.txt
```
Shows the first 10 lines of `file.txt`.

### 14. **tail** - Display the end of a file
```bash
tail file.txt
```
Shows the last 10 lines of `file.txt`.

### 15. **grep** - Search inside files
```bash
grep "word" file.txt
```
Searches for the word “word” in `file.txt`.

### 16. **find** - Search for files
```bash
find /home -name "file.txt"
```
Searches for `file.txt` starting from the `/home` directory.

### 17. **chmod** - Change file permissions
```bash
chmod 755 file.txt
```
Changes the permissions of `file.txt` to be readable, writable, and executable by the owner, and readable and executable by others.

### 18. **chown** - Change file owner and group
```bash
chown user:group file.txt
```
Changes the owner of `file.txt` to `user` and its group to `group`.

### 19. **ps** - List running processes
```bash
ps aux
```
Displays a detailed list of all running processes.

### 20. **kill** - Terminate processes
```bash
kill 1234
```
Terminates the process with PID `1234`.

### 21. **df** - Display disk space usage
```bash
df -h
```
Shows the disk space usage of file systems in a human-readable format.

### 22. **du** - Estimate file space usage
```bash
du -sh foldername
```
Displays the size of the directory `foldername`.

### 23. **top** - Display running processes
```bash
top
```
Displays a real-time view of running processes and system resources.

### 24. **htop** - Interactive process viewer (more user-friendly than top)
```bash
htop
```
An interactive and detailed view of system processes.

### 25. **ifconfig** - Display network configuration (older version)
```bash
ifconfig
```
Shows network interface configurations.

### 26. **ip** - Show/manipulate routing, devices, and network interfaces
```bash
ip a
```
Displays detailed network interface and IP address information.

### 27. **ping** - Check network connectivity
```bash
ping google.com
```
Sends ICMP packets to `google.com` to test connectivity.

### 28. **wget** - Download files from the internet
```bash
wget https://example.com/file.zip
```
Downloads `file.zip` from the URL.

### 29. **curl** - Transfer data to/from a server
```bash
curl https://example.com
```
Downloads and displays the contents of `https://example.com`.

### 30. **tar** - Archive files
```bash
tar -cvf archive.tar foldername
```
Creates an archive `archive.tar` from the directory `foldername`. To extract:
```bash
tar -xvf archive.tar
```

### 31. **zip** - Compress files into a ZIP archive
```bash
zip archive.zip file1.txt file2.txt
```
Creates a ZIP archive `archive.zip` from `file1.txt` and `file2.txt`.

### 32. **unzip** - Extract files from a ZIP archive
```bash
unzip archive.zip
```
Extracts files from `archive.zip`.

### 33. **nano** - Command-line text editor
```bash
nano file.txt
```
Opens `file.txt` for editing in the Nano editor.

### 34. **vim** - Command-line text editor (more advanced than nano)
```bash
vim file.txt
```
Opens `file.txt` for editing in the Vim editor.

### 35. **scp** - Secure copy (remote file transfer over SSH)
```bash
scp file.txt user@remote:/path/to/destination
```
Copies `file.txt` to the remote server at `/path/to/destination`.

### 36. **rsync** - Sync files between systems
```bash
rsync -avz /local/path user@remote:/remote/path
```
Syncs files from the local machine to a remote machine.

### 37. **man** - Display manual for a command
```bash
man ls
```
Shows the manual page for the `ls` command.

### 38. **history** - Show command history
```bash
history
```
Displays a list of previously run commands.

### 39. **alias** - Create a shortcut for a command
```bash
alias ll='ls -l'
```
Creates an alias `ll` for `ls -l`.

### 40. **uname** - Display system information
```bash
uname -a
```
Shows detailed system information, including kernel version.

### 41. **df** - Display disk space usage
```bash
df -h
```
Shows disk usage in a human-readable format.

### 42. **free** - Display memory usage
```bash
free -h
```
Displays system memory and swap usage in a human-readable format.

### 43. **uptime** - Display system uptime
```bash
uptime
```
Shows how long the system has been running, along with the load average.

### 44. **reboot** - Reboot the system
```bash
sudo reboot
```
Reboots the system immediately.

### 45. **shutdown** - Shutdown the system
```bash
sudo shutdown now
```
Shuts down the system immediately.

### 46. **useradd** - Add a new user
```bash
sudo useradd username
```
Creates a new user with the name `username`.

### 47. **passwd** - Change user password
```bash
passwd
```
Prompts to change the password of the current user.

### 48. **groupadd** - Add a new group
```bash
sudo groupadd groupname
```
Creates a new group called `groupname`.

### 49. **chmod** - Change file permissions
```bash
chmod 644 file.txt
```
Sets the permissions of `file.txt` to be readable and writable by the owner, and readable by others.

### 50. **chown** - Change file ownership
```bash
sudo chown user:group file.txt
```
Changes the ownership of `file.txt` to `user` and its group to `group`.
