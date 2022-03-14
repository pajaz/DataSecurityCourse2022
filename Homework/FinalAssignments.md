# Final Homework

Part of Data Security ICT4TF022-3008 course of Haaga-Helia University of Applied Sciences held by Tero Karvinen.  
Link to course page [Here](https://terokarvinen.com/2021/data-security-2022p3-ict4tf022-3008/)
  

##  x) All reports. Add links to each homework report. If you have produced any other material in the course, link that too. (this subtask does not require tests with a computer)

Links inserted to [README.md](../README.md)  
  
## y) Check your references. In all your homework reports each page, each homework must list all of it's sources. Remember to refer to all of your sources, such as course, task page, reports from other students, manuals, web pages, man pages, conferences... Any direct quotes must be marked as such. You can use quotes, blockquote or similar for this. (this subtask does not require tests with a computer)
  
References checked. 

## z) Read (or watch or listen) and summarize (This subtask z does not require tests with a computer. Some bullets per article is enough for your summary, feel free to write more if you like)  
  
### A two security conference presentations from different conferences. (This is about 1-2 hours \[total\] of video for typical conferences)  

[Disobey 2017 - Jaanus Kääp - Hacking Antiviruses](https://www.youtube.com/watch?v=YHbDB9CPz1w )
  
* Former web app developer who now works for an Estonian company Clarified Security which specializes in Vulnerability testing, Development and Research 
* Speech is based on his own experiences  
* Discusses why to attack Antivirus systems and the methods on how to perform the attacks  
* Main points:  
    - Attacking AV systems is an attack towards the protector and because AV systems usually run with escalated privileges, the attacker might elevate their own privileges and gain kernel access for example. Attacking them is also fun.  
    - AV systems are usually very complex and consist of the following parts:  
        + Low privilege GUI
        + Services that are the "Main meat" of AV systems and handle scanning, parsing, packing, emulating
        + Updaters which are usually also services 
        + Software drivers (Speaker's own fortè)
    - Most successful attacks towards AV-systems stem from poorly managed configuration such as letting user controlled input run directly in kernel (IOCTL attack).
* He mentioned [Google Project Zero](https://googleprojectzero.blogspot.com/) blog as a good blog to read on  even though it is pretty advanced.
* Briefly mentioned some of his favorite tools:
    - Process Explorer
    - DriverView
    - DeviceTree
    - WinObj
    - FoxHex (Speakers own tool, still in development in 2017, can't seem to find anything on it via search engine's though)
* Towards the end the speech went a bit technical.   
  
[#GRIMMCon - Xena Olsen - Adversary Detection Pipelines: Finally Making Your Threat Intel Useful](ttps://www.youtube.com/watch?v=qJMwwvdkKOM)  

* Presenters are a CTI Analyst, Pentester and a Red Team Tool Developer
* Discusses the amount of security related data a company faces and how to properly arrange it and form an Adversary Detection Pipeline.  
* The speech is divided into three areas:
    - Pain Points which are basically the things companies should focus on
    - Background info
        + Attribution is hard
        + TTPs (The how of the attack)
    - Adversary Detection Pipelines
        + Way to prioritize threats via structured and unstructured formats.
        + Structured 
            * Known Threats
            * IOSs & TTPs
            * Real-Time Analysis
        + Unstructured
            * Undefined Threats
            * New TTPs
        + Analyzing and Prep/Prio
            * Intent (What do they want?) 
            * Capability (What are they using?)
            * Opportunity (How much do they know?)
* At the end the speech went a bit too business management -like to my liking.
* Recommended reading:
    * Hacker Playbook 2, Peter Kim
    * CTI Squad Goals-Setting Requirements, Scott J. Roberts
    * TI Planning, Brian P. Kimpe
    * The Evolution of CTI: 2019 SANS CTI Survey, p. 7, Rebekah Brown & Robert M Lee
    * Thinking like a hunter, Matt bromiley (2019)

## a) Voluntary, recommended: add a link to your reports as a comment to this page. You might raise in Google, and might also get other people to refer to your work.