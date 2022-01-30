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
  
### Pick a CVE, and briefly explain it & why it matters  

#### [CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) (Apache Log4J2)
  
**Affected component**: Apache Log4J2  
**Versions**: 2.0-beta9 through 2.15.0 with exceptions for a few security releases (2.12.2, 2.12.3, and 2.3.1)  
**Component description**: [Logging utility](https://en.wikipedia.org/wiki/Log4j) based on Java and a part of Apache Logging Services  
**Vulnerability Description**: Attacker can take control over log messages and their parameters and thus excecute his own code on the server if the log4j message lookup substitution ["which enables special strings to be replaced, during the time of logging, by other dynamically generated strings."](https://www.techrepublic.com/article/check-for-log4j-vulnerabilities-with-this-simple-to-use-script/) is enabled.  
**Mitigation**: 
As of version 2.15 the message lookup substition is by default disabled. 
As of version 2.16 (and the aforementioned security updates) the message lookup substitution has been completely removed.  



  
## a) Sequel. Solve [SQLZoo](https://sqlzoo.net/wiki/SQL_Tutorial):

### 0 SELECT basics  

1. SELECT population FROM world  
      WHERE name = 'Germany' 
    Population: 80716000  
2. SELECT name, population FROM world  
      WHERE name IN ('Sweden', 'Norway', 'Denmark');  
    <img src="Pictures/Lesson2/sqlZoo0-2.png">  
3. SELECT name, area FROM world  
      WHERE area BETWEEN 200000 AND 250000  
    <img src="Pictures/Lesson2/sqlZoo0-3.png">

### 2 SELECT from World  

1.  
  
2. SELECT name FROM world  
      WHERE population >= 200000000  
    <img src="Pictures/Lesson2/sqlZoo2-2.png">  
3. SELECT name, (gdp / population) as 'per capita GDP' FROM world  
      WHERE population >= 200000000  
    <img src="Pictures/Lesson2/sqlZoo2-3.png">   
4. SELECT name, (population / 1000000) as 'pop/mil' FROM world  
      WHERE continent LIKE 'South America'  
    <img src="Pictures/Lesson2/sqlZoo2-4.png">  
5. SELECT name, population FROM world  
      WHERE name IN ('France', 'Germany', 'Italy')  
    <img src="Pictures/Lesson2/sqlZoo2-5.png">  
6. SELECT name FROM world  
      WHERE name LIKE '%United%'  
    <img src="Pictures/Lesson2/sqlZoo2-6.png">  
7. SELECT name, population, area FROM world  
      WHERE area > 3000000 OR population > 250000000  
    <img src="Pictures/Lesson2/sqlZoo2-7.png">  
8. SELECT name, population, area FROM world  
      WHERE area > 3000000 XOR population > 250000000  
    <img src="Pictures/Lesson2/sqlZoo2-8.png">  
9. SELECT name, ROUND(population/1000000, 2) as 'pop/mil', ROUND(gdp/1000000000, 2) as 'gpd/bil' FROM world  
      WHERE continent LIKE 'South America'  
    <img src="Pictures/Lesson2/sqlZoo2-9.png">  
10. SELECT name, ROUND(gdp/population, -3) as 'gdp/pop' FROM world  
      WHERE gdp >= 1000000000000  
    <img src="Pictures/Lesson2/sqlZoo2-10.png">   
11. SELECT name, capital FROM world  
      WHERE LENGTH(name)=LENGTH(capital)  
    <img src="Pictures/Lesson2/sqlZoo2-11.png">  
12. SELECT name, capital FROM world  
      WHERE LEFT(name, 1) = LEFT(capital, 1)  
      AND name <> capital  
    <img src="Pictures/Lesson2/sqlZoo2-12.png">  
13. SELECT name FROM world  
      WHERE name LIKE '%a%'  
        AND name LIKE '%e%'  
        AND name LIKE '%i%'  
        AND name LIKE '%o%'  
        AND name LIKE '%u%'  
        AND name NOT LIKE '% %'  
    <img src="Pictures/Lesson2/sqlZoo2-13.png">  

## b) Injected. Solve WebGoat:  

### A1 Injection (intro)  

[See here](/Homework/WebGoat/SQLInjections/A1InjectionIntro.md) 
  
## m) Voluntary bonus: Pick your tasks from SQLZoo 1, 3-9.    

## n) Voluntary difficult bonus: WebGoat: SQL Injection (advanced).  

  
## Voluntary difficult bonus: Install a relational database, show CRUD operations using SQL  
  
### Set-up
Decided to go with mariadb as it's a familiar name and I think I've used it in the past for some database related course.  
Instructions for installation (https://www.osradar.com/install-mariadb-database-debian/)  
sudo apt-get update  
sudo apt-get install mariadb-server  
mariadb --version  
mariadb  Ver 15.1 Distrib 10.5.12-MariaDB, for debian-linux-gnu (x86_64) using  EditLine wrapper  


    
## q) Voluntary difficult bonus: Demonstrate aggregate functions (SUM, COUNT) with your own data you created in the previous step.  

  
## p) Voluntary difficult bonus: Install a practice target for SQL injections, exploit it.  

  
## r) Voluntary difficult bonus: Demonstrate JOIN with your own database  

