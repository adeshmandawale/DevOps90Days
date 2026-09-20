# Day 09 – Linux User & Group Management Challenge

## Users & Groups Created

### Users

- `tokyo`
- `berlin`
- `professor`
- `nairobi`

### Groups

- `developers`
- `admins`
- `project-team`

> Run these commands on a suitable Linux environment. Do not use production accounts for this exercise.

---

## 1. Create Users

```bash
sudo useradd -m tokyo
sudo useradd -m berlin
sudo useradd -m professor
sudo passwd tokyo
sudo passwd berlin
sudo passwd professor
```

Verify:

```bash
grep -E '^(tokyo|berlin|professor):' /etc/passwd
ls -ld /home/tokyo /home/berlin /home/professor
```

**My result:**
> [INSERT ACTUAL OUTPUT]

📸 **Screenshot – users created**

> [INSERT SCREENSHOT HERE]

---

## 2. Create Groups

```bash
sudo groupadd developers
sudo groupadd admins
```

Verify:

```bash
grep -E '^(developers|admins):' /etc/group
```

**My result:**
> [INSERT ACTUAL OUTPUT]

---

## 3. Assign Users to Groups

```bash
sudo usermod -aG developers tokyo
sudo usermod -aG developers,admins berlin
sudo usermod -aG admins professor
```

Verify:

```bash
groups tokyo
groups berlin
groups professor
```

**Expected assignment:**

| User | Groups |
|---|---|
| tokyo | developers |
| berlin | developers, admins |
| professor | admins |

📸 **Screenshot – group memberships**

> [INSERT SCREENSHOT HERE]

---

## 4. Shared Developer Directory

Create the directory:

```bash
sudo mkdir -p /opt/dev-project
sudo chgrp developers /opt/dev-project
sudo chmod 775 /opt/dev-project
```

Verify:

```bash
ls -ld /opt/dev-project
```

**My result:**
> [INSERT ACTUAL OUTPUT]

Test file creation:

```bash
sudo -u tokyo touch /opt/dev-project/tokyo-test.txt
sudo -u berlin touch /opt/dev-project/berlin-test.txt
ls -l /opt/dev-project
```

📸 **Screenshot – shared directory**

> [INSERT SCREENSHOT HERE]

---

## 5. Team Workspace

Create the user and group:

```bash
sudo useradd -m nairobi
sudo groupadd project-team
sudo usermod -aG project-team nairobi
sudo usermod -aG project-team tokyo
```

Create and configure the workspace:

```bash
sudo mkdir -p /opt/team-workspace
sudo chgrp project-team /opt/team-workspace
sudo chmod 775 /opt/team-workspace
```

Verify:

```bash
groups nairobi
groups tokyo
ls -ld /opt/team-workspace
```

Test:

```bash
sudo -u nairobi touch /opt/team-workspace/nairobi-test.txt
ls -l /opt/team-workspace
```

📸 **Screenshot – team workspace**

> [INSERT SCREENSHOT HERE]

---

## Commands Used

- `useradd -m`
- `passwd`
- `groupadd`
- `usermod -aG`
- `groups`
- `chgrp`
- `chmod`
- `sudo -u`
- `ls -ld`

## What I Learned

- [LEARNING 1]
- [LEARNING 2]
- [LEARNING 3]

## Final Verification

- [ ] Four users created
- [ ] Three groups created
- [ ] Group memberships verified
- [ ] Shared directories created
- [ ] Permissions verified
- [ ] File creation tested
- [ ] Screenshots added
