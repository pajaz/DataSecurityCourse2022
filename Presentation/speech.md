In this presentation I am going to discuss Operations Security or OPSEC. In the first few slides I will explain the general consept and importance of OPSEC in a cyber environment and give a few examples on proper implementation.
I will continue with the basics of why OPSEC is also an integral part of Blue team operations and time permitting, through a step by step case-study discuss how OPSEC failures of the attacker and a thorough investigation by the blue team can take the baddie straight to jail.

1. What is OPSEC? (Operations Security)
OPSEC an abbreviation of Operations Security is a term referring to the ways information is kept from the reach of enemies in order to ensure operation security.  
It is often thought of as being one of the most important parts of a military operation as even minor information leaks can cause the loss of lives or possibly endanger the outcome a mission.  
OPSEC and its general 5 step method can also be applied to non-military areas such as and perhaps especially cyber security as the online world is a continuous battle ground where the attacker is ever active and information is a tool of power. (say something about Facebook/Google/any company with interest on data collection).

2. What are the 5 steps of operational security?

The five steps of operational security are: 

    Identify sensitive data in all aspects of your operation. For example details of product research, customer and employee information. Anything that the adversary might find interesting and thus you need be interested in protecting.
    
    Identify possible threats
    Categorize the information of step one and for each category and identify the threats whether external or internal. 
    
    Analyze security threats and vulnerabilities
    What you have in means of defence? What are the vulnerabilities that may be exploited?
    
    Appraise the threat level and vulnerability risk
    This phase is about prioritizing. For each vulnerability go through the following questions:
    How likely will it be attacked?
    What damages would and attack cause?
    How much effort would it take to recover? 
    
    Rank the vulnerabilities by severity and prioritize mitigation accordingly.
    
    Devise a plan to mitigate the threats
    Create and put in place a plan for risk elimination and mitigation. Keep the methods simple and straightforward so that every employee can do their part without difficulty. 

4. OPSEC for the Blue and Red Teams
 
* Blue Team 
Blue teams are groups assigned to analyze and secure information systems. Part of their work is to isolate and gather forensics data on both successful and unsuccessful attacks so that the defence is better prepared for future attempts. Thy were created as a counter-part to Red Teams  

* Red Team
Red Teams goal is to imitate a real adversary as closely as possible. They employ a much broader array of tactics with less limitations then penetration testers such as even physically infiltrating the target to gather information or gain access.  

5. Actions after detection

When the blue team notices an attempt to attack the system, it is often not the best idea to immediately react to it by mitigation. The blue team analysis team can try isolating the attacker to learn more of their motives and methods for example by sand-boxing the used malware to investigate it. This is all integral forensics work especially when dealing with APT actors. 
A response that is too quick might scare the attacker into changing their methods and tools immediately. A thorough investigation helps react properly to future attempts by the same group. Sharing of data between analysts might also help other targets to identify the threat.
How does the blue team keep the the attacker in the dark about the detection?  

The defender has a clear advantage here called the Defender's advantage or Intruder's dilemma: "The attacker needs to hide all his traces, but the defender needs to just find one trace to unravel the intrusion."
If this advantage is lost and the systems have already been breached assume the worst and think of your communication channels within the team and the organization carefully.

6. Be careful, be silent
https://essay.utwente.nl/84945/1/__ad.utwente.nl_Org_BA_Bibliotheek_Documentfiles_Afstudeerverslagen__Verwerkt_caretta_crichlow_MA_eemcs.pdf (page6)
In order to keep investigating the attacker the analyst should use tools that don't make noise or that make the kind of noise the attacker expects them to make. 

* Few tips: 
When gathering OSINT (Open-Source Intelligence) knowing the used tools is a must. For example while trying to find out more about the adversary's domains or IP addresses you definitely don't want your tools to establish connections to them. This is comparable to the adversary's reconnaissance phase. 

Usage of Passive DNS systems during lookups, performing them from the company system to make the right kind of noise. The attacker expects his malware to contact a certain domain from the company IP-address so this might not trigger any alerts. 

No blindly guessing domains/subdomains. This is what the attacker might do during recon but as the blue team you don't want to make any unnecessary noise.

This should go without saying and has already been discussed during this course but:
Investigate inside a preferably offline sandbox (Virtual or hardware). If a virtual network is not enough and a real Internet connection has to be made, the sand-box should mimic an actual organization workstation as closely as possible and be setup so it is technically impossible for it to communicate with other company Infrastructure.

Sources:

