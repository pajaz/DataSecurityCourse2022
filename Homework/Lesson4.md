# Lesson 4 Homework

Part of Data Security ICT4TF022-3008 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen.  
Link to course page [Here](https://terokarvinen.com/2021/data-security-2022p3-ict4tf022-3008/)

## Intelligence gap

Be careful with the tools. Only use tools to practice targets inside practice
networks separated from the internet. Just port scanning someone else's
computer might be a crime, KKO 2003:36. Be careful with IP addresses. If you
install Kali, don't run random tools when your computer is connected to the
Internet

  • z) Read (or watch or listen) and summarize (This subtask z does not require
    tests with a computer. Some bullets per article is enough for your summary,
    feel free to write more if you like)

      □ € Santos et al: The Art of Hacking (Video Collection): 3. Passive
        Reconnoissance: 3.0 - 3.4 (five videos, about 35 min)
      □ € Santos et al: The Art of Hacking (Video Collection): 4. Active
        Reconnaissance: 4.0 - 4.3 (four videos, about 20 min)
      □ Lyon 2009: Nmap Network Scanning: Chapter 15. Nmap Reference Guide:
        Port Scanning Basics (what's open, closed and filtered? This is a
        sample chapter from a book by the author of nmap, Gordon Lyon aka
        Fyodor Vaskovich)
  • a) My networks. Add a new vboxnet internal network to your VirtualBox
    (File: Host Network Manager...)

  • b) Punchbag. Install Metasploitable 2 practice target on Virtual Box, and
    only connect it to your new virtual network. Login to Metasploitable 2 and
    find out its IP address.

  • c) Hero arrives. Connect the Linux computer you've been using to the same
    network (e.g. Debian 11-bullseye).

  • d) Hello sploitable! Open the website on Metasploitable 2. If you can't
    open the expected website, you're not looking at the correct computer,
    don't run any scans or any similar tests.

  • e) Scanalyses. Port scan Metasploitable 2. Analyze the results. This is a
    big task: explain all you can understand from the results. Is there
    something untypical for a server publicly visible on the Internet? Do you
    think some services could be especially vulnerable, a good start for the
    initial foothold? You explation should take the main part of your answer.
    Make sure you only port scan the correct computer. Disconnect your host
    computer from the Internet as needed.

  • f) Volunteer task: it's raining shells. Break into Metasploitable 2. As an
    added bonus, do it using multiple methods. Only do this using methods
    you're able to use safely, so that attacks only target Metasploitable 2
    practice target.

Tips:

  • O'Reilly Learning € (former Safari) is a bit pricey, but Haaga-Helia
    students get free access trough Haaga-Helia library A-Z page.
  • Practice target Metasploitable 2 should never be visible to real internet -
    as it's very easy to break into it.
  • You can log into Metasploitable 2 with user name "msfadmin" and password
    "msfadmin". If the screen is black, you can click it and press enter.
  • IP address is shown with 'hostname -I', 'ip a' or 'ifconfig'
  • Private (non-routable) IPv4 addresses start with 127.x.x.x, 172.16.x.x,
    10.x.x.x. or 192.168.x.x Check that Metasploitable IP address is in one of
    these. Note that your local production network might use the same addresses
    for something important, especially at work.
  • To connect your attack VM (e.g. Debian Bullseye) to your test network: shut
    down the VM, add another virtual network card (connected to virtual network
    vboxnetN).
  • Metasploitable 2 has a web server in default port. The address is just http
    and the IP address. If the IP address of Metasploitable 2 was
    192.168.43.21, then you should see the web server at http://192.168.43.21.
    The front page shows a large "metasploitable2" text, and the text "Never
    expose this VM to an untrusted network". If you don't see this, you're not
    looking at the right computer, don't scan it.
  • Nmap is the leading port scanner. You can only use it on practice targets
    on practice networks.
  • 'sudo nmap localhost' scans top 1000 ports
  • 'sudo nmap -v -A -p- localhost -oA myscan' # -v is verbose; -p- scans all
    tcp ports; -A (aaand kitchen sink) runs scripts, does OS fingerprint, is
    very loud; -oA myscan save all output formats in current directory with
    names starting with myscan.
  • You can watch nmap work using 'wireshark' network sniffer.

h5
