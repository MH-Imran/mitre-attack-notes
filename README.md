# MITRE ATT&CK Notes

These are my personal notes as I study different attacker techniques from the MITRE ATT&CK framework.  
I’m keeping things simple and focusing on what each technique means and how to think about detecting it.

---

## Why I'm Studying MITRE
Learning attacker behavior helps me understand:
- what logs to look for  
- which alerts matter  
- how attackers move through systems  
- how defenders can catch them  

I’ll add more notes here as I learn new techniques and practice detections in my home lab.

---

## Techniques I'm Starting With
### **T1059 – Command and Scripting Interpreter**
Attackers often use command-line tools (like cmd, PowerShell, Bash) to run payloads or move around.  
**What I'm learning:** unusual commands, base64 encoding, scripts running from odd locations.

### **T1078 – Valid Accounts**
Using stolen or weak credentials to log in normally.  
**What I'm learning:** how failed logins, new locations, or unusual login times appear in logs.

### **T1027 – Obfuscated Files or Information**
Trying to hide malicious content using encoding or packing.  
**What I'm learning:** spotting strange file names, encoded strings, or sudden script changes.

---

## More to come
I’ll keep updating these notes as I go deeper into the framework.

This is mainly for my own learning, but I hope it becomes a useful reference over time.
