# 🐧 Mission 6: Endpoint forensics

> **Score: 15 / 15** 🟢 · 📍 Open office, IT desk · 🛠️ Terminal on a Linux server · 🏷️ Linux administration, Host investigation

## 🎯 The mission
A Linux server was pegged at **100% CPU** and the payroll app was crawling. The IT ticket had three parts:

1. Stop what is eating the CPU **and** make sure it can't come back
2. Check vendor installers against a hash list and record any that fail
3. Fix the permissions on a flagged SSH private key

⚠️ The server also ran real services, and stopping legitimate ones or deleting system files cost marks.

## 🧠 How I approached it

### 🕵️ Part 1: The CPU hog (a cryptominer)
- `ps aux` showed one process using almost all the CPU. It ran from a **hidden folder in `/tmp`**, wore a **system-sounding name**, ran as the **web server user** and was talking to an external **mining-pool style** address and port.
- **Hunted for persistence.** `crontab -l` for my own user was empty, but `sudo crontab -u www-data -l` revealed a job that relaunched the miner every few minutes. Killing the process alone would not have worked.
- Removed the cron entry, deleted the binary, killed the process, then re-checked with `ps aux | grep`. CPU dropped to ~0%.
- 🪤 **Gotcha:** I once chained commands on one line without `&&` or `;`, so `sudo` treated the later commands as arguments and nothing ran. Chaining properly fixed it.

### 🔢 Part 2: Hash check
- Ran `sha256sum` on every file in the downloads folder and compared each against the vendor hash list **by filename**, not by position. One installer's hash didn't match, which means it was tampered with.
- Recorded it in the Findings panel.

### 🔑 Part 3: SSH key permissions
- A private key should be readable and writable by **its owner only**: `chmod 600`, then `ls -la` to confirm group and others have nothing.

## ✅ Result
| Check | Result |
|-------|:------:|
| Persistence (cron job) removed | ✔️ |
| Miner binary deleted | ✔️ |
| Miner no longer running | ✔️ |
| Key restricted to owner only | ✔️ |
| Tampered installer identified | ✔️ |

## 📚 Lessons
- 🔁 **Always hunt persistence** (cron, systemd, startup scripts) when you remove malware.
- `sudo` applies to **one command**, so chain deliberately.
- Match hashes by filename. The two lists were not in the same order.
- Leave legitimate services (nginx, postgres) alone, because precision is part of the job.

## 📸 Evidence
<!-- add: screenshots/06-endpoint-forensics/ticket.png, ps-aux.png, crontab.png, hash-check.png, chmod.png, feedback.png -->
