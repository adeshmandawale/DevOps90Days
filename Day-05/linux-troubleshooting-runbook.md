# Day 05 – Linux Troubleshooting Runbook

## Target Service / Process

**Target:** SSH service (`ssh`)  
> If I choose another service, I will replace `ssh` throughout this runbook.

---

## 1. Environment Basics

### Check OS and kernel

```bash
uname -a
cat /etc/os-release
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND 1–2 LINE INTERPRETATION]

📸 **Screenshot placeholder – environment checks**

> [INSERT SCREENSHOT HERE]

---

## 2. Filesystem Sanity

### Create a temporary test directory

```bash
mkdir -p /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy
ls -l /tmp/runbook-demo
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

### Check filesystem space

```bash
df -h
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

📸 **Screenshot placeholder – filesystem checks**

> [INSERT SCREENSHOT HERE]

---

## 3. CPU and Memory

### Check top processes

```bash
ps -eo pid,pcpu,pmem,comm --sort=-pcpu | head
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

### Check memory

```bash
free -h
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

📸 **Screenshot placeholder – CPU/memory**

> [INSERT SCREENSHOT HERE]

---

## 4. Disk / I/O

### Check directory usage

```bash
du -sh /var/log
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

### Check system activity

```vmstat 1 5```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

📸 **Screenshot placeholder – disk/I/O**

> [INSERT SCREENSHOT HERE]

---

## 5. Network

### Check listening ports

```bash
ss -tulpn
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

### Test connectivity

```bash
ping -c 4 8.8.8.8
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

📸 **Screenshot placeholder – network**

> [INSERT SCREENSHOT HERE]

---

## 6. Logs

### Check recent SSH logs

```bash
journalctl -u ssh -n 50 --no-pager
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

### Check service status

```bash
systemctl status ssh --no-pager
```

**Observation:**
> [INSERT ACTUAL OUTPUT AND INTERPRETATION]

📸 **Screenshot placeholder – logs/service status**

> [INSERT SCREENSHOT HERE]

---

## Quick Findings

- CPU:
> [INSERT FINDING]

- Memory:
> [INSERT FINDING]

- Disk:
> [INSERT FINDING]

- Network:
> [INSERT FINDING]

- Logs/service:
> [INSERT FINDING]

## If This Worsens

1. Confirm whether the issue is isolated to one process/service.
2. Review logs and resource usage before restarting anything.
3. If necessary, collect additional evidence such as `strace`, process details, or extended logs before escalation.

## What I Learned

> [ADD 3 SHORT LEARNINGS FROM MY ACTUAL TROUBLESHOOTING DRILL]

> **Important:** This runbook intentionally contains placeholders because the assignment requires evidence from my own machine.
