# Day 06 – Linux File I/O Practice

## Objective

Practice creating, writing, appending, and reading text files using basic Linux commands.

## 1. Create the File

```bash
touch notes.txt
```

**Purpose:** Creates an empty `notes.txt` file.

## 2. Write the First Line

```bash
echo "Linux file practice - line 1" > notes.txt
```

**Purpose:** `>` creates/overwrites the file.

## 3. Append Another Line

```bash
echo "Linux file practice - line 2" >> notes.txt
```

**Purpose:** `>>` appends without overwriting existing content.

## 4. Use tee

```bash
echo "Linux file practice - line 3" | tee -a notes.txt
```

**Purpose:** `tee -a` displays the text and appends it to the file.

📸 **Screenshot placeholder – file creation and writing**

> [INSERT SCREENSHOT HERE]

## 5. Read the Complete File

```bash
cat notes.txt
```

## 6. Read the First Two Lines

```bash
head -n 2 notes.txt
```

## 7. Read the Last Two Lines

```bash
tail -n 2 notes.txt
```

📸 **Screenshot placeholder – reading the file**

> [INSERT SCREENSHOT HERE]

## My `notes.txt`

The file should contain approximately 8–12 lines after completing the practice.

> [OPTIONALLY PASTE YOUR ACTUAL notes.txt CONTENT HERE]

## What I Learned

- `>` writes or overwrites a file.
- `>>` appends to an existing file.
- `cat` displays the complete file.
- `head` and `tail` display selected parts.
- `tee` can display and write data at the same time.
