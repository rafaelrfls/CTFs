# Capture The Flag
## Log Analysis with Sysmon- LetsDefend

**Post LinkedIn:** <a href="https://www.linkedin.com/feed/update/urn:li:activity:7444063651793350656/" rel="noopener noreferrer"> Link</a>



<img width="400" height="300" alt="GetImage" src="https://github.com/user-attachments/assets/3e778ebf-fede-4748-9336-e8e4b5dd42e4" />

---

**Our company has experienced a breach on one of its endpoints. Your task is to investigate the breach thoroughly by analyzing the Sysmon logs of the compromised endpoint to gather all necessary information regarding the attack.**

🔹Which file gave access to the attacker?

No Event Viewer, filtrando pelo EventID: 01 - Process Creation, encontro um executável: IDM.exe

<img width="500" height="587" alt="IDM" src="https://github.com/user-attachments/assets/12057d57-d988-4c95-b7c1-828a4ee09824" />

Na sequencia vejo que gera um comando cmd.exe

<img width="500" height="669" alt="CMD" src="https://github.com/user-attachments/assets/153928ae-25b9-42d8-bbe3-9d473fdb7f38" />

R: IDM.exe

---

🔹What did the attacker use to bypass UAC? Mention the EXE. 

Na imagem anterior é possível ver que é executado o fodhelper.exe, que encontro a técnica T1548.002 no Mitre ATT&CK. Usa o fodhelper.exe para bypass de UAC.

<img width="1235" height="170" alt="mitre" src="https://github.com/user-attachments/assets/ba3d4dc5-c62c-4740-89c4-d05fce826fae" />

R: fodhelper.exe 

---

🔹What registry path and value was used by the above EXE to gain higher privileges? (path\value)

processId do fodhelper: 5976

<img width="500" height="567" alt="paretporcessid" src="https://github.com/user-attachments/assets/352f4bfb-99c2-4b6d-ba6e-749e08afd055" />

Analisando a técnica, vejo que deve executar o seguinte comando:

<img width="500" height="580" alt="bypass UAC" src="https://github.com/user-attachments/assets/7a994f49-cb31-45de-b33b-b3fac8198f0b" />

Na sequencia o comando sendo executado e o parentprocessid: 5976 bate com o registro anterior:

<img width="500" height="641" alt="hkcu paretprocessid" src="https://github.com/user-attachments/assets/5dc5a0b0-8e9c-4829-b01f-230d35f2f962" />

R: HKCU:\Software\Classes\ms-settings\shell\open\command\sEpQhpkr

---

🔹The attacker dropped a file. What is the file location? 

Filtrando pelo EventID: 11 File create, encontro o arquivo mimikatz.exe. Descrição Mitre: Mimikatz is a credential dumper capable of obtaining plaintext Windows account logins and passwords, along with many other features that make it useful for testing the security of networks.

<img width="679" height="567" alt="mimikatz" src="https://github.com/user-attachments/assets/ecdcd567-ed2f-4834-aae3-55a601260898" />


R: C:\Users\Gabr\Downloads\mimikatz.exe 

---

🔹What are the technique name and ID used by the dropped EXE? 

<img width="1389" height="481" alt="T1003 credential dumping" src="https://github.com/user-attachments/assets/ef7aed9e-5321-4290-965d-345828f63bf7" />

R: Credential Dumping: T1003 

---

🔹What is the name of the attack? 

Usado para elevar privilégios ou Lateral Movement.

R: pass the hash 

---

🔹What EXE did the attacker run using elevated privileges from the above attack? 

É possivel ver que o processo 4988 rodou o mimikatz, depois no processo 2176 abre um powershell com privilégios elevados:

<img width="500" height="652" alt="elevated privileges" src="https://github.com/user-attachments/assets/5174c452-0e8a-42ac-a66d-2896fd780b58" />

R: powershell.exe 

---

🔹The attacker downloaded and ran a file. What is the filename? 

Filtrando pelo eventid 11 file create encontro o processo de download do arquivo, ligado ao processo anterior 2176 de execução do powershell

<img width="500" height="612" alt="file" src="https://github.com/user-attachments/assets/9bea493b-dea6-419d-900a-ad291ee88675" />

R: 012e382049b88808e2d0b26e016dc189f608deea9b6cc993ce24a57c99dd93d1.exe 
