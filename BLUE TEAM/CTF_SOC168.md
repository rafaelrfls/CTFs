# Capture The Flag
## SOC168 — Whoami Command Detected - LetsDefend

**Post LinkedIn:** <a href="" rel="noopener noreferrer"> Link</a>

<img width="500" height="500" alt="capa" src="https://github.com/user-attachments/assets/87047b8e-a8d7-47f2-83cc-d83fb88a224f" />


---

**Alerta gerado:**

<img width="1100" height="489" alt="Alert" src="https://github.com/user-attachments/assets/db55657e-2ac6-4c17-b661-7a293bea99ed" />

Informações que tenho:

🔹Event Time: Feb, 28, 2022. 4:12 a.m

🔹Hostname: WebServer1004

🔹Dest. ip: 172.16.17.16

🔹Src ip: 61.177.172.87

🔹HTTP Request Method: POST

Com essas informações verifico o Log Management e filtro pelo Destination Adress para ver os comandos que foram executados.

Comando que gerou o alerta: whoami

<img width="239" height="161" alt="command 1" src="https://github.com/user-attachments/assets/84f36f81-0e4c-4ec7-9486-a3ea5d7beebe" />
<img width="341" height="160" alt="command 1 1" src="https://github.com/user-attachments/assets/86f27239-8ab3-4312-962b-04aa8cf5c76d" />

---

Source IP deu como malicioso no VirusTotal:

<img width="875" height="209" alt="virustotal" src="https://github.com/user-attachments/assets/62384331-3cac-4236-8ad3-f95699cdaed2" />
