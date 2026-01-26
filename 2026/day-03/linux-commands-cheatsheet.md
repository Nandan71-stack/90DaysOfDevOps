


1. Process Management

| Task                   | Command        | What it does            |                |
| ---------------------- | -------------- | ----------------------- | -------------- |
| Show running processes | `ps aux`       | Lists all processes     |                |
| Real-time process view | `top` / `htop` | Live CPU & memory usage |                |
| Find a process         | `ps aux        | grep nginx`             | Search process |
| Kill by PID            | `kill 1234`    | Graceful stop           |                |
| Force kill             | `kill -9 1234` | Immediate stop          |                |
| Kill by name           | `pkill nginx`  | Kill process by name    |                |
| Background job         | `command &`    | Run in background       |                |
| Resume job             | `fg`           | Bring job to foreground |                |
| Job control            | `jobs`         | Show background jobs    |                |
| Watch command output   | `watch df -h`  | Run command repeatedly  |                |

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
2. File System Commands
| Task             | Command                 | What it does       |
| ---------------- | ----------------------- | ------------------ |
| List files       | `ls -la`                | Detailed listing   |
| Change directory | `cd /path`              | Move between dirs  |
| Current path     | `pwd`                   | Show location      |
| Create file      | `touch file.txt`        | New empty file     |
| Create folder    | `mkdir test`            | New directory      |
| Recursive folder | `mkdir -p a/b/c`        | Nested dirs        |
| Copy file        | `cp a.txt b.txt`        | Copy file          |
| Copy folder      | `cp -r dir1 dir2`       | Copy directory     |
| Move/rename      | `mv old new`            | Move or rename     |
| Delete file      | `rm file.txt`           | Remove file        |
| Delete folder    | `rm -rf dir`            | Force delete       |
| Disk usage       | `df -h`                 | Disk space         |
| Folder size      | `du -sh folder`         | Directory size     |
| Find file        | `find / -name file.txt` | Search files       |
| File permissions | `chmod 755 script.sh`   | Change permissions |
| File owner       | `chown user:group file` | Change owner       |

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
3. Networking & Troubleshooting

| Task               | Command                      | What it does       |
| ------------------ | ---------------------------- | ------------------ |
| Check IP           | `ip a` / `ifconfig`          | Network interfaces |
| Ping server        | `ping google.com`            | Test connectivity  |
| DNS lookup         | `nslookup google.com`        | Resolve DNS        |
| Trace route        | `traceroute google.com`      | Network path       |
| Open ports         | `ss -tulnp`                  | Listening services |
| Active connections | `netstat -anp`               | Network stats      |
| Curl URL           | `curl -I https://google.com` | HTTP headers       |
| Download file      | `wget URL`                   | Fetch file         |
| Test port          | `nc -zv host 80`             | Port open test     |
| Who is using port  | `lsof -i :80`                | Check port usage   |

