# Linux File Permissions & Ownership

### A. `chmod` — Change File Permissions

**Purpose**

`chmod` (change mode) controls **who can read, write, or execute** a file or directory.

**Permission types**

- `r` (read) → view file contents / list directory
- `w` (write) → modify file / create-delete files in directory
- `x` (execute) → run file as program / enter directory

**Permission targets**

- `u` → owner (user)
- `g` → group
- `o` → others
- `a` → all (u+g+o)

**View permissions**

```bash
ls -l file.txt

```

Example output:

```
-rwxr-xr--

```

Interpretation:

- `u`: rwx
- `g`: r-x
- `o`: r--

⚠️ **Note**: For directories, `x` means *access/enter*, not execute.

### B. Symbolic vs Numeric Modes

### 1. Symbolic Mode (Human-readable)

**Syntax**

```bash
chmod [who][+/-/=][permission] file

```

**Examples**

```bash
chmod u+x script.sh# add execute to owner
chmod g-w file.txt# remove write from group
chmod o=r file.txt# set others to read-only
chmod a+rxdir/# add read & execute to all

```

**Strength**

- Clear intent
- Safer for incremental changes

**Weakness**

- Verbose for full permission resets

---

### 2. Numeric (Octal) Mode (Compact & Precise)

**Permission values**

- `r = 4`
- `w = 2`
- `x = 1`

Add them per category:

- `7 = rwx`
- `6 = rw-`
- `5 = r-x`
- `4 = r--`

**Format**

```bash
chmod XYZ file

```

- `X` → owner
- `Y` → group
- `Z` → others

**Examples**

```bash
chmod 755 script.sh# rwx r-x r-x
chmod 644 file.txt# rw- r-- r--
chmod 700 secret.sh# rwx --- ---

```

### C. `chown` — Change File Ownership

**Purpose**

`chown` changes the **owner** and/or **group** of a file or directory.

**Syntax**

```bash
chown user file
chown user:group file
chown :group file

```

**Examples**

```bash
chown alice file.txt# change owner
chown alice:dev file.txt# change owner and group
chown :dev file.txt# change group only

```

**Recursive ownership**

```bash
chown -R alice:dev project/

```
