In this presentation I am going to discuss Operations Security or OPSEC. In the first few slides I will explain the general consept and importance of OPSEC in a cyber environment.  
I will continue with the basics of why OPSEC is also an integral part of Blue team operations and through a step by step case-study discuss how OPSEC failures of the attacker and a thorough investigation by the blue team can take the baddie straight to jail.

1. What is OPSEC?
OPSEC an abbreviation of Operations Security is a term referring to the ways information is kept from the reach of enemies in order to ensure operation security. (1)
It is often thought of as being one of the most important parts of a military operation as even minor information leaks can cause the loss of lives or possibly endanger the outcome of a mission.  
OPSEC and its general 5 step method can also be applied to non-military areas such as and perhaps especially cyber security as the online world is a continuous battle ground where the attacker is ever present and in this world information is a tool of power. Facebook and Google don't just offer free services to us out of generosity. 

2. What are the 5 steps of operational security?

The five steps of operational security are (2): 

* Identify sensitive data in all aspects of your operation. For example details of product research, customer and employee information. Anything that the adversary might find interesting and thus you need to be interested in protecting.

* Identify possible threats
Categorize the information of step one and for each category identify the threats whether external or internal. 

* Analyze security threats and vulnerabilities
What you have in means of defence? What are the vulnerabilities that may be exploited?

* Appraise the threat level and vulnerability risk  
This phase is about prioritizing. For each vulnerability go through the following questions:
How likely will it be attacked?
What damages would an attack cause?
How much effort would it take to recover? 
Rank the vulnerabilities by severity and prioritize mitigation accordingly.

* Devise a plan to mitigate the threats
Create and put in place a plan for risk elimination and mitigation. Keep the methods simple and straightforward so that every employee can do their part without difficulty. 

3. Good Practices (1)

* Apply controlled process management so that employees have a clear step-by-step path to follow for example in change management. Good logging systems are integral for monitoring.
* Another originally military based strategy should be applied. That is devices and user accounts should follow a "need to know" basis. Access and privileges should be granted only where needed and nothing more to ensure better security.
* Separate network maintenance and security teams. i.e have a dedicated SOC team in charge of security issues. 
* Automate to escape human error and plan for the worst.


4. OPSEC for the Blue Team (3)
 
* Blue Team 
Blue teams are groups assigned to analyze and secure information systems. Part of their work is to isolate and gather forensics data on both successful and unsuccessful attacks so that the defence is better prepared for future breach attempts. Thy were created as a counter-part to Red Teams  

* Red Team
Red Teams goal is to imitate a real adversary as closely as possible. They employ a much broader array of tactics with less limitations than penetration testers such as even physically infiltrating the target to gather information or gain access.  

5. Actions after detection

When the blue team notices an attempt to attack the system, it is often not the best idea to immediately react to it by mitigation. The blue team analysis team can try isolating the attacker to learn more of their motives and methods for example by sand-boxing the used malware to investigate it (4). This is all integral forensics work especially when dealing with APT actors. That is Active Perstistant Threat actors who are often more well funded (often by state players), with better technology and focused goals and targets.
A response that is too quick might scare the attacker into changing their methods and tools immediately. A thorough investigation helps react properly to future attempts by the same group. Sharing of data between analysts might also help other targets to identify the threat.
How does the blue team keep the the attacker in the dark about the detection?  

The defender has a clear advantage here called the Defender's advantage or Intruder's dilemma(5): "The attacker needs to hide all his traces, but the defender needs to just find one trace to unravel the intrusion." 
If this advantage is lost and the systems have already been breached assume the worst and think carefully of your communication channels within the team and the organization carefully.

6. Be careful, be silent
In order to keep investigating the attacker the analyst should use tools that don't make noise or that make the kind of noise the attacker expects them to make. 

A few tips: 
* When gathering OSINT (Open-Source Intelligence) knowing the used tools is a must. For example while trying to find out more about the adversary's domains or IP addresses you definitely don't want your tools to establish connections to them. This is comparable to the adversary's reconnaissance phase. 

* Usage of Passive DNS systems during lookups, performing them from the company system to make the right kind of noise. The attacker expects his malware to contact a certain domain from the company IP-address so this might not trigger any alerts. 

* No blindly guessing domains/subdomains. This is what the attacker might do during recon but as the blue team you don't want to make any unnecessary noise.

* This should go without saying and has already been discussed during this course but:
Investigate inside a preferably offline sandbox (Virtual or hardware). If a virtual network is not enough and a real Internet connection has to be made, the sand-box should mimic an actual organization workstation as closely as possible and be setup so it is technically impossible for it to communicate with other company Infrastructure.  
  
* All in all the methods described here are very similar to the methods used by an adversary except maybe even more careful that is because the adversary is probably a lot more easily scared off than the defender. Similar ruleset still applies whether attacking or defending. Keep your information secure.
 
8. Case of VandaTheGod
  
While not an OPSEC failure of the defender the case of VandaTheGod is a nice example of bad OPSEC derailing a succesful campaign (8).  
Since 2013 this attacker, a self-proclaimed hacktivist was making a name for himself by defacing mostly government owned sites globally and making a little extra dough on the side by selling credit card, patient and other personal information to the highest bidder.  
The adversary was an active social media user and liked to boast about his successes on multiple platforms, mostly Twitter, under different aliases. He also claimed to be a member of multiple hacking groups that also enjoyed the public attention.
Investigators from a cyber security company Checkpoint started looking into the matter and found a long trail of breadcrumbs from connecting with "others in the hacking community through numerous social media accounts, backup accounts in case of takedown, email addresses, websites and more".  
His failures were not too numerous but they were big. From using the same email address to register multiple domains that could be linked to him  to accidentally posting his other social media account names and real initials online through screenshots.
Even if through the WHOIS record investigators were able to find out his home City and got his initials from the screenshot, finding the correct person would've been difficult from a large city. That is unless the person searched for has posted Cyber activist posts through his real personal Social media account as Vanda did. By cross-referencing the hacker accounts and the personal account it became evident that the same person was behind both and VandaTheGod was reported to the law-enforcement. His accounts went silent at the end of 2019.



Sources:
1) https://www.fortinet.com/resources/cyberglossary/operational-security  
2) https://www.techrepublic.com/article/the-five-military-opsec-steps-that-businesses-can-learn-from/9  
3) https://en.wikipedia.org/wiki/Blue_team_(computer_security)  
4) https://darknetdiaries.com/episode/11/)
5) https://essay.utwente.nl/84945/1/__ad.utwente.nl_Org_BA_Bibliotheek_Documentfiles_Afstudeerverslagen__Verwerkt_caretta_crichlow_MA_eemcs.pdf (ch. 4.3.2)
6) https://www.mbsecure.nl/blog/2018/9/opsec-for-blue-teams-part-1
7) https://www.mbsecure.nl/blog/2018/9/opsec-for-blue-teams-part-3
8) https://research.checkpoint.com/2020/vandathegod/

  
