# Linux Process Management

### A. Monitoring Processes (`ps`, `top`, `htop`)

### 1. `ps` — Snapshot of Processes

**Purpose**

`ps` shows a **static snapshot** of processes at the time the command runs.

**Commonly used forms**

```bash
ps# processes in current shell
ps -e# all processes
ps -ef# full-format listing (SysV style)
ps aux# full listing (BSD style)

```

**Key columns (from `ps -ef`)**

- `PID` → Process ID
- `PPID` → Parent Process ID
- `USER` → Owner
- `STAT` → Process state (R, S, Z, etc.)
- `CMD` → Command started

---

### 2. `top` — Live Process Monitor

**Purpose**

`top` provides a **real-time, continuously updating** view of system activity.

**What it shows**

- CPU and memory usage
- Load average
- Running processes sorted by CPU (default)

**Useful keys inside `top`**

- `P` → sort by CPU
- `M` → sort by memory
- `k` → kill a process (asks for PID)
- `q` → quit

**Limitations**

- Interface is functional but not user-friendly.

---

### 3. `htop` — Enhanced Interactive Monitor

**Purpose**

`htop` is an improved alternative to `top` (not installed by default everywhere).

**Advantages**

- Color-coded display
- Mouse support
- Easier process killing and sorting
- Tree view of parent/child processes

**Start**

```bash
htop

```

---

### B. Killing Processes with `kill`

**Purpose**

`kill` sends a **signal** to a process (does not always mean “force kill”).

**Basic syntax**

```bash
kill PID

```

(Default signal: `SIGTERM` – graceful termination)

**Common signals**

- `SIGTERM (15)` → request clean shutdown (preferred)
- `SIGKILL (9)` → force kill (cannot be ignored)
- `SIGHUP (1)` → reload configuration (daemon-dependent)

**Examples**

```bash
kill 1234# graceful stop
kill -9 1234# force kill
kill -SIGTERM 1234# explicit signal

```

---

### C. Job Control: Background & Foreground Processes

Job control applies **only to processes started from the current shell**.

---

### 1. Background Processes (`&`, `bg`)

**Start in background**

```bash
command &

```

**Move stopped job to background**

```bash
bg %job_number

```

---

### 2. Foreground Processes (`fg`)

**Bring background job to foreground**

```bash
fg %job_number

```

---

### 3. Managing Jobs

**List jobs**

```bash
jobs

```

Example output:

```
[1]+  Running   sleep100 &
[2]-  Stopped   nanofile.txt

```

**Suspend running process**

- Press `Ctrl + Z`

**Kill a job**

```bash
kill %1

```

###
