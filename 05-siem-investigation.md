# 🔎 Mission 5: SIEM investigation

> **Score: 14 / 15** 🟢 · 📍 SOC, analyst desk · 🛠️ Cybrixen SIEM · 🏷️ Security monitoring, Log analysis, Incident detection

## 🎯 The mission
Overnight authentication logs looked wrong. The job was to find **who attacked**, **which account fell**, **when it first happened** and **what kind of attack** it was. After that, the threat had to be contained.

## 🧠 How I approached it
1. 📊 **Zoomed out first.** Event types, hosts, users, source IPs and the timeline histogram showed where the spike was.
2. 🔴 **Filtered to failed logins** and looked for one external source hitting many usernames.
3. 🎯 **Pivoted on the attacking IP** to find any *successful* login from it. That is the moment an attempt becomes a breach.
4. 🕵️ **Checked what the compromised account did next** (file access and remote desktop activity) to understand the impact.
5. 📝 **Recorded the incident ticket** from log evidence only.
6. 🧯 **Contained:** blocked the attacker at the edge firewall and disabled the compromised account.

## ✅ What went right
- Attacking IP ✔️
- Compromised account ✔️
- Time of first successful malicious login ✔️
- Blocked the attacker ✔️
- Disabled the account so the stolen password stops working ✔️

## ❌ The one miss: attack type
I picked the wrong attack type. The correct answer was **credential stuffing**.

| Attack | The log pattern |
|--------|-----------------|
| **Brute force** | Many passwords against **one** account |
| **Password spraying** | **One** (or few) passwords across **many** accounts |
| **Credential stuffing** | A **leaked list** of username and password pairs, **one try each**, many usernames not even valid here, and one works first time |

The clue I underweighted: lots of "unknown user" failures, one attempt per name, and a success on the very first try.

## 📚 Lessons
- Don't classify by volume alone. Look at **how many tries per account** and **how many different accounts**.
- "Unknown user" failures suggest the attacker is using a list from somewhere else.
- Containment has two halves: **block the source** and **kill the compromised credential**.

## 📸 Evidence

<img width="959" height="463" alt="Screenshot 2026-11-16 163318" src="https://github.com/user-attachments/assets/507d1a8f-744d-44fa-b0d3-989b733edd3d" />

---


