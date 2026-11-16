<div align="center">

<!-- TODO: add your CUX logo at assets/cux-logo.png -->

# 🛡️ Cybrixen Certified Cyber Defender [CCCD]
### 8 missions · 1 office · 1 very busy security analyst

![Score](https://img.shields.io/badge/final%20score-83.8%20%2F%20100-7c3aed?style=for-the-badge)
![Missions](https://img.shields.io/badge/missions-8%20of%208%20done-22c55e?style=for-the-badge)
![From](https://img.shields.io/badge/from-Cybrixen-0ea5e9?style=for-the-badge)

</div>

---

## 👋 What is this?

Welcome to my proof-of-work. 🎉

**Cybrixen** drops you into a simulated office and gives you a day's worth of real security and IT problems: catch phishing, fix a leaky firewall, hunt an attacker in the logs, kill a cryptominer and survive a ransomware attack on the CEO's laptop.

I completed all **8 missions**. This repo is the evidence. Every mission has a write-up covering what the task was, how I tackled it, what I scored, **where I lost marks**, and what I learned from it.

> 💡 **Why show the mistakes?** Because that is where the learning is. A portfolio with only perfect scores teaches nobody anything.

---

## 🏆 Scorecard

| # | Mission | Score | Progress | Verdict |
|:-:|---------|:-----:|----------|:-------:|
| 1 | [📧 Phishing triage](01-phishing-triage.md) | **10 / 10** | `██████████` | 🟢 Perfect |
| 2 | [🔐 Access review](missions/02-access-review.md) | **4 / 10** | `████░░░░░░` | 🔴 Biggest lesson |
| 3 | [🧹 Clean-desk walk](missions/03-clean-desk-walk.md) | **5.8 / 10** | `██████░░░░` | 🟡 Over-eager |
| 4 | [🔥 Firewall hardening](missions/04-firewall-hardening.md) | **15 / 15** | `██████████` | 🟢 Perfect |
| 5 | [🔎 SIEM investigation](missions/05-siem-investigation.md) | **14 / 15** | `█████████░` | 🟢 One slip |
| 6 | [🐧 Endpoint forensics](missions/06-endpoint-forensics.md) | **15 / 15** | `██████████` | 🟢 Perfect |
| 7 | [🧨 Ransomware response](missions/07-ransomware-response.md) | **10 / 15** | `██████░░░░` | 🟡 Learned the hard way |
| 8 | [🎣 Executive phishing](missions/08-executive-phishing.md) | **10 / 10** | `██████████` | 🟢 Perfect |
| | **Total** | **83.8 / 100** | `████████░░` | |

**Strongest areas:** Phishing triage · Firewall hardening · SIEM investigation · Endpoint forensics · Executive phishing
**Work-on-next areas:** Access review · Clean-desk walk · Ransomware response

---

## 🧰 Skills I practised

| Area | What it looked like in the simulation |
|------|----------------------------------------|
| 📧 **Email security and social engineering** | Spotting phishing vs genuine emails in two different inboxes |
| 🔐 **Identity and access management** | Leavers, Domain Admins, MFA, VPN groups, service accounts |
| 🏢 **Physical security** | Clean-desk checks, USB baiting, propped-open doors |
| 🔥 **Network security** | Default-deny firewall rules, rule order, packet testing |
| 📊 **Security monitoring** | Reading SIEM logs, finding the attacker, containing the breach |
| 🐧 **Linux administration** | Finding malware and its persistence, hash checks, file permissions |
| 🚨 **Incident response** | Containment, order of operations, choosing a clean backup |

---

## 🎓 Organization and certificate

| | |
|---|---|
| **Programme** | Cybrixen Certified Cyber Defender |
| **Provider /** | [cybrixen.com](https://cybrixen.com) |


<!-- TODO: add certificate at assets/certificate.png, then uncomment
<div align="center">
  <img src="assets/certificate.png" alt="Cybrixen certificate" width="650"/>
</div>
-->

---

## 📈 What I'd do differently (the honest bit)

1. **Slow down on look-alike names.** In the access review, two people had nearly the same name. Checking name, department and title before clicking would have saved marks.
2. **Don't touch what you weren't asked to touch.** Extra "helpful" changes (a group membership, shredding sticky notes) cost points in missions 2 and 3.
3. **In an active incident, isolate, don't power off.** Memory can hold the encryption key and evidence.
4. **Know the attack types cold.** Credential stuffing, password spraying and brute force look similar in logs but are different.

---

## 🗂️ Repo structure

```
.
├── README.md
├── assets/                  # CUX logo, certificate
├── missions/                # one write-up per mission (01 to 08)
└── screenshots/             # evidence, one folder per mission
    ├── 01-phishing-triage/
    ├── 02-access-review/
    ├── 03-clean-desk-walk/
    ├── 04-firewall-hardening/
    ├── 05-siem-investigation/
    ├── 06-endpoint-forensics/
    ├── 07-ransomware-response/
    ├── 08-executive-phishing/
    └── results/             # final score and feedback pages
```

## 👤 Author

**<!-- TODO: your name -->**  Farhad Khan<!-- TODO: username -->

---
