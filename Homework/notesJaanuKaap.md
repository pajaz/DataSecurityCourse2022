AV are:
- Complex systems
- High permissions > Attack them, get higher permissions

AV Build up
- GUI (low rights)
- Services ("Main meat" of the AV system)
    * Scanning, parsing, packing, emulating
    * 
- Updater (Usually also services)
- SW-drivers
    * Protection for the AV itself for example (prevetns closing AV), filter-drivers (for example filter which files can be opened in file-system)

- Antivirus buildup - Communication
    * Named objects (event, pipe, mutex)
    * Shared memory
    * RPC (Remote Process Calls)
    * IOCTL 


- AV Attack vectors
    * Remote 
        + Update
            - Updates happen often
            - Is the update server connection encrypted? 
            - Are the sent batches signed? is the signing checked properly?
            - Memory corruptiond?
        + Parsers
            - It is possible to infect a computer through a file the user doesn't even execute
                * Example: A pdf file containing an exploit is sent, target's email client downloads it, AV system automatically starts parsing the file > Exploit triggers
                * Example2: Symantec (2016)
        + Unpackers
            - Lot of viruses and others pack the actual code and during runtime unpack it and execute it (i.e. Skype). Antiviruses have to do the unpacking process to properly investigate the file > If the unpackers are written badly they might contain memory corruptions. 
            - 2016: Symantec&Norton (in kernel), exe file that was packed by a specific packer, sent to user and once it touched the hard-drive it triggered the exploit in kernel and granted attacker full control over kernel. (google project 0 blog recommended)
        + Emulators
            - AV's have emulators for CPU's and such for sandboxing malicious software execution
            - 2016: ESET (push/pop)
        + Terms:
            * Fuzzing
            * Reversing
            * Logic Flaws (historical zip-bomb)
            * Crazy stuff (TrendMicro vs Google)
    * Local (Some code already running on the target computer)
        + ACL (Access Control List) Issues
            - SERVICE_CHANGE_CONFIG (Not so much with AVs anymore)
                + Change the directory or filename that is run as a service
        - File Permissions
        - Unquoted Path
        - Events, Mutexes, Pipes
            - If configured incorrectly > Attacker can create their own pipes for example, or mark the AV to turn it self off.
        - IOCTL (Main focus of the speech)
            - User and driver communication
            - DeviceIoControl (Windows)
                * hdevice, 
                * dwloControlCode 
                * IpInBuffer
                * IpOutBuffer 
                Terms:
                 - Race Condition
            - Same for other drivers
            - Tools:
                * Process Explorer
                * DriverView
                * DeviceTree
                * WinObj
                * FoxHex (Speakers own tool, still in development in 2017)