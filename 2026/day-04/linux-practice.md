# Linux Practice Note: Processes, Services, and Logs

**Goal:** Practice inspecting processes, services, and logs on a Linux system. This note includes 6+ commands with recorded output examples. You can run these on your own system and replace the sample outputs with your real ones.

---

## 🔹 Chosen Service: `ssh`

We will inspect the **ssh** service (common on most Linux systems).

---

## 1️⃣ Process Commands

### Command 1: `ps aux | head -n 5`

**Purpose:** View running processes.

```bash
ps aux | head -n 5
```

**Sample Output:**

```
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.1 171620  11448 ?        Ss   10:01   0:01 /sbin/init
root       532  0.0  0.2  50000  18000 ?        Ss   10:02   0:00 sshd
```

---

### Command 2: `pgrep ssh`

**Purpose:** Find PID of ssh process.

```bash
pgrep ssh
```

**Sample Output:**

```
532
```

---

## 2️⃣ Service Commands

### Command 3: `systemctl status ssh`

**Purpose:** Check ssh service status.

```bash
systemctl status ssh
```

**Sample Output:**

```
● ssh.service - OpenBSD Secure Shell server
   Loaded: loaded (/lib/systemd/system/ssh.service; enabled)
   Active: active (running)
```

---

### Command 4: `systemctl list-units --type=service | head`

**Purpose:** List active services.

```bash
systemctl list-units --type=service | head
```

**Sample Output:**

```
ssh.service        loaded active running OpenBSD Secure Shell server
cron.service       loaded active running Regular background program
```

---

## 3️⃣ Log Commands

### Command 5: `journalctl -u ssh -n 5`

**Purpose:** View recent logs for ssh service.

```bash
journalctl -u ssh -n 5
```

**Sample Output:**

```
Jan 29 10:10:01 system sshd[532]: Server listening on 0.0.0.0 port 22
```

---

### Command 6: `tail -n 10 /var/log/syslog`

**Purpose:** View system log entries.

```bash
tail -n 10 /var/log/syslog
```

**Sample Output:**

```
Jan 29 10:11:12 system CRON[901]: pam_unix(cron:session): session opened
```

---

## ✅ Summary Checklist

* ✔ Ran 2 process commands
* ✔ Ran 2 service commands
* ✔ Ran 2 log commands
* ✔ Inspected ssh service

---


This is how you build real DevOps/Linux troubleshooting skills 🚀
