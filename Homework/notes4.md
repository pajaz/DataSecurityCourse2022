Measure one cuts twice i.e do your recon.  
Bad recon might end up with you breaking availability to the system. (you break it)   
Recon can be Passive(usually legal and hard to detect) or Active(usually illegal and easier to detect)  
In Finland active port scanning is illegal.  

-----------------------------  
  
Group 5 (W/ Jyri)  
What kind of steps should you take for Recon when planning for an attack without getting caught.  

Start from the easiest to gain information and build up from there.  

Sources for easy information:  
Company Websites,  
News Sites,  
Social Media,  
WHOIS (domain.com),  
Phishing for Information,  
Active Scanning,  

-----------------------------
  
Disrupt one link in a chain, the chain breaks.  

In Cyber Kill Chain by Lockheed, Exploitaition is smaller part then you'd think.  
In pentesting usually just RAM is infected but in reality you need the C&C step afterwards. (Just RAM infection disappears on reboot)    
Always be thinking C-I-A.  

Tools for recon:  
nslookup, whois, geoiplookup (geoip-bin)  
panopticlick (test your own tools and hide your trails)  

Learn:  
Banner Grabbing  
- 

  
  
Basic Network usage
- Wikipedia (Internet Protocol Suite)  
- Three Way Handshake  (https://serverarch.wordpress.com/2018/02/06/tcp-3-way-handshake/)
  
OPSEC fails easily without knowledge (you get caught)  

Pivoting, use information to gain more information  
Example:  
1. Browse for key targets.  
2. Search their online presence for private information (phone number, email, address, hobbies, interests etc..).  
3. Target them outside work environment.  
  
Three Way Handshake  
- 

Few people use password managers > same password everywhere.  

Active Recon  
  
  - Often Iíllegal without proper permissions  
    - Who can give the permission?  
  - Port Scanners, OS fingerprinting  
    - Servers usually have 1 or 2 open ports  
  - Crawlers  
  - nmap (run with sudo)  
    - Popular portscanner.  
        - Mostly works against servers.  
    - Be careful, easily breaks laws. Watch with Wireshark.   
    - Connects to different ports to find open ones.  
    - Port is open if there is a service that answers to calls.  
        - Open sql services is kind of a nono. 
    - Banner Grabbing  (-sV option)    
    - -A ("and kitchen sink", does a lot of tests)  
    - Closed, probably no service on this.  
    - 
  - saas (shodan (student package exists), don't randomly go clicking, might be illegal)  
  - vulnerability scanners, opvas 
    - Not so useful as most of the warnings don't actually work.  
    - nmap -A does a lot of vulnerability scanning.  
    
  
--------------------  
  
  
Bloodhound helps figuring out complex UAM systems. In Windows they are usually overly complex.  
  
Check UNIX command line history for typen passwords. People are dumb.  

Windows stashes passwords in hashed form so you can't get the pw but the hash actually works as a password (minhash,  hash is pass attack or  pass the hash). 
  
TTP = Tactics, Techniques and Procedures  
  
Tommi Mättö had a pretty well thought out story on XXS attack.  

Reference doc for js MDN Web Docs

python3 -m http.server palvelimen verkkoon (0.0.0.0 tarkoittaa tätä, tai oikeastaan localhostia)  
Jos sivun edessä lukee file iso osa js ei toimi

parametrit http:/?ja parametrit

ngrep  is  network grep. Can be used with sniffer for example.  

NMAP presentation by its creator Fyodor
https://www.youtube.com/watch?v=bKUjyeQ78AU&t=23s

Host Discovery  
  


z) Read (or watch or listen) and summarize (This subtask z does not require
  tests with a computer. Some bullets per article is enough for your summary,
  feel free to write more if you like)

  + € Santos et al: The Art of Hacking (Video Collection): 3. Passive Reconnoissance: 3.0 - 3.4 (five videos, about 35 min)
    - Recon is often overlooked but can be the most important step
    - Understanding Passive Reconaisance
     - Map out, understand the target
     - Passive is research without sending any information to the target network thus no alarms are tripped
     - Can find open ports on external network, employees, passwords from public breaches, unlisted subnets (usually the most vulnerable), test machines/systems that have been forgotten and are ill-protected.
     - Information you can find: 

      + Host & Port Discovery
        * Search engine (site:e.com: shows everything on that domain) and a useful tip is to exclude pages that you're not interested in like the basic www.e.com (-site:www.e.com) and such so you might find hidden hosts like: test.e.com or developer sites with possible vulnerabilities. 
        * Certificate transparency: Find issued certificates using a tool. Find issued certs > use tool to find other system they bought certificates for. Google transparency tool for example. 
        * Guess hostnames: nslookup www.e.com and get the ip. try text.e.com. try admin.e.com etc. Dictionary it. whos with ip is nice also to get more data.
        * Regional Internet registries: If you know some ips, go to registry site, type ip and you might find other networks that belong to them + technical contacts + maybe other info that the target might not realize is available. AFRINIC, APNIC, LACNIC, RIPE for different regions of globe.
         - inetnum: network block that belongs to searched org. IP reveals the whole block of ips org is associated with. Good to check from the company if the whole range is acutally owned by the company and if they do and haven't paid attention > vulnerabilities maybe
        * Netcraft searches: Find out what's on the backend of target site
        * Shodan: kind of like censys but you can also search with company name
        * Censys.io: Search ips or ranges and return what kind of services are listening
        * 

      3.3 Searching for files
        * Find useful information from available files
        * Web Searches
          * site:e.com filetype:pdf for example
          * Password files might be online by mistake: site:example inurl:etc -intext:etc ext:password
        * Files contain metadata
         * Usernames and software (Word documents for example, authors and such) Software version is important for pentest
         * ExifTool pulls metadata from files
     - Don't skip:
      - You might miss vulnerabilities
      - You might attack the wrong system which can lead into problems (even legal ones)
      - 

      3.4 Searching for Names, Passwords, and Sensitive Information
        * Public Breaches
          * Adobe, LinkedIn, Dropbox etc...
        * Search pastebin.com

      Google Hacking Database  http://www.exploit-db.com/google-hacking-database



  + € Santos et al: The Art of Hacking (Video Collection): 4. Active Reconnaissance: 4.0 - 4.3 (four videos, about 20 min)

  Objectives:
    * 4.1 Understanding Active Reconnaissance
      - Information is sent to target network
      - Might set off alarms if logs are being looked
      - Can also be called "The Scanning phase"
      - Tip: Get louder step by step to see if anyone's looking

  * 4.2 Exploring Active Reconnaisance Methodologies from an Ethical Hacker Perspective

    - Time sensitive task need thorough enumeration of the target network or computer before attacking (overwheling might occur)
      - Recon helps you decide which systems and services to focus on

  4.3

  Port Scanning:
    - Confirm that the ports found in Passive phase are actually open and find new open ports
    - nmap:
      - Most versatile and stable port scanner
      - Tips:
        + -sS: TCP SYN scan (half-open connection)
          + Send a SYN message to server > server responds with SYN/ACK > Stop without responding.  
          + Fast and one of the most popular scans
        + -vv: verbose information
        + -T4: Increase speed ?
        + -a: Operating system, version detection and minor script scanning
        + -Pn: treat all hosts as online. Recommended when scanning from the Internet ?
        + OUTPUT options help put the data into textfiles
        + -p1-65535, -p U:53,111,137, -p T:21-25,80: Scan every port in the system from 1 to 65535. By default nmap scans only the most common ports so this option allows you to decide. Can also decide between UDP and TCP scans.
        + 
    - Masscan
      - Fastest port scanner (as fast as 25mil packets/s)
      - Good for scanning a lot of ports and not as versatile as nmap
      - Similar look and feel as with nmap
   
    - Udpprotoscanner
      - Fast UDP port scanner
      - If you just need to scan for UDP Services
    
  
  Web Service review:
    - Decide which of the possibly multiple Web applications to prioritize during attack.
    - EyeWitness tool
      - Visit every website given and returns header information and screenshots etc.

  Vulnerability Scanning: 
    - Common mistake is to jump straight here without doing proper recon.
    - This part should be at the end of the recon phase because the methods used are often loud.
    - Tools:
      - Network Vulnerability Scanners:
        + OPENVAS - Free & Open Source
          + For professional environments the payed options are better speed and efficiency wise
        + Nessus - $$
        + Nexpose - $$
        + Qualys - $$
        + Nmap (limited)
          - SCRIPT SCAN options (/usr/share/nmap/scripts)
            - Full list and use guide on nmap website
      - Web Vulnerability Scanners:
        + Nikto
          + Alltime favorite
        + WPScan
          + Specific to WordPress sites
        + SQLMap
          + Database pentest and SQLInjections
        + Burp Suite
          + One of the most popular WVS tools
        + Zed Attack Proxy
          + Similar to Burp but free


  4.3 Surveying Essential Tools for Active Reconnaisance: Port Scanning and Web Service Review

  4.4 Survey Essential Tools for Active Reconnaisance: Network and Web Vulnerability Scanners 
