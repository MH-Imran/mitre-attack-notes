# T1059 – Command and Scripting Interpreter

These are my personal notes on T1059 as I study attacker behaviors related to command-line and scripting tools.

---

## What This Technique Means (In My Words)
Attackers often rely on the command line or scripting tools (like PowerShell, Bash, cmd.exe) to run commands, download files, move around the system, or execute payloads.  
It's simple, flexible, and built into the OS, which makes it harder to detect without good logging.

---

## What I'm Trying to Understand
- What normal command-line usage looks like  
- What unusual or suspicious commands look like  
- How attackers hide commands (base64, encoded scripts, etc.)  
- How logs are generated when these tools run  

---

## Examples of Suspicious Behavior
Things I’m learning to watch for:

- PowerShell commands with long base64 strings  
- Scripts running from temporary folders  
- Unexpected usage of tools like `curl`, `wget`, or `bitsadmin`  
- Command shells spawning other unusual processes  
- Bash scripts downloaded from the internet and executed immediately  

These aren’t always attacks, but they are worth investigating.

---

## Where This Shows Up in Logs
Depending on the system:

**Windows**  
- Event ID 4688 (process creation)  
- PowerShell logs (module, script block logging)

**Linux**  
- `.bash_history`  
- Syslog  
- Auditd logs (if enabled)

---

## Detection Ideas I'm Practicing
Here are some simple detection thoughts I’m trying to build:

- Look for encoded PowerShell commands  
- Flag scripts running from odd directories  
- Alert on command-line tools executing network connections  
- Watch for repeated failed commands or unusual parameters  

I’ll expand these as I gain more hands-on experience.

---

## Notes
I plan to add more MITRE techniques as I learn them.  
This is mainly a study log for myself, but it’s helping me understand how attackers operate.
