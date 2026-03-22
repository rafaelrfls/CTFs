# Capture The Flag
## PCAP ANALYSIS - TryHackMe

**Post LinkedIn:** <a href="https://www.linkedin.com/posts/rafael-salvalagio-ghensev-49671285_acabei-de-concluir-o-desafio-pcapanalysis-activity-7403440864611598336-_biE?utm_source=share&utm_medium=member_desktop&rcm=ACoAABIUxTIB-gWzPMQPErZHskqDXatNOleOjok" rel="noopener noreferrer"> Link</a>


![PCAP](https://github.com/user-attachments/assets/4ccd653e-e6f7-47d4-9017-6dee349f32a6)

---

**We have captured this traffic from P13's computer. Can you help him?.**


🔹In network communication, what are the IP addresses of the sender and receiver?

Como estou investigando o arquivo PCAP no PC do usuário P13, utilizo o filtro ¨frame contains P13¨

R: 192.168.235.137,192.168.235.131

<img width="1377" height="432" alt="sender and receiver IP addresses" src="https://github.com/user-attachments/assets/bd908f7f-f7b5-4c6d-b9a1-539abcf56285" />

---

🔹P13 uploaded a file to the web server. What is the IP address of the server?

Utilizo os filtros: ip.src e protocolo HTTP, que traz o resultado de um método POST

R: 192.168.1.7

<img width="1096" height="255" alt="Web Server IP" src="https://github.com/user-attachments/assets/27d4d478-44fc-4d7b-ac28-97143276376d" />

---

🔹What is the name of the file that was sent through the network?

Utilizo o Follow HTTP Stream pelo mesmo pacote anterior

R: file

<img width="1008" height="405" alt="File name" src="https://github.com/user-attachments/assets/7227da9a-9090-44dd-a92d-8c4a6837938d" />

---

Ainda no follow HTTP Stream, obtenho as respostas das duas perguntas seguintes:

🔹What is the name of the web server where the file was uploaded?

R: Apache

🔹What directory was the file uploaded to?

R: uploads

<img width="550" height="324" alt="Web Server and directory" src="https://github.com/user-attachments/assets/048af520-1f37-47bb-b9be-5fee62eb392b" />

---

🔹How long did it take the sender to send the encrypted file?

Statistics -> Conversations 

R: 0.0073

<img width="1559" height="204" alt="Duration" src="https://github.com/user-attachments/assets/64f012f7-96e0-42a2-8e8f-1ea6a07f9660" />








