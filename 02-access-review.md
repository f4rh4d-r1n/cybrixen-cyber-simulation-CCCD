# 🔐 Mission 2: Access review

> **Score: 4 / 10** 🔴 · 📍 Open office, HR workstation · 🛠️ Cybrixen Directory · 🏷️ Identity and access management, Account lifecycle

## 🎯 The mission
HR sent a leavers memo. The task was to bring the directory in line with that memo **and** the company access policy. Changing an account that was already correct **cost marks**.

## 📜 The rules I worked from
| Policy | In plain English |
|:------:|------------------|
| AP-1 | Disable leavers on or before their last day |
| AP-2 | Only IT staff in Domain Admins |
| AP-3 | Every Domain Admin must have MFA |
| AP-4 | Service accounts: stay enabled, no MFA, changes via change control |
| AP-5 | VPN Users only for IT, Sales and Executive |

## 🧠 How I approached it
1. Read the memo and policy first.
2. Disabled the leavers named in the memo.
3. Filtered **Domain Admins**, removed non-IT members, and checked MFA.
4. Filtered **VPN Users** and removed anyone outside the allowed departments.
5. Left service accounts alone.

## ❌ Where I lost marks
| What went wrong | Why it cost me |
|-----------------|----------------|
| Disabled a **look-alike name** (one letter different) instead of only the real leaver | A current employee lost access. Names, departments and job titles must all match the memo |
| Added someone to **Domain Admins** with no policy reason | Creating new privilege is the opposite of AP-2 |
| One Domain Admin was left **without MFA** | AP-3 applies to *every* member, so the whole list needs checking, not just the first few |

## ✅ What went right
- Both real leavers were disabled.
- A non-IT Domain Admin was removed.
- A non-eligible VPN user was removed.

## 📚 Lessons
- 🔍 **Verify identity before clicking disable:** compare username, department and title, not just the first name that appears in search.
- 🧾 **Make a checklist from the policy**, tick each item, and stop when it's done. Extra changes are errors.
- 🛡️ Privileged accounts deserve a second look. A missing MFA on an admin is the worst gap in the directory.

## 📸 Evidence
<!-- add: screenshots/02-access-review/memo.png, policy.png, directory.png, feedback.png -->
