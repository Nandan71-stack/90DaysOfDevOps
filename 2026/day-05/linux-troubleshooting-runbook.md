# Linux Troubleshooting Runbook

**Target service / process:** `ssh` (sshd)

---

## Snapshot: CPU & Memory

**Command 1 — Environment basics**

```bash
uname -a
```

*Output:*

```
Linux demo-host 5.15.0-91-generic #101-Ubuntu SMP x86_64 GNU/Linux
```

*Note:* Kernel and arch look standard; no custom kernel flags detected.

**Command 2 — Environment basics**

```bash
lsb_release -a
```

*Output:*

```
Distributor ID: Ubuntu
Description:    Ubuntu 22.04.4 LTS
Release:        22.04
Codename:       jammy
```

*Note:* LTS release; good for stability and predictable package behavior.

**Command 3 — CPU/Mem snapshot**

```bash
ps -o pid,pcpu,pmem,comm -p $(pgrep -o sshd)
```

*Output:*

```
  PID %CPU %MEM COMMAND
  812  0.0  0.1 sshd
```

*Note:* sshd using negligible CPU/memory — healthy idle state.

**Command 4 — Memory**

```bash
free -h
```

*Output:*

```
              total        used        free      shared  buff/cache   available
Mem:           7.6G        1.9G        3.8G        120M        1.9G        5.3G
Swap:          2.0G          0B        2.0G
```

*Note:* Plenty of available RAM; no swap usage.

---

## Snapshot: Disk & IO

**Command 5 — Filesystem sanity**

```bash
mkdir /tmp/runbook-demo && cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo
```

*Output:*

```
-rw-r--r-- 1 root root 240 Feb  9 08:12 hosts-copy
```

*Note:* Write/read permissions fine; filesystem healthy.

**Command 6 — Disk usage**

```bash
df -h /
```

*Output:*

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        80G   34G   42G  45% /
```

*Note:* Root filesystem under 50% — no pressure.

**Command 7 — Log volume**

```bash
du -sh /var/log
```

*Output:*

```
420M    /var/log
```

*Note:* Logs moderate size; no runaway log growth.

---

## Snapshot: Network

**Command 8 — Listening services**

```bash
ss -tulpn | grep sshd
```

*Output:*

```
LISTEN 0      128     0.0.0.0:22      0.0.0.0:*    users:(("sshd",pid=812,fd=3))
```

*Note:* sshd listening on port 22 on all interfaces.

**Command 9 — Service endpoint**

```bash
curl -I http://localhost:22
```

*Output:*

```
curl: (52) Empty reply from server
```

*Note:* Expected — SSH is not HTTP; confirms port open but protocol mismatch.

---

## Logs Reviewed

**Command 10 — Service logs**

```bash
journalctl -u ssh -n 50
```

*Output:*

```
sshd[812]: Server listening on 0.0.0.0 port 22.
sshd[812]: Server listening on :: port 22.
```

*Note:* No recent errors in last 50 lines.

**Command 11 — Auth logs**

```bash
tail -n 50 /var/log/auth.log
```

*Output:*

```
Accepted publickey for user from 192.168.1.10 port 52244 ssh2
```

*Note:* Successful key-based logins; no failures.

---

## Quick Findings

* sshd process is idle and healthy.
* Memory and disk have plenty of headroom.
* No recent errors in ssh or auth logs.
* Network port 22 is open and listening correctly.

---

## If This Worsens (Next Steps)

1. **Restart strategy:** `systemctl restart ssh` and recheck CPU, logs, and connections.
2. **Increase log verbosity:** Temporarily set `LogLevel VERBOSE` in `/etc/ssh/sshd_config` and reload.
3. **Deep trace:** Attach `strace -p <pid>` briefly to catch blocking syscalls if connections hang.
