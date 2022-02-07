# Lesson 3 Homework

Part of Data Security ICT4TF022-3008 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen.  
Link to course page [Here](https://terokarvinen.com/2021/data-security-2022p3-ict4tf022-3008/)

# Tricks, Tips and Playbooks

* z) Read and summarize (This subtask z does not require tests with a computer. Some bullets per article is enough for your summary, feel free to write more if you like)  
  + Mitre 2022: ATT&CK Enterprise Matrix  
        - Give examples of a single, easy technique in each tactic. Which is the easiest?  
        - Explain technique, subtechnique, tactic and procedure. Give example of each.  
        - Describe a procedure (a brief description is enough, no need to repeat all steps listed)  
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
