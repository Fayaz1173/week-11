# Essential linux commands

# a) Commonly used Linux commands (short reference)

(Shown: command — short description)

- `ls` — list directory contents
- `pwd` — print working directory
- `cd [dir]` — change directory
- `cp` — copy files/directories (`cp -r` for dirs)
- `mv` — move/rename files/directories
- `rm` — remove files/directories (`r` recursive, `f` force)
- `touch` — create empty file or update timestamp
- `cat` — print file to stdout
- `less` / `more` — view file interactively
- `head` / `tail` — view start/end of files (`tail -f` for live)
- `grep` — search text using regex/strings (`R` recursive)
- `find` — find files by name/type/time/perm etc.
- `chmod` — change file permissions (numeric or symbolic)
- `chown` — change file owner and group
- `ps` — list processes (e.g., `ps aux`)
- `top` / `htop` — interactive process monitor (`htop` optional)
- `kill` / `killall` — send signals to process (SIGTERM, SIGKILL)
- `tar` — archive / compress (`tar -czvf` create gzip tarball)
- `gzip` / `gunzip` — compress/uncompress single files
- `zip` / `unzip` — zip archives
- `scp` — secure copy over SSH
- `ssh` — remote shell
- `ln` — create hard/symbolic links (`ln -s`)
- `wc` — word/line/byte count (`wc -l` lines)
- `sort` / `uniq` — sort and deduplicate lines
- `awk` / `sed` — stream text processing (power tools)
- `df` — disk free (filesystem usage)
- `du` — disk usage (per-file/dir)
- `chmod` / `chown` — change mode and ownership
- `stat` — detailed file metadata
- `file` — detect file type
- `mount` / `umount` — attach/detach filesystems
- `echo` — print text / useful in scripts
- `xargs` — build/execute commands from stdin
- `tee` — duplicate output to file and stdout

Bonus safe-delete helpers:

- `trash-cli` (package) — move files to trash instead of `rm`
