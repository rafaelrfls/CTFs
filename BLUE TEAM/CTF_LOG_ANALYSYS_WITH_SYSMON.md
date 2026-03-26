# Capture The Flag
## Log Analysis with Sysmon- LetsDefend

**Post LinkedIn:**


<img width="400" height="300" alt="GetImage" src="https://github.com/user-attachments/assets/3e778ebf-fede-4748-9336-e8e4b5dd42e4" />

---

**Our company has experienced a breach on one of its endpoints. Your task is to investigate the breach thoroughly by analyzing the Sysmon logs of the compromised endpoint to gather all necessary information regarding the attack.**

🔹Which file gave access to the attacker? 

R: IDM.exe

---

🔹What did the attacker use to bypass UAC? Mention the EXE. 

R: fodhelper.exe 

---

🔹What registry path and value was used by the above EXE to gain higher privileges? (path\value) 

R: HKCU:\Software\Classes\ms-settings\shell\open\command\sEpQhpkr 

---

🔹The attacker dropped a file. What is the file location? 

R: C:\Users\Gabr\Downloads\mimikatz.exe 

---

🔹What are the technique name and ID used by the dropped EXE? 

R: Credential Dumping: T1003 

---

🔹What is the name of the attack? 

R: pass the hash 

---

🔹What EXE did the attacker run using elevated privileges from the above attack? 

R: powershell.exe 

---

🔹The attacker downloaded and ran a file. What is the filename? 

R: 012e382049b88808e2d0b26e016dc189f608deea9b6cc993ce24a57c99dd93d1.exe 
