# 🔥 Mission 4: Firewall hardening

> **Score: 15 / 15** 🟢 · 📍 Server room · 🛠️ FW-EDGE-01 management console · 🏷️ Network security, Firewall administration

## 🎯 The mission
An audit flagged the edge firewall. The change ticket (an insurer wanted proof that only approved services are exposed) listed what the firewall **should** and **should not** allow. The job was to rework the rules and **commit** them. Only committed rules count.

## 📋 What the ticket asked for
| # | Requirement |
|:-:|-------------|
| 1 | Database reachable **only** from the web server |
| 2 | SSH to the web server **only** from the IT admin subnet |
| 3 | Website over **HTTPS only**, with plain HTTP retired |
| 4 | Mail: SMTP in from the internet, mail submission **only** from the office LAN |
| 5 | **Everything else denied** by default |

## 🧠 How I approached it
1. 🧭 **Understood the engine:** first matching rule wins, so order matters.
2. 🔍 **Audited every existing rule** against the ticket. Sources set to `any`, retired HTTP still open, two mail ports lumped into one rule.
3. ✂️ **Split and tightened:** one rule per purpose, with the narrowest source that still works.
4. 🚫 **Flipped the default policy to deny.** That single change makes "everything else is denied" true.
5. 🧪 **Tested with the packet tracer:** traffic that should pass *and* traffic that should be blocked, for every requirement.
6. 💾 **Committed the configuration.** Uncommitted edits are ignored.

## ✅ Result
All five requirements passed live traffic tests.

## 📚 Lessons
- Default-deny plus explicit allows is much easier to audit than allow-all plus blocks.
- Test the "should be blocked" cases too, because over-permissive rules still pass the happy path.
- Nothing is real until it's committed.

## 📸 Evidence

<img width="959" height="454" alt="Screenshot 2026-11-16 162530" src="https://github.com/user-attachments/assets/f9ec7c17-2854-4519-a316-6058cdac4574" />

