# Note-to-self:
Learn more about how attackers deploy root kits and what security measures users can take. 
Learn more about brute-force attacks and how they get around limited password attempts. 
How will Brute-force attacks change with quantum computing and AI?

# Definitions

Spyware - Malware designed to track and spy on you, logging online activities and can log keystrokes from the keyboard.

Adware - Malware that is designed to automatically deliver advertisements to users, usually through pop-up’s or on web browsers.

Backdoor - unauthorized access by bypassing the normal authentication procedures to access a system. 

Ransomware -  Malware designed to hold a computer system or data within it captive until payment is received, and even then may not release the computer. 

Scareware - Malware that uses ‘scare’ tactics to trick users into taking specific actions.

Rootkit - malware designed to modify the host OS to create a backdoor, which can be taken advantage of remotely.

Virus - A type of malware that replicates itself when executed and attaches itself to other executable files.

Trojan Horse - Malware that makes its true intentions to appear legitimate. Trojans do not self-replicate as viruses do.

Worms - malware that does not require user input to replicate, and can infect host networks and other end devices. Ex. Code Red was a worm in 2001 that was able to infect over 300,000 servers in just 19 hours. 

How do I know my system is infected?
Increased CPU usage at idle
Computer freezing and crashing often
A decrease in web browser speed
Many more

**Methods of Infiltration**
Social Engineering - Plainly it is the manipulation of people to perform acts or divulge information, think phishing attacks as an example

Denial-of-Service - DoS attacks are a type of network attack that is relatively simple, sending a large amount of packets to a server or end user to cause interruptions to users, devices or applications.

Distributed DoS - This is a more sophisticated form of DoS using multiple sources of a botnet called zombies to attack. 

Botnet - a network of infected computers called bots that are connected through the internet and controlled by an individual or organization for malicious purposes. Usually used for DDoS attacks, brute-force attacks, or anything that needs mass computing power. 

On-Path Attacks - These are Man-in-the-Middle (MITM) and Man-in-the-Mobile (MITMO) attacks, where threat actors are able to intercept and modify communications between two devices to either collect data or to impersonate one of the devices. 

SEO Poisoning - Search Engine Optimization Poisoning is where attackers take advantage of popular terms to put malicious sites higher in rank than the legitimate websites. 

**Password Attacks**

Password Spraying- Method of ‘spraying’ the most common passwords first, such as “password123”.
 
Dictionary Attacks- Hackers systematically try every word in a dictionary or a list of common words to attempt to break a password.

Brute-force Attacks- Attack using every possible word, number, and symbol combination.

Rainbow Attacks- Using a rainbow chart of already broken hashes and passwords they connect to, they can use this before brute-force attacks to reduce time to break.

Traffic Interception- If passwords are sent over the internet in plain-text which is unencrypted, hackers can intercept these passwords. 

Advanced Persistent Threats (APTs) - APTs can have multi-phased plans that take place over several years. If they have network vulnerabilities, backdoors, or other resources available to them, they may wait until the most opportune time to execute their attack. 

Hardware Vulnerabilities - Hardware flaws that threat actors can take advantage of, this is prevalent with RAM.

Software Vulnerabilities - Vulnerabilities in OS or application code that attackers can use to hijack systems. 

Buffer Overflow - Buffers are memory areas allocated to an application, but when data is written beyond the limits of the buffer, vulnerabilities begin to form. Usually data beyond the buffer is sent to other memory addresses that can be potentially accessed by hackers, therefore compromising data, leading to system crashes, and even escalation of privileges. 

Non-validated input- Threat Actor could abuse input constraints to overflow buffer. 

Race Conditions - This happens when outputs depend on carefully timed inputs and calculations in an ordered method, but if this is interrupted it could cause vulnerabilities. 

Weaknesses in Security Practices - Developers should use carefully vetted libraries when coding programs as to not introduce potential vulnerabilities or backdoors into their code, especially if PII, HIPPA, or Card information will be used in the application. 

Access Control Problems - Process of controlling who can do what and ranges from physical protections to who has access to what files on network systems. Permissions. 

**Software Updates**

Developers are large companies that are constantly debugging and updating the software that they create for the consumer. This leads to patches being released almost everyday to overcome potential CVEs found by others or even internally found. Google’s Project Zero is a good example of a dedicated team finding vulnerabilities and patching them. 

**Cryptocurrency**
Cryptocurrency is digital currency that can be used the same way as USD or Euros, but is structured in a highly decentralized manner with no central bank or governing body in charge of it. This money is kept in crypto wallets. Users may donate computing power in exchange for portions of a crypto currency in a method called “mining”.

Cryptojacking is where  threat actors are able to highjack peoples machines to mine without their knowledge or consent. This can happen on desktops, tablets, and even phones.
