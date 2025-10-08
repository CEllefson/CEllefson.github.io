# Awareness Presentation Slides
[Cyber 1100 Awareness Presentation.pdf](https://github.com/user-attachments/files/22758384/Cyber.1100.Awareness.Presentation.pdf)


# Project with Clutch Kickers Automotive Repair

For this project I had the great opportunity to help a business I’ve worked with before called Clutch Kickers Automotive Repair owned by Frank Locurto. As a car and truck mechanic, he doesn’t have a lot of time to set up his network at his shop but knows how much this could help his business with storing important information needed for more complex repairs. This is a brief and mostly simplified description of what we went through and did, but I will provide my checklist which has more specifics below for those interested.

For this project I helped him build a Windows 11 Work endpoint computer and a NAS computer flashed with Debian Linux to store his information for use in the future. His router sadly had one ethernet port so I helped him pick out a decent residential switch to hook everything together. After the Internet connection was set up, I worked on his NAS to update/upgrade and set up Samba to help with a more friendly file sharing system. This process was more intimidating since I have less experience with setting up NAS systems and I know linux/windows cannot always work well together but a few guides on the internet made it go relatively smoothly. This NAS allows CKARs to store their automotive technical information along with business information, with the ability to easily encrypt information since it is on Linux. For easier switching between the NAS and the desktop computer we decided to use a KVM switch for better security, allowing us to disable SSH on the Windows 11 computer and ensure “openssh-server” was uninstalled on the NAS. The KVM switch worked out nicer than I originally thought and was very fast. 

After the endpoint and NAS were set up, I made sure that the Windows 11 endpoint was on its most current version, with Microsoft Defender updated with all extra security options enabled. Finally we got to the part of configuring the firewall. For this I used the Windows Defender Firewall with Advanced Settings to ensure a more robust set of rules and to verify that certain ports that are typically attacked are shut. I'll have the ones I was looking for listed below this but think Telnet, FTP, and SSH. 

After that I went into his router's settings and updated them from default login credentials to something a good bit stronger that he is able to remember. I went through the router settings and made sure that they were on the more secure options without hampering his access to the internet or adding new devices to the network. I also updated his DNS resolver to cloudflare for slightly faster internet search speeds along with better security than his ISPs DNS resolver. After the settings were configured I helped him set up a Mesh Wi-Fi system so he can have access to the internet across the shop. 

At this point we know that the endpoint, NAS, Router, and Meshed Wi-Fi is working well and should have good security so now is the time to test these. After receiving written permission from the owner, I began my penetration-testing, which was really just port scanning but it is always important to cover all legal avenues even on benign activities. We went over what all we were going to do, including the program and commands I will be using, and got to show him the process which I think he enjoyed. Even if it is something simple as port scanning, it is interesting if you have never seen it or didn’t know this was something you could do. 

I had Kali Linux flashed on my laptop and utilized the Nmap software to scan for active ports and ones that I had missed. The software was a lot more complex than I thought, with so many different scanning types and options to play around with. I’m glad I used this since I found a few ports (3306 MySQL, 137-139 NetBIOS) I had missed and was able to update the firewall settings. 

After we finished the digital pentesting, I walked the property to examine the physical security of the premises. I found it to be satisfactory but I did make some recommendations, which for obvious reasons I will not be including in this. 

I was happy to say that the network was performing as expected and internet speed tests showed almost full access to the bandwidth for his internet plan. We ran some tests and downloaded a couple programs he wanted on his workstation and moved on to the presentation.

Frank is pretty tech savvy but of course his focus is more on the car repair and sale portion so I tried to tailor the presentation to potential issues he can have in his industries and scams that business owners can face. We went through the notes I have below and talked a little bit on each point. The biggest thing I could harp on for any owner of a business, is to be skeptical about giving out information and be careful what links you click on. Now that he has some information from customers saved, mostly innocuous, it is his job to properly dispose of sensitive information and protect the other information that may be PII. We talked at length about how socially engineered attacks have the opportunity to cause issues for his business, but the less thought about “business email compromise” where companies he regularly deals with can become compromised and act as a threat vector to attack his business. We discussed best practices for passwords and how sentence based passwords, as of now, are king. Of course you still need to add characters, numbers, and upper/lower case letters, but “ThisPasswordIsEasyToRemember” takes 800x10^27 years to crack. We also discussed the different types of malware and how they can work together to take down endpoints and networks, and what that can mean for a business owner. He seemed to receive the information well and enjoyed the whole process. I showed him the HaveIBeenPwned website to see if his email had been compromised, which it had, and recommended a password reset following the new password guidelines. I lastly harped again on the need for MFA for almost anything that would allow for it. If login credentials ever become compromised, it could be the final barrier to losing critical information and data, which would be a huge headache. 

As the network that started only had default login credentials, the risk of intrusion was high but there weren’t really any end points to begin with for threat actors to take advantage of, save the router. Given the ease that a threat actor could breach his network I would say that the system was at risk, but I’m happy that after the proper configuration, RAID 5 set-up, and expanding his understanding and optics, I would say his security posture is fairly strong. It's hard to definitively rate these for smaller businesses since most are for large businesses or organizations, but the increase to his digital hygiene, and configuring firewall and security settings makes a robust security system that requires very little input. For obvious security reasons I will not be posting my recommendations, but I found that a good, better, best approach was very well received. Highlighting the most important parts of a network or physical security and giving priced out options in varying quality and price gives small business owners options that won’t break the bank but will also increase their security posture. With that being said, make sure you do good research on your recommendations so you don’t recommend a lock that could be easily raked for example. 

I actually had a lot of fun doing this project. It felt like a good opportunity to use all the information I had learned over the last year and apply it to a business that will use it several times a week. I got to learn more about port scanning programs along with how to set up a NAS. It was fun and gratifying to know I helped a small business become more functional and safe.



# CKAR Checklist
**Network Set-Up:**

- Set-up Endpoint with Windows 11 and server with Debian Linux (installed with Samba for Windows friendly file-sharing) for information and technical documentation storage, recommend KVM for seamless transition between desktop to server management for users.
- Given the router has one LAN ethernet port (TP-Link Deco X20), I recommend a 4-5 port switch for ethernet connection.
(1Gb minimum, 2.5Gb for no speed impedement) 

- Ethernet is faster and more secure than Wi-Fi even with WPA3
- 3 short Cat6 or Cat7 ethernet cables, cat5e can be used for price but are capped at 1 Gb/s data transfer. 
- Ensure Endpoint, server, and Wi-Fi network is operational with good internet speeds, utilize iperf3 to verify speeds. 
- Update system security and firewall, ensure ports are closed that are unnecessary
  - Port 23 Telnet
  - Port 20/21 FTP
  - Port 22 SSH unless user chooses to use it, less of a security risk than telnet or FTP
  - Port 25 SMTP (Prevents spam pings, only needed if you’re making a mail server, not for sending emails from endpoints)
  - Ports 137, 139, 445 for SMB unless SMBv3 is used (Prior Versions have Eternal Blue vulnerability)
- Ensure Router Does NOT have default login credentials: 
  - 192.168.68.1 (usually for TP link Deco) although 192.168.0.1, 192.168.1.0 or 192.168.1.1 are typical default gateways
- Not for this appointment, but recommendation for VPN at client router through TP-Link VPN Settings for heightened security and IP obfuscation. 

**Pen Testing:**
- For this network security evaluation, we will be conducting light port-scanning utilizing Nmap. This will help us ensure that vulnerable ports are closed.
- For the nmap scanning we will perform a couple different scans to recognize potential vulnerabilities and gather information about the network.
  -  nmap 192.168.68.1 -p- will scan all ports on the router to verify if they are open but can be refined down with specifications such as nmap 192.168.68.1 -p 21-445
     - This is contingent on default gateway IP address, will verify and adjust
  -  nmap 192.168.68.1/24 -sL will list targets on a the network
  -  nmap 192.168.68.1/24 -PR will be used for ARP discovery on the local network.
-   We will also assess the physical security of the premises as physical and cyber security often go hand-in-hand. 
       


# Awareness Poster
<img width="960" height="540" alt="Security Awareness Mini-Poster" src="https://github.com/user-attachments/assets/49aca501-e031-4c20-9b81-a1caa96ea693" />


[Awareness Guide.md](https://github.com/user-attachments/files/22758470/Awareness.Guide.md)
# Security Awareness:

* What are the types of malware that you should recognize?  
  * Worms  
    * No user activation required  
    * Self-replicates and jumps to other devices on the network  
  * Viruses  
    * File vs fileless  
    * Requires user execution  
  * Trojan attacks  
  * Ransomware  
  * Spyware  
    * Keylogger  
  * Rootkit and Backdoor tools  
  * How multiple of these attacks can be used together and spread  
* What can you do to avoid these types of attacks?  
  * This is why it’s important to never click on links on emails you're not 100% certain of.  
  * Always use MFA when available  
* Social Engineering  
  * Phishing/Smishing attacks  
  * Scareware   
  * Business Email Compromises (Think normal parts suppliers, NAPA/O’Reilly)  
  * When in doubt about the validity of an email or text message, always call the person or company directly from a number that you know is legitimate. A 1 minute inconvenience can save a much longer headache.  
  * Roughly 36% of all cyber attacks are socially engineered, so it’s important to recognize the signs  
* Password  
  * Complexity is good, but longer passwords will always be safer than short complex ones  
  * Try to make them 12-15 characters long, but of course more is better  
  * Make them complex as well, upper and lower case letters with numbers and a few special characters  
  * Never use “Password” as a password, these and variations of are often cracked instantly through rainbow charts
