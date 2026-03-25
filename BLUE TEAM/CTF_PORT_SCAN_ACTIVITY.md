## Port Scan Activity - LetsDefend

---

**Can you determine evidences of port scan activity?**


🔹What is the IP address scanning the environment?

R: 10.42.42.253

<img width="803" height="356" alt="IP scanning" src="https://github.com/user-attachments/assets/3f3a3cb5-44ac-4a54-bcad-97d32d718d96" />

---

🔹What is the IP address found as a result of the scan?

Filtrando o IP origem e flag ACK, aparece apenas um IP que estabeleceu conexão:

R: 10.42.42.50

<img width="812" height="70" alt="ack flag" src="https://github.com/user-attachments/assets/0de958b0-b21a-4987-9396-bea94e1f9780" />

---

🔹What is the MAC address of the Apple system it finds?

Analiso os pacotes que o atacante tentou conexão e encontro um com sistema Apple:

R: 00:16:cb:92:6e:dc

<img width="800" height="229" alt="Apple" src="https://github.com/user-attachments/assets/16fba05b-f64d-40a8-8ed8-7dfe9e2b57b6" />

---

🔹What is the IP address of the detected Windows system?

Mesmo IP que estabeleceu conexão:

R: 10.42.42.50

<img width="537" height="304" alt="windows" src="https://github.com/user-attachments/assets/fcf17154-c799-4f95-a496-cec8d7dda781" />
