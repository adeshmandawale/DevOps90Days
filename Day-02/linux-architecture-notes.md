# Day 02 – Linux Architecture, Processes, and systemd

## 1. Linux Architecture

Linux can be understood in three main layers:

- **Kernel:** The core of Linux. It manages CPU, memory, storage, networking, devices, and processes.
- **User Space:** Where applications, shells, utilities, and services run. Users normally interact with Linux through this layer.
- **Init / systemd:** The first major userspace process started by the kernel (`PID 1`). It initializes the system and manages services.

Basic flow:

`Hardware → Kernel → systemd → Services / Applications → User`

## 2. Processes

A **process** is a running instance of a program. Every process has a **PID (Process ID)**.

Processes can be:
- Created by another process (parent → child).
- Managed by the kernel.
- Stopped, resumed, or terminated using signals.
- Monitored using commands such as `ps` and `top`.

### Common Process States

- **Running (R):** Currently executing or ready to execute.
- **Sleeping (S):** Waiting for an event or resource.
- **Stopped (T):** Execution has been paused.
- **Zombie (Z):** Process has finished, but its parent has not yet collected its exit status.

## 3. systemd

`systemd` is the service and system manager used by many modern Linux distributions.

It is responsible for:
- Starting services during boot.
- Managing service dependencies.
- Starting, stopping, restarting, and checking services.
- Managing targets and system startup.
- Working with system logs through `journald`.

Useful commands:

```bash
systemctl status nginx
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
systemctl enable nginx
```

For troubleshooting, `systemctl status <service>` is often one of the first commands I would use.

## 4. Five Linux Commands I Use / Would Use Daily

1. `ls` – List files and directories.
2. `cd` – Navigate through directories.
3. `ps` – View running processes.
4. `top` – Monitor CPU, memory, and processes in real time.
5. `systemctl` – Manage and troubleshoot systemd services.

## Why This Matters for DevOps

Understanding processes and systemd helps troubleshoot real production problems such as crashed services, high CPU or memory usage, failed startups, and service restarts. These fundamentals make Linux troubleshooting much easier.
