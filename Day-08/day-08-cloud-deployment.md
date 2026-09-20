# Day 08 – Cloud Deployment: Docker, Nginx & Web Server

## Deployment Summary

**Cloud Provider:** [AWS EC2 / Utho]  
**Instance OS:** [INSERT OS]  
**Instance IP:** [INSERT IF COMFORTABLE]  
**Web Server:** Nginx

> This document records my actual cloud deployment. Replace all placeholders with my own commands, results, and screenshots.

---

## 1. Cloud Instance

### Instance Details

- Provider: [INSERT]
- Instance type: [INSERT]
- Operating system: [INSERT]
- Public IP: [INSERT]
- Security group/firewall: [INSERT]

📸 **Screenshot – Cloud instance**

> [INSERT SCREENSHOT HERE]

---

## 2. SSH Connection

Example command:

```bash
ssh -i <key-file> <user>@<instance-ip>
```

**My actual command:**

```text
[PASTE ACTUAL SSH COMMAND HERE]
```

**Result:**
> [DESCRIBE SUCCESS OR ISSUE]

📸 **Screenshot – SSH connection**

> [INSERT `ssh-connection.png` HERE]

---

## 3. System Update

Example:

```bash
sudo apt update
sudo apt upgrade -y
```

**Commands I actually used:**

```bash
[INSERT COMMANDS]
```

---

## 4. Install Nginx

```bash
sudo apt install nginx -y
sudo systemctl enable --now nginx
sudo systemctl status nginx
```

**Result:**
> [INSERT ACTUAL RESULT]

📸 **Screenshot – Nginx service**

> [INSERT SCREENSHOT HERE]

---

## 5. Docker

The original task includes Docker. Record the Docker installation and verification here.

```bash
[INSERT ACTUAL DOCKER INSTALLATION COMMANDS]
```

Verify:

```bash
docker --version
sudo systemctl status docker
```

📸 **Screenshot – Docker/Nginx**

> [INSERT `docker-nginx.png` HERE]

---

## 6. Security Group / Port 80

Allow HTTP traffic on **TCP port 80** in the cloud security group/firewall.

**My configuration:**
> [DESCRIBE WHAT I CONFIGURED]

---

## 7. Verify Web Access

Open:

```text
http://<your-instance-ip>
```

Expected result: Nginx welcome page.

📸 **Screenshot – Nginx webpage**

> [INSERT `nginx-webpage.png` HERE]

---

## 8. Nginx Logs

Common log locations:

```bash
sudo tail -n 50 /var/log/nginx/access.log
sudo tail -n 50 /var/log/nginx/error.log
```

Save the relevant logs:

```bash
sudo cp /var/log/nginx/access.log ~/nginx-logs.txt
sudo cp /var/log/nginx/error.log ~/nginx-error-logs.txt
```

**My log observations:**
> [INSERT OBSERVATIONS]

📸 **Screenshot – log contents**

> [INSERT SCREENSHOT HERE]

**Note:** The assignment also asks for `nginx-logs.txt`. Add the actual log file separately to the repository after the deployment.

---

## Challenges Faced

> [DESCRIBE THE ACTUAL ISSUES I FACED AND HOW I SOLVED THEM]

## What I Learned

- [LEARNING 1]
- [LEARNING 2]
- [LEARNING 3]
- [LEARNING 4]
- [LEARNING 5]

## Final Verification

- [ ] Cloud instance running
- [ ] SSH connection successful
- [ ] Nginx installed and running
- [ ] Port 80 accessible
- [ ] Nginx webpage verified
- [ ] Logs collected
- [ ] Screenshots added
- [ ] `nginx-logs.txt` added
