COI model

Threat modeling

Att&CK (attack.mitre.org)
* matrices

## Recon

### Active Scanning
* Scanning the target's infrastucture by monitoring their network traffic to find information that can be used during the attack.  
* Can not be easily mitigated by the defender as the operations performed are happening outside their controlled environment. Rather than mitigating the defender should focus on the availability of sensitive data.  [Pre-compromise](https://attack.mitre.org/mitigations/M1056/)
* Detection is also difficult due to the afformentioned reason but may be detected by unusual amounts of data originating from a single source.  

### Gather Victim Host Information  
* Collecting information of the victim's host through methods like Active Scanning or Phishing for Information as well as infecting websites and collecting user and system information from visitors and accessible datasets.  
* Information may include but is not limited to:  
    * name, assigned IP, functionality, operating system, language, etc.  
* Same problems exist in Mitigation and Detection as with Active Scanning.  

### Gather Victim Identity Information
* Targeted information includes but not limited to:  
    * Employee names, email addresses as well as sensitive data.  
* Methods used: Phishing for Information, Social Media sites, Searching Victim-Owned Websites etc.  
* "Gathering this information may reveal opportunities for other forms of reconnaissance (ex: Search Open Websites/Domains or Phishing for Information), establishing operational resources (ex: Compromise Accounts), and/or initial access (ex: Phishing or Valid Accounts)."  
* Once again similar problems in Mitigation and Detection as with Active Scanning and Gathering Victim Host Information.  
  
### Gather Victim Network Information
* Targeted information includes but not limited to:  
    * Administrative data such as IP ranges and domain names, topology and operations details  
* Collecting information of the victim's host through methods like Active Scanning or Phishing for Information and for example online or other accessible databases.  
* For Mitigation and Detection, see previous records.  
  
### Gather Victim Org Information  
* Targeted information includes but is not limited to:  
    * Names of divisions and departments, Specific business operations, key employee roles and responsibilities.  
* Collecting information of the victim's host through methods like Active Scanning or Phishing for Information and for example online or other accessible databases  
* For Mitigation and Detection, see previous records.  
  
### Phishing for Information
* Gathering sensitive information from targets through misleading electronic communication often applying Social Engineering techniques such as posing as someone else and/or pushing the target to react in hurry.  
* Targeted information includes:  
    * Sensitive or other useful information.  
* Differs from traditional Phishing in that the goal is not to execute malicious code.  
* Can be targeted (single employee, key individuals/departments/companies) or mass-distributed.  
* Mitigation efforts include:  
    * Using technical solutions to filter malicious email/web-content (both as company policies and individual options).    
    * Employee training in threat identification.  
* Monitor and filtering suspicious content and requests both in internal systems and social media.  
  
###  Search Closed Sources
* Acquiring information not generally available either through legitimate sources and databases (i.e. paid subscriptions) or gaining access to leaked information through blackmarkets.  
* For Mitigation and Detection, see previous records.    

### Search Open Technical Databases
* Gathering information that is freely available from online databases and repositories.
* Targeted information includes but is not limited to:  
    * Registrations of domains/certificates.  
    * Public collections of network data/artifacts.  
* For Mitigation and Detection, see previous records.  
  
### Search Open Website Domains
* Gathering information from online sources such as:  
    * Social Media, news sites or sites hosting business information.  
* For Mitigation and Detection, see previous records. 

**EASY**
  
### Search Victim-Owned Sites
* Targeted information includes but is not limited to:  
    * Names of departments, Street addresses, key employee data.  
* For Mitigation see previous inserts.  
* Detection involves:  
    * Monitoring network traffic for indications of a possible enemy recon missions:  
        * Crawlers and large single-source data requests.   
    * Revelation of artifacts related to possibly malicious actions by analyzing metadata.  

End of Recon phase.  

## Resource Development
  
### Acquire Infrastructure
* Getting hold of the infrastructure used for staging, launching and executing the attack either through purchase, lease or renting.  
* Solutions include but are not limited to:  
    * Physical or cloud servers, domains, third-party websites, botnets.  
* Infrastructure solutions can help hide the identity of the adversary by blending in to normal traffic.  
* For Mitigation see most of the previous records.  
* Detection:  
    * "Use of services that may aid in tracking of newly acquired infrastructure such as WHOIS databases for domain registration information."  
    * Internet scans may help in revealing the enemy's inrastructure proactively.  

**EASY**

### Compromise Accounts
* Gain access to existing accounts or services that can be used in later stages. Accounts may exist in single or multiple platforms.  
* Methods for gaining access involve but are not limited to:  
    * Phishing for Information, purchasing hacked credentials or by brute-force attacks.  
* Information of possible targes should be gathered in Reconnoisance stage.  
* For Mitigation see previous record.  
* Detection involves monitoring social media for suspicous accounts.  
  
### Compromise Infrastructure
* Rather than using purchased or rented infrastructure compromised infrastructure can be used to carry out the operation.  
* Makes it easier to hide the adversary's identity.  
* For Mitigation see previous record.  
* Monitoring changes to domain registrant information and/or domain resolution information is part of the Detection.  
*  Internet scans may help in revealing the enemy's inrastructure proactively. 
  
### Develop Capabilites
* In-house development of capabilities.  
* For Mitigation see previous record.  
* Detection phase involves persistent Malware analysis and use of Malware repositories to identify the adversary and development patterns. Usage of certificate tracking services may reveal additional information.  
  
### Establish Accounts
* Building of new online presences (impersonating or invented) to social media or websites to later use for legitimization of your identity.  
* Maybe important for social engineer operations.    
* Cannot be easily mitigated.  
* Detection involves monitoring of social media sites.  
  
### Obtain Capabilities
* Purchase, download or steal capabilities rather than develop them.  
* May involve but is not limited to:  
    * Malware, software (including licenses), exploits, certificates, and information relating to vulnerabilities.  
* For Detection, in addition to what was mentioned in the section Develop Capabilities analysis of Malware may reveal patterns found in previously used malware which could be an indication that they did not develop their own tools.  

**EASY**
  
### Stage Capabilities
* Stage acquired capabilities on acquired infrastructure or on webservices for easy access.    
* If infrastructure or patterns in malware, tooling, certificates, or malicious web content have been previously identified, internet scanning may uncover when an adversary has staged their capabilities.  
   
**END OF RESOURCE DEVELOPMENT**

## Inital Access

Initial Access consists of techniques that use various entry vectors to gain their initial foothold within a network. Techniques used to gain a foothold include targeted spearphishing and exploiting weaknesses on public-facing web servers. Footholds gained through initial access may allow for continued access, like valid accounts and use of external remote services, or may be limited-use due to changing passwords.  
  
The adversary is trying to get into your network.

Possibly easy methods:  
Drive-by Compromise (Need capabilities and compromised infrastructure)  
External Remote Services (Need credentials)   
Hardware Additions (Need physical access)   
Phishing (Need gullible people)  
Replication Through Removable Media (Difficult)  
Supply Chain Compromise (Difficult)  
Trusted Relationships (Need gullible people and to compromise a third-party software)  
Valid Accounts (Need credentials)  
  
## Execution
The adversary is trying to run malicious code.  
  
Execution consists of techniques that result in adversary-controlled code running on a local or remote system. Techniques that run malicious code are often paired with techniques from all other tactics to achieve broader goals, like exploring a network or stealing data. For example, an adversary might use a remote access tool to run a PowerShell script that does Remote System Discovery.  

Methods:  
Command and Scripting Interpreter (Need to run cmd and scripts)  
Container Administration Command (Difficult)  
Deploy Container (Difficult)  
Exploitation for Client Execution ()  
Inter-Process Communication ()  
Native API (Similar to CSI but requires knowledge of native api)  
Scheduled Task/Job (Usually needs admin level access if done remotely)  
Shared Modules (Change Windows Module loader and UNC paths)  
Software Deployment Tools (SCCM n stuff, more complex)  
System Services (Requires setting up services > Admin)  
User Execution (Requites user actions, Plausible)      
Windows Management Instrumentation (Dif)
  
## Persistence 
The adversary is trying to maintain their foothold.  
  
Persistence consists of techniques that adversaries use to keep access to systems across restarts, changed credentials, and other interruptions that could cut off their access. Techniques used for persistence include any access, action, or configuration changes that let them maintain their foothold on systems, such as replacing or hijacking legitimate code or adding startup code.  

Methods:  
Account Manipulation (Credential and permissions editing, changing password frequently, needs permissions)  
BITS Jobs (??)  
Boot or Logon Autostart Execution (Plausible)  
Boot ot Logon Initialization Script (Plausible)  
Browser Extensions (Very plausible)  
Compromise Client Software Binary (More difficult)  
Create Account (If you have the credentials, very easy)  
Create or Modify System Process (More difficult)  
Event Triggered Execution (Medium)  
External Remote Services (Medium)  
Hijack Execution Flow (Difficult)  
Implant Internal Image (Difficult)  
Modify Authentication Process (More complex but interseting)  
Office Application Startup (Easy)  
Pre-OS Boot (Sounds more difficult)  
Scheduled Task/Job (Need admin but doable)  
Server Software Component ()  
Valid Accounts ()  
  
## Privilege Escalation
The adversary is trying to gain higher-level permissions.  

Privilege Escalation consists of techniques that adversaries use to gain higher-level permissions on a system or network. Adversaries can often enter and explore a network with unprivileged access but require elevated permissions to follow through on their objectives. Common approaches are to take advantage of system weaknesses, misconfigurations, and vulnerabilities. Examples of elevated access include:  
* SYSTEM/root level  
* local administrator  
* user account with admin-like access  
* user accounts with access to specific system or perform specific function  

These techniques often overlap with Persistence techniques, as OS features that let an adversary persist can execute in an elevated context.  

Methods:  
Abuse Elevation Control Mechanism (Soundsdif)  
Access Token Manipulation (Sounds dif)
Boot or Logon Autostart Execution (Easy)    
Boot or Logon Initialization Scripts (Easy)  
Create or Modify System Process (Dif)  
Domain Policy Modification (Easyish)  
Escape to Host (Diff)  
Evetn Triggered Execution (Difficult)  
Exploitation for Privilege Escalation (dif)  
Hijack Execution Flow (No idea)  
Process Injection (medium) 
Scheduled Task/Job (More for persistence and other stuff)  
Valid Accounts ()   

## Defense Evasion
  
The adversary is trying to avoid being detected.  

Defense Evasion consists of techniques that adversaries use to avoid detection throughout their compromise.  Techniques used for defense evasion include uninstalling/disabling security software or obfuscating/encrypting data and scripts. Adversaries also leverage and abuse trusted processes to hide and masquerade their malware. Other tactics’ techniques are cross-listed here when those techniques include the added benefit of subverting defenses.  

Methods:  
Abuse Elevation Control Mechanism (sounds dif)  
Access Token Manipulation (sounds dif)  
Execution Guardrails ()  

##  Credential Access
  
The adversary is trying to steal account names and passwords.  
  
Credential Access consists of techniques for stealing credentials like account names and passwords. Techniques used to get credentials include keylogging or credential dumping. Using legitimate credentials can give adversaries access to systems, make them harder to detect, and provide the opportunity to create more accounts to help achieve their goals.  
  
Methods:  

  
##  Discovery
  
The adversary is trying to figure out your environment.  
  
Discovery consists of techniques an adversary may use to gain knowledge about the system and internal network. These techniques help adversaries observe the environment and orient themselves before deciding how to act. They also allow adversaries to explore what they can control and what’s around their entry point in order to discover how it could benefit their current objective. Native operating system tools are often used toward this post-compromise information-gathering objective.  
  
Methods:  
  

##   Lateral Movement  
  
The adversary is trying to move through your environment.  
  
Lateral Movement consists of techniques that adversaries use to enter and control remote systems on a network. Following through on their primary objective often requires exploring the network to find their target and subsequently gaining access to it. Reaching their objective often involves pivoting through multiple systems and accounts to gain. Adversaries might install their own remote access tools to accomplish Lateral Movement or use legitimate credentials with native network and operating system tools, which may be stealthier.  
  
Methods:  
  

##  Collection
  
The adversary is trying to gather data of interest to their goal.  
  
Collection consists of techniques adversaries may use to gather information and the sources information is collected from that are relevant to following through on the adversary's objectives. Frequently, the next goal after collecting data is to steal (exfiltrate) the data. Common target sources include various drive types, browsers, audio, video, and email. Common collection methods include capturing screenshots and keyboard input.  
  
Methods:  
  

##  Command and Control
  
The adversary is trying to communicate with compromised systems to control them.  
  
Command and Control consists of techniques that adversaries may use to communicate with systems under their control within a victim network. Adversaries commonly attempt to mimic normal, expected traffic to avoid detection. There are many ways an adversary can establish command and control with various levels of stealth depending on the victim’s network structure and defenses.  
  
Methods:  
  

## Exfiltration
  
The adversary is trying to steal data.  
  
Exfiltration consists of techniques that adversaries may use to steal data from your network. Once they’ve collected data, adversaries often package it to avoid detection while removing it. This can include compression and encryption. Techniques for getting data out of a target network typically include transferring it over their command and control channel or an alternate channel and may also include putting size limits on the transmission.  
   
Methods:  
  

##  Impact
  
The adversary is trying to manipulate, interrupt, or destroy your systems and data.  
  
Impact consists of techniques that adversaries use to disrupt availability or compromise integrity by manipulating business and operational processes. Techniques used for impact can include destroying or tampering with data. In some cases, business processes can look fine, but may have been altered to benefit the adversaries’ goals. These techniques might be used by adversaries to follow through on their end goal or to provide cover for a confidentiality breach.  
  
Methods:  
  












