# 🧨 Mission 7: Ransomware response

> **Score: 10 / 15** 🟡 · 📍 CEO office + SOC · 🛠️ The CEO's laptop and the incident response console · 🏷️ Incident response, Business continuity

## 🎯 The mission
The CEO's laptop showed a ransom note. Three things to deliver:
1. 🔌 **Contain** the laptop
2. 📋 Put the **response plan in the right order**
3. 💾 **Choose the backup** to restore from

## 🔎 What the EDR alerts told me
Three alerts told a single story:

`Cracked installer ran a hidden program` → `Second-stage download` → `Connection to a brand-new domain` → `Mass file encryption + shadow copies deleted + ransom note`

## ✅ What went right
- Unplugged the laptop from the wired network
- **Chose the right backup:** the latest *successful* snapshot taken **before** the encryption began. Snapshots after it showed an unusually high number of changed files (encrypted copies), and one earlier snapshot had warnings.

## ❌ Where I lost marks
| Mistake | What should have happened |
|---------|---------------------------|
| **Left Wi-Fi on** | Isolate from **every** network path, wired **and** wireless, or it can still spread or phone home |
| **Shut the laptop down** | Powering off wipes **memory**, which can hold the encryption key and live evidence. **Isolate it and leave it running** |
| **One response step out of order** (5 of 6 correct) | See the order below |

## 🧭 The order to remember
| Step | Phase | Why |
|:----:|-------|-----|
| 1 | 🔌 **Contain** | Stop the spread first |
| 2 | 📣 **Escalate** | Tell the incident lead and senior management early |
| 3 | 🧊 **Preserve** | Capture memory and logs **before** changing anything |
| 4 | 🔬 **Investigate** | Find the entry point, check other systems |
| 5 | 🛠️ **Recover** | Wipe and restore from a clean backup |
| 6 | 📚 **Review** | Reset credentials, lessons-learned meeting |

## 📚 Lessons
- ⚡ **Isolate, don't power off.** My instinct was "turn it off", and that destroyed evidence.
- Containment means *all* network paths.
- **Preserve before you wipe.** Evidence is how you find the way in.
- Backup metadata (changed-file counts) can reveal when the encryption actually started.

## 📸 Evidence
<!-- add: screenshots/07-ransomware-response/edr-alerts.png, response-plan.png, backups.png, feedback.png -->
