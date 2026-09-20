# Day 10 – File Permissions & File Operations Challenge

## Files Created

- `devops.txt`
- `notes.txt`
- `script.sh`
- `project/`

---

## 1. Create Files

```bash
touch devops.txt
echo "Linux permissions practice" > notes.txt
vim script.sh
```

Content of `script.sh`:

```bash
echo "Hello DevOps"
```

Verify:

```bash
ls -l devops.txt notes.txt script.sh
```

📸 **Screenshot – initial permissions**

> [INSERT SCREENSHOT HERE]

---

## 2. Read Files

Read `notes.txt`:

```bash
cat notes.txt
```

View `script.sh`:

```bash
vim -R script.sh
```

First five lines of `/etc/passwd`:

```bash
head -n 5 /etc/passwd
```

Last five lines:

```bash
tail -n 5 /etc/passwd
```

---

## 3. Understand Permissions

Linux permissions follow:

```text
rwx rwx rwx
│   │   └── others
│   └────── group
└────────── owner
```

Values:

- `r = 4`
- `w = 2`
- `x = 1`

Check current permissions:

```bash
ls -l devops.txt notes.txt script.sh
```

**My initial permissions:**

| File | Initial permissions | Meaning |
|---|---|---|
| devops.txt | [INSERT] | [INSERT] |
| notes.txt | [INSERT] | [INSERT] |
| script.sh | [INSERT] | [INSERT] |

---

## 4. Modify Permissions

### Make script executable

```bash
chmod +x script.sh
./script.sh
```

**Result:**
> [INSERT ACTUAL OUTPUT]

### Make devops.txt read-only

```bash
chmod a-w devops.txt
```

### Set notes.txt to 640

```bash
chmod 640 notes.txt
```

Meaning:

- Owner: `rw-`
- Group: `r--`
- Others: `---`

### Create project directory with 755

```bash
mkdir project
chmod 755 project
```

Verify all changes:

```bash
ls -ld project
ls -l devops.txt notes.txt script.sh
```

📸 **Screenshot – permission changes**

> [INSERT SCREENSHOT HERE]

---

## 5. Test Permissions

### Test read-only file

Attempt to write:

```bash
echo "test" >> devops.txt
```

**Expected/actual result:**
> [INSERT ACTUAL RESULT OR ERROR]

### Test execution without permission

First remove execute permission:

```bash
chmod -x script.sh
./script.sh
```

**Expected/actual result:**
> [INSERT ACTUAL RESULT OR ERROR]

Restore execute permission:

```bash
chmod +x script.sh
```

📸 **Screenshot – permission test/error**

> [INSERT SCREENSHOT HERE]

---

## Permission Changes

| File/Directory | Before | After | Why |
|---|---|---|---|
| `script.sh` | [INSERT] | [INSERT] | Make script executable |
| `devops.txt` | [INSERT] | [INSERT] | Remove write permission |
| `notes.txt` | [INSERT] | `640` | Restrict access |
| `project/` | N/A | `755` | Standard directory access |

## Commands Used

- `touch`
- `cat`
- `vim`
- `head`
- `tail`
- `ls -l`
- `chmod`
- `mkdir`

## What I Learned

- [LEARNING 1]
- [LEARNING 2]
- [LEARNING 3]

## Final Verification

- [ ] Files created
- [ ] Files read successfully
- [ ] Permissions understood
- [ ] Permissions changed
- [ ] Permission errors tested
- [ ] Screenshots added
