# Capture The Flag 1
## Stolen Mount - TryHackMe

**Post LinkedIn:** <a href="https://www.linkedin.com/posts/rafael-salvalagio-ghensev-49671285_tryhackme-ctf-capturetheflag-activity-7405346714842460160--2Ig?utm_source=share&utm_medium=member_desktop&rcm=ACoAABIUxTIB-gWzPMQPErZHskqDXatNOleOjok" rel="noopener noreferrer"> Link</a>


<img width="586" height="267" alt="StolenMount" src="https://github.com/user-attachments/assets/4465dfdb-1b9c-4706-98a2-29cf40ab1794" />

---

**Para encontrar a Flag, precisei analisar um PCAP file e descobrir o que um invasor acessou e roubou de um servidor NFS.**


🔹Utilizando o Wireshark, segui o TCP Stream, que logo mostra uma Hash MD5:

<img width="800" height="800" alt="Hash" src="https://github.com/user-attachments/assets/d7dfbe10-22d2-44c9-b5ff-6ddf0de0221b" />

---

🔹Decifro a Hash usando o site crackstation.net, que me da o resultado: avengers

<img width="900" height="900" alt="Senha" src="https://github.com/user-attachments/assets/47cac711-bc97-4b35-b7d2-7961554a18b0" />

---

🔹Em seguida aparece um arquivo no pacote 286, copio o hexdump e uso o CyberChef para reconstruir o arquivo:

<img width="738" height="160" alt="Arquivo" src="https://github.com/user-attachments/assets/19b5c18e-f9fb-4351-903b-afce465f4aba" />


<img width="1919" height="616" alt="CyberChef" src="https://github.com/user-attachments/assets/33b0517b-0e31-4278-af1b-e6ad8fb9c605" />

---

🔹 Após baixar o arquivo .zip, ele pede uma senha. Uso a senha avengers fornecida anteriormente e consigo descompactar:

<img width="487" height="370" alt="Senha arquivo" src="https://github.com/user-attachments/assets/0fc513ed-1a3c-42f7-8c7b-74c86003d684" />

---

🔹 Dentro tem um QRcode, abro usando um leitor online e por fim, recebo a Flag:

<img width="1404" height="629" alt="Flag" src="https://github.com/user-attachments/assets/3512caf7-5e83-42df-9611-7721208f92e9" />

