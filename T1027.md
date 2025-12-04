# T1027 – Obfuscated Files or Information

These are my notes on the MITRE technique where attackers hide or disguise their files, scripts, or commands to avoid being detected.

---

## What This Technique Means (In My Own Words)
Attackers don’t always run their tools or scripts in a clean, readable way.  
They often try to hide what something really is by:

- encoding it  
- compressing it  
- renaming it  
- splitting it into pieces  
- packing it inside another file  

The idea is simple: make the malicious content harder to spot.

---

## What I’m Learning to Watch For
Some patterns that stand out as I study this:

- PowerShell commands full of long base64 strings  
- Scripts downloaded from the internet and renamed to look harmless  
- Files with strange extensions (like `.jpg` that behave like `.exe`)  
- Packed or compressed payloads that expand during execution  
- Suspicious ZIP/RAR files containing scripts  

Again, these aren’t always malicious, but they are worth reviewing.

---

## Examples From Real Cases (Very Common)
- A malicious PowerShell script encoded in base64  
- A payload hidden inside a ZIP file  
- Malware disguised as a PDF or image  
- Obfuscated JavaScript in phishing pages  
- Encoded commands passed through CLI tools  

These are things SOC teams run into a lot.

---

## Where This Appears in Logs
Depending on what is being executed:

**Windows Logs**
- Script Block Logging  
- Events showing encoded commands  
- Tools like `powershell.exe`, `cscript.exe`, `wscript.exe`

**Linux Logs**
- Executable files in unusual locations  
- Compressed files being extracted right before execution  

---

## Detection Thoughts I’m Trying to Build
- Flag encoded PowerShell commands  
- Look for `.exe` files with misleading extensions  
- Watch for scripts running from temp folders  
- Alert on compressed files immediately followed by execution  
- Spot files with extremely long or random names  

These small things can give early warning signs.

---

## Notes
I’m still new to this technique, but I’ll keep adding examples and detection ideas as I practice more in my home lab.
