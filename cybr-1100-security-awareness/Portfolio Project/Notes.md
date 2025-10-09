# Initial Plan for CKAR
[CKAR Checklist.md](https://github.com/user-attachments/files/22758445/CKAR.Checklist.md)
# Network Set-Up:

* Set-up Endpoint with Windows 11 and server with Debian Linux (installed with Samba for Windows friendly file-sharing) for information and technical documentation storage, recommend KVM for seamless transition between desktop to server management for users.  
* Given the router has one LAN ethernet port (TP-Link Deco X20), I recommend a 4-5 port switch for ethernet connection.  
  * (1Gb minimum, 2.5Gb for no speed impedement)   
  * Ethernet is faster and more secure than Wi-Fi even with WPA3  
  * 3 short Cat6 or Cat7 ethernet cables, cat5e can be used for price but are capped at 1 Gb/s data transfer.   
* Ensure Endpoint, server, and Wi-Fi network is operational with good internet speeds, utilize iperf3 to verify speeds.   
* Update system security and firewall, ensure ports are closed that are unnecessary  
  * Port 23 Telnet  
  * Port 20/21 FTP  
  * Port 22 SSH unless user chooses to use it, less of a security risk than telnet or FTP  
  * Port 25 SMTP (Prevents spam pings, only needed if you’re making a mail server, not for sending emails from endpoints)  
  * Ports 137, 139, 445 for SMB unless SMBv3 is used (Prior Versions have Eternal Blue vulnerability)  
* Ensure Router Does NOT have default login credentials:   
  * 192.168.68.1 (usually for TP link Deco) although 192.168.0.1, 192.168.1.0 or 192.168.1.1 are typical default gateways  
* Not for this appointment, but recommendation for VPN at client router through TP-Link VPN Settings for heightened security and IP obfuscation. 

# Pen Testing:

* For this network security evaluation, we will be conducting light port-scanning utilizing Nmap. This will help us ensure that vulnerable ports are closed.   
* For the nmap scanning we will perform a couple different scans to recognize potential vulnerabilities and gather information about the network.  
  * nmap 192.168.68.1 \-p- will scan all ports on the router to verify if they are open but can be refined down with specifications such as nmap 192.168.68.1 \-p 21-445  
    * This is contingent on default gateway IP address, will verify and adjust  
  * nmap 192.168.68.1/24 \-sL will list targets on a the network  
  * nmap 192.168.68.1/24 \-PR will be used for ARP discovery on the local network.   
* We will also assess the physical security of the premises as physical and cyber security often go hand-in-hand. 

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
  * This is why it’s important to never click on links on emails your not 100% certain of.  
* Social Engineering  
  * Phishing/Smishing attacks  
  * Scareware   
  * Business Email Compromises (Think normal parts suppliers, NAPA/O’Reilly)  
  * When in doubt about the validity of an email or text message, always call the person or company directly from a number that you know is legitimate. A 1 minute inconvenience can save a much longer headache.  
  * Roughly 36% of all cyber attacks are socially engineered, so it’s important to recognize the signs
 
# Reflection

I actually had a lot of fun doing this project. It felt like a good opportunity to use all the information I had learned over the last year and apply it to a business that will use it several times a week. I got to learn more about port scanning programs along with how to set up a NAS. It was fun and gratifying to know I helped a small business become more functional and safe.
