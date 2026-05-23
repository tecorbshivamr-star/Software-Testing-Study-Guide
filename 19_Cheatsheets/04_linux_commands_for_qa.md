# Linux Commands for QA

Quick reference for the most common Linux terminal commands used by QA engineers for parsing logs, managing files, and checking network statuses.

---

## 1. Viewing & Parsing Logs

| Command | Description | Example |
|---|---|---|
| `cat` | Output entire contents of a file to terminal. | `cat error.log` |
| `tail` | Output the last 10 lines of a file. | `tail error.log` |
| `tail -f` | **(Crucial)** Follow the file in real-time. Extremely useful for watching live application logs while you click through the UI. | `tail -f server.log` |
| `head` | Output the first 10 lines of a file. | `head data.csv` |
| `less` | View file contents one screen at a time (use arrows to scroll, `q` to quit). | `less huge_log.txt` |
| `grep` | **(Crucial)** Search for a specific word/pattern inside a file. | `grep "Exception" server.log` |
| `grep -i` | Search ignoring case sensitivity. | `grep -i "error" log.txt` |
| `grep -r` | Search recursively through all files in a directory. | `grep -r "NullPointer" /var/logs/` |

---

## 2. File & Directory Management

| Command | Description | Example |
|---|---|---|
| `ls` | List files in current directory. | `ls` |
| `ls -la` | List files with detailed info (permissions, owner, size, hidden files). | `ls -la` |
| `pwd` | Print Working Directory (shows your current path). | `pwd` |
| `cd` | Change directory. | `cd /var/www/html` |
| `cd ..` | Move up one directory level. | `cd ..` |
| `cp` | Copy a file. | `cp test.py test_backup.py` |
| `mv` | Move or rename a file. | `mv old_name.txt new_name.txt` |
| `rm` | Remove (delete) a file. | `rm junk.txt` |
| `rm -rf` | Force remove a directory and all its contents (Use with extreme caution!). | `rm -rf /old_tests/` |
| `mkdir` | Make a new directory. | `mkdir reports` |

---

## 3. Network & API Commands

| Command | Description | Example |
|---|---|---|
| `ping` | Check if a server is reachable and measure latency. | `ping google.com` |
| `curl` | **(Crucial)** Transfer data from or to a server. Great for hitting APIs from the terminal. | `curl https://api.example.com` |
| `curl -I` | Fetch only the HTTP headers. | `curl -I https://example.com` |
| `curl -X POST`| Send a POST request with data. | `curl -X POST -d "user=1" http://api.com` |
| `netstat -tuln`| List all listening ports (useful to check if your test server is running). | `netstat -tuln` |

---

## 4. System & Process Monitoring

| Command | Description | Example |
|---|---|---|
| `top` | View live system processes, CPU, and RAM usage (like Task Manager). | `top` |
| `htop` | A more user-friendly, colorful version of `top` (might need installation). | `htop` |
| `ps aux` | List all currently running processes. | `ps aux` |
| `kill -9` | Force kill a process by its Process ID (PID). | `kill -9 1234` |
| `df -h` | View free disk space in human-readable format (GB/MB). | `df -h` |
| `free -m` | View free and used RAM in Megabytes. | `free -m` |

---

## 5. Chaining Commands (Pipes)

You can chain commands together using the pipe `|` operator, passing the output of the first command as the input to the second.

**Find out how many times "Error" appears in a log file:**
```bash
grep "Error" server.log | wc -l
```
*(Explanation: `grep` finds all the lines with "Error", and passes them to `wc -l` which counts the lines.)*
