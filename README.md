<h1>Hi, I'm Michael! <br/><a href="https://www.linkedin.com/in/michael-musoke/">Cybersecurity Professional</a></h1>

<h2>👨‍💻 Investigation Using Security Onion </h2>

- <b> Security Onion </b>
  - [Investigation of a PCAP](https://github.com/Muts256/Security_Onion-Investigation)

<h2> Introduction </h2>
   Security Onion is a free open-source Linux distribution for network security monitoring, intrusion detection, and log management. It integrated powerful tools like Suricata, Zeek, Wazuh, and the ELK stack to capture and analyse network traffic.
  In the security industry, Security Onion plays a critical role by providing SOCs, incident responders, and threat hunters with a comprehensive platform for real-time monitoring and forensic analysis. Its ability to correlate data from multiple     sources enables organisations to quickly identify, investigate, and mitigate potential threats, thereby enhancing their overall security posture.

<h2> Technology Used </h2>

  Security Onion



  A suspicious packet was captured in an organisation's network traffic. You have been asked to investigate this packet and find what it contains 

<h2>Import the PCAP</h2>

  Log on to the security onion console. Create a directory into which the pcap will be downloaded
  using mkdir command e.g., mkdir Malware
  

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/8d901d6d8603c48c06c66f52607d39a78b881874/S1.png)

  Use the command wget to download an infected pcap from the website, as shown in the image above.

  When the zipped pcap is downloaded, use the unzip command to decompress the pcap. Use the provided password to unlock the zipped file
  i.e., unzip name of file

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/8d901d6d8603c48c06c66f52607d39a78b881874/S2.png)

  Next is to import the pcap using the command so-import-pcap name of pcap. After the import completes, triple-click on the hyperlink and copy it into a browser

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/8d901d6d8603c48c06c66f52607d39a78b881874/S3.png)

  Once the browser opens into the pcap. Select the dates the pcap was captured. In this case 2022-01-07-2022-01-31

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/8d901d6d8603c48c06c66f52607d39a78b881874/S4.png)


  Scrolling to the Event alerts by Suricata and Zeek at the time. Under the event.dataset notice that Suricata and Zeek flagged some packets 
  

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/93a9e8162f2aa4b8b1d6c843807a46e7d63f8829/S5.png)

  In the Alerts tab, 9 counts of Malware Vider are shown

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/93a9e8162f2aa4b8b1d6c843807a46e7d63f8829/S6.png)

  Vidar is a type of malware, specifically an “infostealer” (also called a “stealer”). An infostealer’s goal is to gather sensitive information from an infected computer (passwords, browser credentials, cookies, possibly crypto-wallet data, etc.)      and send that data back to attackers.
  Scrolling further, notice a public IP address. 2.56.57.108. 
  
  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/93a9e8162f2aa4b8b1d6c843807a46e7d63f8829/S7.png)

  Used OSINT tools to find out more about the source IP address. AbuseIPDB in particular.

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/93a9e8162f2aa4b8b1d6c843807a46e7d63f8829/S8.png)

  AbuseIPDB.com, the source IP based in Singapore, was reported several times. It was associated with multiple cases of misuse.


  Use VirusTotal to find more information about this IP address

  ![image alt](https://github.com/Muts256/Security_Onion-Investigation/blob/93a9e8162f2aa4b8b1d6c843807a46e7d63f8829/S9.png)

  VirusTotal showed that the IP address has been reported by 4 security vcendors and has been associated with malicious activity

  More investigations can be done on the file extension and comparing them to the Gary Kessler Magic number to confirm the file extensions are valid; otherwise, they could be obfuscating messages in them.

  
  <h2> Conclusion </h2>

  The preliminary investigation indicates that the IP address identified in the packet capture has multiple malicious reports on both AbuseIPDB and VirusTotal. While these findings do not confirm compromise on their own, they provide sufficient       indicators of potentially harmful activity. The correlation between network traffic in the pcap and the negative reputation of the IP warrants a deeper investigation to determine whether the activity represents an active threat, attempted intrusion, or false positive. Further analysis should include host-level inspection, validation of traffic intent, and review of related logs to assess any impact.

  <h2> Lessons Learned </h2>
  
- **Reputation checks are a crucial first step:** Tools like AbuseIPDB and VirusTotal quickly show whether an IP or domain has known malicious history, helping to prioritise alerts.

- **One indicator is not enough:** A malicious reputation alone does not confirm compromise; multiple data sources and contextual evidence are required to avoid false positives.

- **Packet captures provide valuable evidence:** Analysing PCAPs helps validate whether suspicious network activity is legitimate, accidental, or malicious.

- **Threat hunting requires correlation:** Effective investigations depend on correlating logs, threat intelligence, and network activity rather than relying on single artefacts.

- **Documentation matters:** Recording findings, steps taken, and conclusions makes investigations repeatable, auditable, and defensible.

- **Escalation decisions should be evidence-based:** Even preliminary IOC matches (malicious IPs, unusual traffic patterns) should trigger deeper analysis when uncertainty or risk remains.

- **Using OSINT tools builds speed and confidence:** Familiarity with public threat-intel platforms improves time-to-triage and supports stronger decision-making.

<h2> 🤳 Connect with me:</h2>

[<img align="left" alt="michael-musoke | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />][linkedin]

[linkedin]: https://linkedin.com/in/michael-musoke

<!--
**Muts/Muts256** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
