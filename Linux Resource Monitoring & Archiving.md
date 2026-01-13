# Linux Resource Monitoring & Archiving

### 1. `df` — Disk Space Usage (Filesystem Level)

**Purpose**

Shows **disk space usage per mounted filesystem**.

**Common usage**

```bash
df
df -h
df -T

```

**Important options**

- `h` → human-readable (MB, GB)
- `T` → filesystem type

**Sample output**

```
Filesystem  Size  Used  Avail  Use%  Mountedon
/dev/sda150G22G26G46%    /

```

---

### 2. `du` — Disk Usage (Directory/File Level)

**Purpose**

Shows **actual space used by files/directories**.

**Common usage**

```bash
du
du -h
du -sh directory/

```

**Important options**

- `s` → summary only
- `h` → human-readable

**Sample output**

```
1.5G   project/

```

---

### 3. `free` — Memory Usage

**Purpose**

Displays **RAM and swap usage**.

**Common usage**

```bash
free
free -h

```

**Sample output**

```
              total   used   freeshared  buff/cache  available
Mem:8G3G1G200M4G4.5G
Swap:2G0G2G

```

---

### 4. `uptime` — System Runtime & Load

**Purpose**

Shows **how long the system has been running** and **load averages**.

**Usage**

```bash
uptime

```

**Sample output**

```
10:42:01 up 3 days,  4users,  load average: 0.42, 0.35, 0.30

```

**Load averages**

- 1 min, 5 min, 15 min CPU demand
- On a single-core system, >1.0 indicates overload

---

### 5. `vmstat` — Virtual Memory & CPU Stats

**Purpose**

Reports **memory, swap, CPU, and I/O statistics**.

**Usage**

```bash
vmstat
vmstat 2

```

**Key columns**

- `si / so` → swap in / out (non-zero = memory pressure)
- `us` → user CPU
- `sy` → system CPU
- `id` → idle CPU

**Sample output (trimmed)**

```
procs --------memory-------- ---cpu---
rb   swpd  free  buff  cache   us sy id
100820M120M3.5G10387

```

---

## B. Archiving & Compression

### 1. `tar` — Archiving (with optional compression)

**Purpose**

Combines multiple files into a **single archive**.

**Common options**

- `c` → create
- `x` → extract
- `t` → list
- `f` → filename
- `v` → verbose
- `z` → gzip
- `j` → bzip2

**Examples**

```bash
tar -cvf archive.tar files/
tar -xvf archive.tar
tar -czvf archive.tar.gz files/
tar -xzvf archive.tar.gz

```

---

### 2. `zip` and `unzip`

**Purpose**

Creates and extracts **ZIP compressed archives** (common cross-platform).

**Create archive**

```bash
zip archive.zip file1 file2
zip -r archive.zip directory/

```

**Extract archive**

```bash
unzip archive.zip

```

**List contents**

```bash
unzip -l archive.zip

```
