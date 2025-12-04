# T1078 – Valid Accounts

These are my personal notes on the MITRE technique where attackers use real, valid credentials to access systems.

---

## What This Technique Means (My Understanding)
Instead of breaking in through exploits, attackers sometimes just log in normally using:
- stolen usernames/passwords
- weak or default credentials
- old accounts that were never disabled

Because the login looks “normal,” it can be harder to catch.

---

## How Attackers Usually Abuse Valid Accounts
From what I'm learning so far:

- They log in during unusual hours  
- They access systems the user never touches  
- They come from new or unexpected locations  
- They perform admin actions that aren’t normal  
- They try multiple passwords until one works  
- Once inside, they blend in by using legitimate tools  

This is why monitoring behavior is very important.

---

## What Shows Up in Logs
**Windows Event Logs**
- Successful login events  
- Failed login attempts  
- Logins from new IPs  
- Use of high-privileged accounts  

**Linux**
- `/var/log/auth.log`  
- SSH connections  
- Sudden sudo usage  

---

## Things I'm Learning to Spot
I’m trying to understand these patterns:

- A user logging in at a time they never do  
- Logins from a country the user has never visited  
- A normal user suddenly trying admin commands  
- Multiple failed logins followed by a success  
- Access to servers that the user doesn’t normally work on  

These are the types of things SOC analysts review during triage.

---

## Simple Detection Thoughts I'm Practicing
- Alert when an account logs in from a new location  
- Track login times against the user’s normal pattern  
- Flag logins followed by unusual commands  
- Watch for many failed attempts before a success  
- Monitor admin accounts very closely  

---

## Notes
This technique is one of the most common in real incidents, so I’ll keep adding to this as I learn more.
