
### 1. **Backup a Directory**
This script creates a backup of a directory and saves it as a compressed `.tar.gz` file.
```bash
#!/bin/bash
# Backup script for a directory

SOURCE="/path/to/source"
DEST="/path/to/destination/backup_$(date +%Y%m%d).tar.gz"

tar -czvf $DEST $SOURCE
echo "Backup of $SOURCE completed and stored in $DEST"
```

### 2. **Disk Usage Report**
This script provides a detailed disk usage report of the file system.
```bash
#!/bin/bash
# Disk usage report script

df -h | awk '{print $1, $5}' > disk_usage_report.txt
echo "Disk usage report generated: disk_usage_report.txt"
```

### 3. **Check if a Service is Running**
This script checks if a service (e.g., Apache) is running and restarts it if it’s not.
```bash
#!/bin/bash
# Check if Apache is running and restart if not

SERVICE="apache2"

if ! systemctl is-active --quiet $SERVICE; then
    echo "$SERVICE is not running, restarting..."
    systemctl start $SERVICE
else
    echo "$SERVICE is running"
fi
```

### 4. **Rename Files in Bulk**
This script renames all `.txt` files in a directory by adding a timestamp.
```bash
#!/bin/bash
# Rename .txt files in bulk by adding timestamp

for file in *.txt; do
    mv "$file" "${file%.txt}_$(date +%Y%m%d).txt"
done
echo "Renamed all .txt files with timestamp."
```

### 5. **Monitor CPU Usage**
This script monitors CPU usage and sends an alert if it exceeds a threshold.
```bash
#!/bin/bash
# Monitor CPU usage and alert if above threshold

THRESHOLD=80
CPU_USAGE=$(top -bn1 | grep "Cpu(s)" | awk '{print $2 + $4}')

if (( $(echo "$CPU_USAGE > $THRESHOLD" | bc -l) )); then
    echo "Warning: CPU usage is above $THRESHOLD%. Current usage: $CPU_USAGE%"
else
    echo "CPU usage is normal: $CPU_USAGE%"
fi
```

### 6. **Find and Delete Old Files**
This script finds and deletes files older than 30 days in a specified directory.
```bash
#!/bin/bash
# Delete files older than 30 days

find /path/to/directory -type f -mtime +30 -exec rm {} \;
echo "Deleted files older than 30 days."
```

### 7. **Ping Multiple Servers**
This script pings a list of servers to check if they are reachable.
```bash
#!/bin/bash
# Ping multiple servers

SERVERS=("server1.com" "server2.com" "8.8.8.8")

for server in "${SERVERS[@]}"; do
    if ping -c 1 $server &> /dev/null; then
        echo "$server is reachable"
    else
        echo "$server is not reachable"
    fi
done
```

### 8. **User Account Creation**
This script automates the creation of user accounts with a default home directory and password.
```bash
#!/bin/bash
# Create a user account with a default password

read -p "Enter username: " USERNAME
useradd -m $USERNAME
echo "$USERNAME:password123" | chpasswd
echo "User $USERNAME created with default password."
```

### 9. **File Permission Check**
This script checks the permissions of a given file and outputs whether it's writable, readable, or executable.
```bash
#!/bin/bash
# Check file permissions

FILE="/path/to/file"

if [ -r $FILE ]; then
    echo "$FILE is readable"
fi

if [ -w $FILE ]; then
    echo "$FILE is writable"
fi

if [ -x $FILE ]; then
    echo "$FILE is executable"
fi
```

### 10. **System Uptime Report**
This script generates a report of the system's uptime.
```bash
#!/bin/bash
# System uptime report

UPTIME=$(uptime -p)
echo "System has been up for: $UPTIME"
```

---
