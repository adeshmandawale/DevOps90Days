# Day 07 – Linux File System Hierarchy & Scenario Practice

## Part 1: Linux File System Hierarchy

### Core Directories

| Directory | Purpose | My Observation |
|---|---|---|
| `/` | Root of the Linux filesystem. Everything starts here. | [RUN `ls -l /` AND ADD 1–2 OBSERVATIONS] |
| `/home` | Contains normal users' home directories. | [RUN `ls -l /home`] |
| `/root` | Home directory of the root user. | [RUN `ls -l /root` — use sudo if needed] |
| `/etc` | System and application configuration files. | [RUN `ls -l /etc`] |
| `/var/log` | System and application log files. | [RUN `ls -l /var/log`] |
| `/tmp` | Temporary files used by applications and users. | [RUN `ls -l /tmp`] |

### Additional Directories

| Directory | Purpose | My Observation |
|---|---|---|
| `/bin` | Essential command binaries. | [RUN `ls -l /bin`] |
| `/usr/bin` | Common user command binaries. | [RUN `ls -l /usr/bin | head`] |
| `/opt` | Optional or third-party application software. | [RUN `ls -l /opt`] |

📸 **Screenshot placeholder – filesystem observations**

> [INSERT TERMINAL SCREENSHOT HERE]

### Useful Checks

Find large log files:

```bash
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

Check hostname configuration:

```bash
cat /etc/hostname
```

Check my home directory:

```bash
ls -la ~
```

---

# Part 2: Scenario-Based Practice

## Scenario 1 – Service Not Starting

**Problem:** A service called `myapp` failed to start after a reboot.

### Step 1

```bash
systemctl status myapp
```

**Why:** Check whether the service is active, failed, or stopped.

### Step 2

```bash
journalctl -u myapp -n 50 --no-pager
```

**Why:** Review recent service errors and events.

### Step 3

```bash
systemctl is-enabled myapp
```

**Why:** Check whether the service is configured to start during boot.

### Step 4

```bash
systemctl list-units --type=service --state=failed
```

**Why:** Check whether other services have failed.

**My conclusion:**
> [WRITE WHAT I WOULD CHECK NEXT BASED ON THE ERROR]

---

## Scenario 2 – High CPU Usage

**Problem:** The application server is slow.

### Step 1

```bash
top
```

### Step 2

```bash
ps aux --sort=-%cpu | head -10
```

### Step 3

Record the PID of the highest CPU process.

**PID:** [INSERT PID]

**What I found:**
> [INSERT ACTUAL OBSERVATION]

📸 **Screenshot placeholder – high CPU investigation**

> [INSERT SCREENSHOT HERE]

---

## Scenario 3 – Finding Service Logs

**Problem:** Find logs for a systemd-managed service.

```bash
systemctl status ssh
journalctl -u ssh -n 50 --no-pager
journalctl -u ssh -f
```

**What I learned:**
> [INSERT OBSERVATION]

---

## Scenario 4 – Permission Denied

**Problem:** `backup.sh` cannot be executed.

### Step 1 – Check permissions

```bash
ls -l /home/user/backup.sh
```

### Step 2 – Add execute permission

```bash
chmod +x /home/user/backup.sh
```

### Step 3 – Verify

```bash
ls -l /home/user/backup.sh
```

### Step 4 – Run it

```bash
./backup.sh
```

**What I learned:**
> [INSERT OBSERVATION]

## Key Takeaways

- Linux directories have specific purposes.
- `/etc` is important for configuration.
- `/var/log` is important during troubleshooting.
- `systemctl` and `journalctl` are useful for service problems.
- Permissions determine whether users can read, write, or execute files.

> **Note:** Add actual `ls -l` observations and terminal screenshots before marking this day complete.
