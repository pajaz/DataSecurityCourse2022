# Lesson 2 Homework

Oh, wasp!  

Remember to keep it safe, legal and ethical. Especially if you grasp OWASP 10, you still can't try these to machines you don't own.  

## z) Read and summarize (This subtask z does not require tests with a computer. Some bullets per article is enough for your summary, feel free to write more if you like)  

### OWASP: OWASP 10 2021  
#### [A05:2021-Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
  
* Surfaced in 90% of applications tested in 2021.  
* Issues come from from multiple things such as old components versions with unfixed vulnerabilities, using components with their default settings and credentials in place or too revealing error handling and more. Basically **things that wouldn't happen if proper care would've been taken when setting up the software/environment.**  
* To avoid flaws in configuration:  
	* Have standardised hardening processes for setting up environments  
	* Opt out of things you don't necessarily need  
	* Keep everything up to date and monitor and edit access rights  
	* "Sending security directives to clients, e.g., Security Headers."  
	* Automate supervision
   
#### [A06:2021-Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
  
* Issue stem from:  
	* Not knowing the components you're using as they might be out-dated or plain malicious  
		* Use official sources and prefer signed packages  
	* Not removing the stuff you don't need  
		* Don't install and remove everything unnecessary. Also check third party components.  
	* Not monitoring for updates and vulnerabilites  
		* Proper tools performing scans often to find vulnerabilities, unmaintained sources and old unpatched versions.  
		* Vulnerability email listings and sites by trusted sources  
	* Not acting fast when a vulnerability is found  
		* Patch things up immediately  
  
#### [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)
  
* The attacker manages to insert his own queries or code in to the application  
* 94% of applications tested for a vulnerability of some sort in this category  
* To mitigate injection attacks:  
	* Use safe APIs
	* Validate input data safely on the server-side

  
### Any episode from [Darknet Diaries](https://darknetdiaries.com/).  

#### [EP 11: Strictly Confidential](https://darknetdiaries.com/episode/11/)
  
* A forensics department employee, Andrew works for a company doing compromise assessment for a high profile tech company that wants to know of any flaws in their system. During the investigation an active threat actor was detected and the forensics team was called in. The threat actor was identified to be an APT actor. The group had been active in the system for 5 years and had been succesful in extracting confidential data in the progress. After a 2 month forensics investigation, enough data was gathered and the decision to remediate the malware was made but suddenly the the threat actors went quiet.  
* Compromise assessments is the investigation of company infrastructure to find out any possible weaknesses.  
* APT (Advanced Persistent Threat) actors are well-funded (often  by states as was the case here) groups that have a specific goal in mind and possess the means to get to that goal. The recognition of such groups is often difficult and slow. In this episode the threat actors were recognized due to earlier published reports portraying similar methods.  
* The forensics process involves identifying and isolating the malware to study it and the actions of the threat actors in order to develop a profile for future identification/mitigation.  
	* If the attack is mitigated too soon the defender might not be prepared well enough for future attacks. For example if the actual behavior and goals of the adversary are not investigated properly they might just change their toolset and go unrecognized in the future.  
  
### Pick a CVE, and briefly explain it & why it matters  

#### [CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) (Apache Log4J2)
  
**Affected component**: Apache Log4J2  
**Vulnerability Published**: 2021/12/10  
**Versions**: 2.0-beta9 through 2.15.0 with exceptions for a few security releases (2.12.2, 2.12.3, and 2.3.1)  
**Component description**: [Logging utility](https://en.wikipedia.org/wiki/Log4j) based on Java and a part of Apache Logging Services  
**Vulnerability Description**: Attacker can take control over log messages and their parameters and thus excecute his own code on the server if the log4j message lookup substitution ["which enables special strings to be replaced, during the time of logging, by other dynamically generated strings."](https://www.techrepublic.com/article/check-for-log4j-vulnerabilities-with-this-simple-to-use-script/) is enabled.  
**Mitigation**: 
As of version 2.15 the message lookup substition is by default disabled. 
As of version 2.16 (and the aforementioned security updates) the message lookup substitution has been completely removed.  
  
**So what?**  
If the attacker can execute any arbitrary code he can effectively manipulate data thus compromising confidentiality, accessibility and integrity.  
The log4j 2 utility is widely used by Java applications all over the world.  
  
  
## a) Sequel. Solve [SQLZoo](https://sqlzoo.net/wiki/SQL_Tutorial):

0. SELECT basics [HERE](/Homework/SQLZoo/sqlZoo0.md)  
  
2. SELECT from World [HERE](/Homework/SQLZoo/sqlZoo2.md)  
  
## b) Injected. Solve WebGoat:  

### A1 Injection (intro)  

[See here](/Homework/WebGoat/SQLInjections/A1InjectionIntro.md) 
  
## m) Voluntary bonus: Pick your tasks from SQLZoo 1, 3-9.    

3. SELECT from Nobel Tutorial [HERE](/Homework/SQLZoo/sqlZoo3.md)  

4. SELECT within SELECT Tutorial [HERE](/Homework/SQLZoo/sqlZoo4.md)  

## n) Voluntary difficult bonus: WebGoat: SQL Injection (advanced).  

  
## Voluntary difficult bonus: Install a relational database, show CRUD operations using SQL  
  
### Set-up
    
## q) Voluntary difficult bonus: Demonstrate aggregate functions (SUM, COUNT) with your own data you created in the previous step.  

  
## p) Voluntary difficult bonus: Install a practice target for SQL injections, exploit it.  

  
## r) Voluntary difficult bonus: Demonstrate JOIN with your own database  

