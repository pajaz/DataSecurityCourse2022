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
  

