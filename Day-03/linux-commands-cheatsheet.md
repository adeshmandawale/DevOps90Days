# Day 03 – Linux Commands Cheat Sheet

## Process Management

| Command | Purpose |
|---|---|
| `ps aux` | List running processes and resource usage. |
| `ps -ef` | Show processes with parent/child information. |
| `pgrep <name>` | Find the PID of a process by name. |
| `top` | Monitor CPU, memory, and processes in real time. |
| `htop` | Interactive process and resource monitor. |
| `kill <PID>` | Send a termination signal to a process. |
| `kill -9 <PID>` | Forcefully terminate a process when normal termination fails. |
| `jobs` | Show jobs running in the current shell. |
| `bg` | Resume a stopped job in the background. |
| `fg` | Bring a background job to the foreground. |

## File System

| Command | Purpose |
|---|---|
| `pwd` | Show the current working directory. |
| `ls -lah` | List files including hidden files with readable sizes. |
| `cd <dir>` | Change the current directory. |
| `find <path> -name <pattern>` | Search for files by name. |
| `du -sh <path>` | Show the total disk usage of a path. |
| `df -h` | Show available and used filesystem space. |
| `mkdir <dir>` | Create a directory. |
| `cp <source> <destination>` | Copy files or directories. |
| `mv <source> <destination>` | Move or rename files. |
| `rm <file>` | Remove a file. |

## Networking

| Command | Purpose |
|---|---|
| `ping <host>` | Test basic network reachability. |
| `ip addr` | Display network interfaces and IP addresses. |
| `ss -tulpn` | Show listening TCP/UDP sockets and processes. |
| `dig <domain>` | Query DNS records. |
| `curl -I <url>` | Check HTTP response headers from a URL. |

## Quick Troubleshooting Flow

1. Check the process: `ps aux` or `top`.
2. Check disk space: `df -h`.
3. Check directory usage: `du -sh <path>`.
4. Check network interfaces: `ip addr`.
5. Check listening ports: `ss -tulpn`.
6. Test connectivity: `ping <host>`.
7. Test an HTTP endpoint: `curl -I <url>`.

## My Most Useful Commands

- Process: `top`
- Disk: `df -h`
- Network: `ss -tulpn`
- HTTP: `curl -I`
- File search: `find`

> Focus: understand what each command tells me instead of memorizing long command lists.
