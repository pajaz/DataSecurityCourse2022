# Lesson 3 Homework

Part of Data Security ICT4TF022-3008 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen.  
Link to course page [Here](https://terokarvinen.com/2021/data-security-2022p3-ict4tf022-3008/)

# Tricks, Tips and Playbooks

**ATTN**    
Been sick since last Thursday so progress has been stunted. Finished the WebGoat assignments this morning (2022/2/7), took around 2 hours.  
The articles will require more time. Last Wednesday I read them for 3+ hours and only got to about the **halfway point** of the Mitre 2022 tactics and that's without even looking at the sub-techniques. Will try to finish reading and summarizing this evening (depending on health.)    
**ATTN**

* z) Read and summarize (This subtask z does not require tests with a computer. Some bullets per article is enough for your summary, feel free to write more if you like)  
  + Mitre 2022: ATT&CK Enterprise Matrix  
        - Give examples of a single, easy technique in each tactic. Which is the easiest?  
        - Explain technique, subtechnique, tactic and procedure. Give example of each.  
        - Describe a procedure (a brief description is enough, no need to repeat all steps listed) 
    
  1. [Reconnaissance]()    
    * Gathering any intelligence that may prove useful in the span of the attack.  
    * Technique: Search Open Website Domains for publicly available information such as e-mail addresses, domain names, key target information.  
  
  2. [Resource Development]()  
    * Developing, buying, leasing or stealing resources to be used in carrying out the attack.  
    * Technique: Acquire Infrastrucure such as servers and domains by purchasing them. Easy enough if you have the money, but may leave a papertrail. Maybe even easier would be to download freely available open-source software.  
  
  3. [Initial Access]()  
    * Attempts to gain access to the target network through phishing or exploitation of weaknesses in the system.  
    * Technique: Phishing because all you need is a single target from the mass to fall for your tricks and you might gain access.  

  4. [Execution](https://attack.mitre.org/tactics/TA0002/)  
    * Running the code that was succesfully planted on the target system. Often paired with a plethora of other tactics.  
    * Technique of choice: Use the Command and Scripting Interpreter to run your scripts or commands. Most operating systems have a command line tool installed and through it manipulating the system can be relatively easy.  
  
  5. [Persistence](https://attack.mitre.org/tactics/TA0003/)  
    * Trying to stay in after the initial access.  
    * Technique: Adding startup script to extend your stay. For example in Windows system you only need to edit the startup registry keys which are easy(ish) to find or quite literally just drop a shortcut to a specific startup folder for it to run on login.   
  
  6. [Privilege Escalation](https://attack.mitre.org/tactics/TA0004/)  
    * Getting a higher access-level (like admin account or root)  
    * Technique: Valid Accounts, first gaining control of valid accounts with high engough privileges already in place makes it easy to change the privileges of your next target.  
      
  7. [Defense Evasion](https://attack.mitre.org/tactics/TA0005/)  
    * Avoiding getting noticed by the user or the security installed in the target environment.  
    * Technique: Masquerading your actions, scripts and/or software as processes of different software or into harmless filetypes.  

  8. [Credential Access](https://attack.mitre.org/tactics/TA0006/)  
    * Stealing account name and passwords for more access or privilege.  
    * Technique: Use Keylogging to capture keystrokes while they're being typed in.  
    
  9. [Discovery](https://attack.mitre.org/tactics/TA0007/)  
    * Familiarizing with the target environment to help making the next decision.  
    * Technique: There are multiple pretty easy ones here as a lot the techniques utilize readily available system tools. System Information Discovery should be an easy enough start through cmd.  
  
  10. [Lateral Movement](https://attack.mitre.org/tactics/TA0008/)  
    * Trying to move within or through the target environment to find the intended target and/or the means to access it.  
    * Technique: Usage of Internal Spearphishing to gain new credentials or elevate current rights. People are more likely to fall for phishing attempts when they come from a trusted company account.  
  
  11. [Collection](https://attack.mitre.org/tactics/TA0009/)  
    * Gathering of data within in the target system.  
    * Technique: Once again multiple easy enough ways to gather data as access has already been gained.  Collect email, collect files, pack them for delivery.  
  
  12. [Command and Control](https://attack.mitre.org/tactics/TA0009/)  
    * Attempts to open a communication line with the compromised system for data transfer.  
    * Technique: Using Remote Access Software to communicate with the target system. This type of software is often already present or downloadable from lets say Software Center and can be possibly repurposed.  

  13. [Exfiltration](https://attack.mitre.org/tactics/TA0010/)  
    * Stealing the data that was collected earlier.  
    * Technique: Exfiltration Over Web Services seems like a rather easy one. Choosing a popular Web Service that's most likely accesible from the target system should be easy and as such services are often used by the targets themselves such traffic might go unnoticed.  
    
  14. [Impact](https://attack.mitre.org/tactics/TA0040/)  
    * Alter data to cover tracks or cause further harm.  
    * Technique: Data Manipulation to distract the target and possibly never even get noticed, change a few dates here and some prices there or edit calendar meetings to make sure key personnel are not at the office on your chosen dates. I almost went with Data Destruction but nowadays a lot of the important data is stored on networked drives that are backed up on a regular basis.  
  

  +  OWASP: Cross Site Scripting (XSS)  
* y) Cross Site Story. Write a short story or draw a comic of a cross site  
  scripting attack. Make roles clear: who attacks? Who runs, what code, where? What unauthorized access is gained? (This subtask y does not require
  any tests with a computer.).  
* a) Webgoat: A3 Sensitive data exposure  
    + Insecure Login: 2 Let's try  
    The goal was to get some other user's login details by using a packet sniffer. The sniffer was not really needed. After clicking logging in the Chromium browser's Developer Tools > Network tab a new event start.mvc appeared containing the necessary information under the Payload tab.  
    Since the advice in this part was to use a packet sniffer, I decided to install and try one. Namely [tcpdump](https://www.baeldung.com/linux/sniffing-packet-tcpdump).  
    sudo apt-get update  
    sudo apt-get install tcpdump  

    From the aforementioned site I looked in to the different options it offers.  
    Just running the `sudo tcpdump` without any options was not enough. I did get information on the moving packages but it was not enough. Firstly tcpdump chooses the lowest numbered web interface to listen if no options are selected, and by default you get the none verbose options.  

    pajazzo@derpsec:\~$ sudo tcpdump
    tcpdump: **verbose output suppressed**, use -v\[v]... for full protocol decode
    **listening on enp0s3**, link-type EN10MB (Ethernet), snapshot length 262144 bytes

    Clicking the login button in WebGoat added nothing to the tcpdump stream.  
    So let's get the available interfaces.  
      
    pajazzo@derpsec:~$ sudo tcpdump -D  
    1.enp0s3 [Up, Running, Connected]  
    2.any (Pseudo-device that captures on all interfaces) [Up, Running]  
    3.lo [Up, Running, Loopback]  
    4.bluetooth-monitor (Bluetooth Linux Monitor) \[Wireless]  
    5.nflog (Linux netfilter log (NFLOG) interface) \[none]  
    6.nfqueue (Linux netfilter queue (NFQUEUE) interface) \[none]  
    7.dbus-system (D-Bus system bus) \[none]  
    8.dbus-session (D-Bus session bus) \[none]  
      
    So we'll go with lo (assuming it's localhost here).  
    pajazzo@derpsec:~$ sudo tcpdump -i lo  
    tcpdump: verbose output suppressed, use -v\[v]...   for full protocol decode  
    listening on lo, link-type EN10MB (Ethernet),  snapshot length 262144 bytes  
      
    Now were getting a steady stream of in and outgoing packages, but they seem to not contain enough data to be useful. I'm seeing a lot of packages with length 0, some are larger but not showing anything useful yet. So checked the man tcpdump to see if filtering could be done by package length as I'm pretty sure the user and password info are not in a 0 length package. The manual didn't help but [this](https://www.baeldung.com/linux/sniffing-packet-tcpdump) site offered a solution to limit the package length and also filter the stream to just inbound packets:  
    sudo tcpdump -i lo -v "greater 100 and inbound"  

    Stream looks a lot better now. Ended monitoring after clicking Log in on WebGoat and only returned around 200 packets. A quick scroll through found the following for me:  
    06:42:58.664362 IP (tos 0x0, ttl 64, id 38940, offset 0, flags \[DF], proto TCP (6), length 764)
    localhost.56186 > localhost.http-alt: Flags \[P.], cksum 0x00f1 (incorrect -> 0x9f67), seq 1:713, ack 394, win 10204, options [nop,nop,TS val 1246020279 ecr 1246018409], length 712: HTTP, length: 712  
    POST /WebGoat/start.mvc HTTP/1.1  
    Host: localhost:8080  
    Connection: keep-alive  
    Content-Length: 50  
    sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"  
    sec-ch-ua-mobile: ?0  
    User-Agent: Mozilla/5.0 (X11; Linux x86_64)AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.99 Safari/537.36  
    sec-ch-ua-platform: "Linux"  
    Content-Type: text/plain;charset=UTF-8  
    Accept: */*  
    Origin: http://localhost:8080  
    Sec-Fetch-Site: same-origin  
    Sec-Fetch-Mode: cors  
    Sec-Fetch-Dest: empty  
    Referer: http://localhost:8080/WebGoat/start.mvc  
    Accept-Encoding: gzip, deflate, br  
    Accept-Language: en-US,en;q=0.9  
    Cookie:   JSESSIONID=QV8oFPd56Xw22TjpsXfuzDjaa7kk6ZAGiAO2mYl8  
    {**"username":"CaptainJack","password":"BlackPearl"**} \[|http]
  
    Done. The developer console option was a lot faster though.  

* b) Webgoat: A7 Cross Site Scripting (XSS): Cross site scripting
    + 2 What is XSS?  
    Wasn't much to do here. Followed the instructions and ended up with identical JSESSIONIDs on both opened tabs.  
    + 7 Try It! Reflected XSS  
    This was a lot more difficult and I couldn't actually even finish it properly. I figured from the response that the vulnerable field is the credit card number field. Then I just replaced the credit card number with text console.log and the number above changed green. On lesson 8 I could see that the code should have been inside <script> </script> tags so I don't know why the application told me I passed this one.  

Tips

* XSS, cross site scripting. Think how this is used to actually break
  somewhere. The story helps you to consider the real attack, not just alert
  (document.cookie).
* ATT&CK FAQ can help with concepts
* Insecure login: Sniffer is more realistic than F12 here, so consider
  'wireshark', "tshark -i any -V -Y 'http.request.method == POST'" or 'sudo
  ngrep -d lo assword'.
* A7:2017 Cross Site Scripting: JavaScript bookmarklets no longer work by
  default in most browsers. So use F12 Console to run JavaScriptin your
  browser. Cross Site Scripting: script tags. "Try It! Reflected XSS" is
  done, when the top sign turns green, even if the text says "Well done, but
  ... Please continue.".
