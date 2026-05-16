# Overthewire Bandit Learning Notes

## 15-5-2026
### Level 1
- **Concept**: Read a file named `-` using relative paths (`./-`) or the double-dash (`--`) separator to prevent Linux from misinterpreting the filename as a command argument.

### Level 4
- **Concept**: Use `file ./*` to inspect the file type/magic bytes of every file in the directory.

### Level 5 
- **Concept**: Use `find` with `-type`, `-size`, and `! -executable` to filter targets.
- **Note**: `c` stands for bytes (e.g., `1033c` = 1033 bytes).
- **Flag Command**: `find . -type f -size 1033c ! -executable`

### Level 6 
- **Concept**: Filter by file owners using `-user` and `-group`.
- **Note**: `/` (Root directory) != `.` (Current directory).
- **Flag Command**: `find / -user bandit7 -group bandit6 -size 33c`

### Level 7
- **Concept**: Use `grep` to extract specific keywords from text streams.
- **Flag Command**: `cat data.txt | grep "millionth"`

---

## 16-5-2026
### Level 8
- **Concept**: Combine `sort` and `uniq -u` to find unique data.
- **Note**: `uniq` only checks adjacent lines, so data MUST be sorted first. `-u` filters for rows that appear exactly once.
- **Flag Command**: `cat data.txt | sort | uniq -u`

### Level 9
- **Concept**: Use `strings` to extract printable text from binary files, ignoring corrupted data.
- **Flag Command**: `strings data.txt | grep "="`

### Level 12
- **Concept**: Use `xxd -r` to reverse a text-based hexdump back into a raw binary file.
- **Flag Command**: `xxd -r data.txt new_binary`

### Level 13
- **Concept**: SSH Key-based authentication and secure file transfer.
- **`scp`**: Securely copy files between local machine and remote server over SSH.
- **`chmod`**: Modify file permissions. e.g., `chmod 600 sshkey.private` restricts access to the Owner only (Read/Write), which is mandatory for SSH private keys.
