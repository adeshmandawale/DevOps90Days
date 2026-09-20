# Day 04 – Linux Practice: Processes and Services

## Process Checks

### 1. Check running processes

```bash
ps aux --sort=-%cpu | head -10
```

**What I observed:**

The top CPU consumer was the -bash shell process (PID 2956, user ubuntu) at 0.3% CPU and 0.5% memory — this is simply the interactive shell session I was using to run the command itself. All other processes in the top 10 showed 0.0% CPU usage, meaning the system was essentially idle at the time of the snapshot.

<img width="1911" height="290" alt="image" src="https://github.com/user-attachments/assets/ce844837-ae0d-4a0a-ad91-c4e776c6449f" />

### 2. Inspect a specific process

```bash
pgrep -a ssh
```

**What I observed:**

pgrep -a ssh showed the main sshd daemon (PID 688) configured for EC2 Instance Connect, plus two active SSH sessions for user ubuntu — one on pts/0 and one on pts/1. SSH is running normally with two concurrent logins.

**Screenshot / terminal output:**

<img width="1915" height="162" alt="image" src="https://github.com/user-attachments/assets/16917b55-e817-4b63-843e-0f931a9ba1be" />


---

## Service Checks

I inspected the SSH service. If your system uses a different service, replace `ssh` with the service available on your machine.

### 1. Check service status

```bash
systemctl status ssh
```

**What I observed:**

SSH is active and running fine since boot (~1h 45m), using minimal memory. The ec2-instance-connect.conf file confirms Instance Connect is properly configured. No issues.

### 2. Check whether the service is enabled

```bash
systemctl is-enabled ssh
```

**What I observed:**

systemctl is-enabled ssh returned disabled — meaning SSH won't automatically start on the next reboot. It's still running now, but this only affects boot-time startup, not the current session.

**Screenshot / terminal output:**

<img width="627" height="50" alt="image" src="https://github.com/user-attachments/assets/15ba5f27-5e13-4667-8ab5-0577ab949e52" />

---

## Log Checks

### 1. View recent service logs

```bash
journalctl -u ssh -n 50 --no-pager
```

**What I observed:**

Logs show normal SSH restarts around reboots and successful Instance Connect logins. One suspicious login attempt as root from IP 45.10.175.77 was rejected before authentication — likely automated scanning, nothing successful.

### 2. Follow service logs

```bash
journalctl -u ssh -f
```

Press `Ctrl+C` to stop following the logs.

**What I observed:**

journalctl -u ssh -f shows live SSH activity in real time. Several unknown IPs (167.57.205.111, 186.61.153.88, 181.4.222.63, 41.92.112.32) connected and closed without authenticating — likely automated scans. Two successful logins were accepted for user ubuntu, from IPs 152.58.33.56 and 152.58.31.240, both using the same public key.

**Screenshot / terminal output:**

<img width="1897" height="311" alt="image" src="https://github.com/user-attachments/assets/736bcc15-9fab-4229-9a16-5d357c7d3356" />

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
