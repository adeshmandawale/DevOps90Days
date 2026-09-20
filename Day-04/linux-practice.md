# Day 04 – Linux Practice: Processes and Services

## Process Checks

### 1. Check running processes

```bash
ps aux --sort=-%cpu | head -10
```

**What I observed:**
> [INSERT YOUR ACTUAL OUTPUT/OBSERVATION HERE]

### 2. Inspect a specific process

```bash
pgrep -a ssh
```

**What I observed:**
> [INSERT YOUR ACTUAL OUTPUT/OBSERVATION HERE]

**Screenshot / terminal output:**

> 📸 **INSERT SCREENSHOT HERE**

---

## Service Checks

I inspected the SSH service. If your system uses a different service, replace `ssh` with the service available on your machine.

### 1. Check service status

```bash
systemctl status ssh
```

**What I observed:**
> [INSERT YOUR ACTUAL OUTPUT/OBSERVATION HERE]

### 2. Check whether the service is enabled

```bash
systemctl is-enabled ssh
```

**What I observed:**
> [INSERT YOUR ACTUAL OUTPUT/OBSERVATION HERE]

**Screenshot / terminal output:**

> 📸 **INSERT SCREENSHOT HERE**

---

## Log Checks

### 1. View recent service logs

```bash
journalctl -u ssh -n 50 --no-pager
```

**What I observed:**
> [INSERT YOUR ACTUAL OUTPUT/OBSERVATION HERE]

### 2. Follow service logs

```bash
journalctl -u ssh -f
```

Press `Ctrl+C` to stop following the logs.

**What I observed:**
> [INSERT YOUR ACTUAL OUTPUT/OBSERVATION HERE]

**Screenshot / terminal output:**

> 📸 **INSERT SCREENSHOT HERE**

---

## Mini Troubleshooting Flow

1. Check whether the process/service is running.
2. Inspect the process and identify its PID.
3. Check the systemd service status.
4. Review recent logs for errors.
5. Take corrective action only after understanding the evidence.

## What I Learned

- `ps` helps identify processes and their resource usage.
- `systemctl` helps inspect and manage systemd services.
- `journalctl` provides useful service logs.
- Troubleshooting should start with evidence instead of immediately restarting or killing processes.

> **Note:** Replace every placeholder with output from my own machine before considering this day complete.
