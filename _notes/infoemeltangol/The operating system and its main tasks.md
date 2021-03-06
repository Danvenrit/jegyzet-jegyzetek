# The operating system and its main tasks
---
### Tasks of operating systems (main ones)
- scheduling
- interrupt management
- process control
- storage and memory management
-  logging
- peripheral management
- resource management system
	-  components can be accessed through it
	-  in case of multiple users/processes
		-  scheduling
		-  assignment and control of privileges
	- provides a consistent environment for programs
### Types of operating systems
- one user, one task
	-  DOS (CLI, not open source)
- one user, multiple tasks
	-  Windows (GUI, not open source)
- multi-user, multitask
	-  Unix, Linux (GUI or CLI, can be open source)
---
### Operational structure
- #### kernel
	- core of the OS
	- runs in the background
	- performs basic tasks
	- manages hardware resources
	- performs multiplexing
		- the kernel dictates how long a particular process can use a particular piece of hardware
	- no need for an OS or kernel if the programmer takes over the tasks when creating the program
		- this was the basic
		- restart was required to start a new program
			- over time boot tasks, utilities and routines became permanent
				- OS-es appeared
				
	- types of kernel
		- monolithic
			- This is a type of operating system architecture in which the entire operating system works in the kernel space.
		- microkernels
			- is the near-minimum amount of software that can provide the mechanisms needed to implement an operating system
		- hybrid/modified microkernels
			-  an operating system kernel architecture that attempts to combine aspects and benefits of microkernel and monolithic kernel
		- exokernel
			- is designed to separate resource protection from management to facilitate application-specific customizationy
			- seeks to provide application-level management of hardware resources
			- are typically small in size because of their limited operability
		- nanokernel 
			- is a small kernel that offers hardware abstraction, but without system services
			 
	- tasks 
		- peripheral management
		- memory access providing
		- processor time allocation
		- storage management
		- file system management
- #### shell (system shell, console)
	- interface between user and kernel
	- manages applications
	- less resource intensive than GUI 
		- most servers are Unix based with shell
	- supports programmable scripts
		- uses some kind of special command language, that the OS understands, and which doesen't need compiling
	- executing user codes
	- runs scripts
	- use of internal commands
		- file and folder operations
			- copy, del, ren, md
		- navigation
			- cd, dir
		- date, time
		- command line statements
	- external commands
		- contained in an executable file started by the command line
		- disk management
			- format, scandisk, diskcopy, chkdsk, etc.
		- memory information
			- mem
		- help
		- text editing
			- nano
		- network device management
			- ipconfig
	- creating pseudo commands
	- internal variables
	- manipulating the environment before new processes
	- redirecting I/O
	- transferring data between processes via pipe
	- starting processes in the background
	- command line editing 
	- command history
	- stopping and restarting running processes
	- sending and receiving signals
	- waiting for another process or sleep
---
### Areas of working
- #### memory management
	- one of the most important resource
	- alloctes memory as efficiently as possible
		- memory management unit
			- most important parts of the process goes to the memory
			- the rest are sent to swap (in UNIX at least)
	- 2 types of programs
		- resident
			- always in memory (can be called upon faster)
				- antivirus
				- firewall
				- ie: most important programs / services of the os
		- transient
			- loads only when called (most third party programs)
- #### process control
	- process
		- started program
		- provides access to resources
			- often impossible to manage because future demand is unknown
				- deadlock
- #### interrupt management
	- interrupt
		- a signal that informs you that something has happened
	- types
		- interrupt
			- signal of a long-awaited data
		- exception
			- generated by the processor, when it detects an error in the process
		- non maskable interrupt
			- severe hardware failure
			- usually terminated by an immediate shutdown (BSOD)
		- trap
			- interrupted by the software
			- if the process directly accesses the OS or would execute and instruction that it has no right to
	- scenario
		1. an interrupt is received
		2. the CPU completes the operation that being performed
			- if no interrupt is disabled at that level, accepts the request
			- otherwise it waits
		3. the CPU saves the state vector of the running process
		4. the CPU switches to privileged (kernel) mode, disabling all interrupts that are less than or equal priority
		5. the CU determines the location of the interrupt request and retrieves the corresponding routine address from the interrupt vector table
		6. the serving routine runs
		7. the CPU returns to user mode, allows disabled requests
		8. the CPU resets the interrupted process state vector, returning control
- #### communication with peripherals 
	- establish a connection between the user and the machine
		- not direct
	- the OS communicates with the hardware
		- only the useful parts are transmitted through the peripherals to the user
---
### Multitasking
- running programs in parallel
- the OS is responsible for separating processes and managing parallel execution
	- usually apparent
	- in reality threads are running alternately, just at a high speed that it can't be noticed by the user
		- Time-Slice Multithreading
	- real multithreading
		- each thread runs one thing continuously
---
### Installing the OS
- media device inserted into the PC
- in BIOS, boot sequence is set
- installation, defining partitions
---
### Booting the OS
- #### BIOS searches boot sectors for boot file
- #### possible dual boot
	- in case of multiple systems
- #### loading kernel
- #### initializing devices
	- searching for new hardware
	- searching for drivers and starting them
- #### starting services
	- GUI
- #### starting user interactions
- #### logging in
- #### starting programs
---
### Shutting down the PC
- When the computer is switched off, the machine stops running programs, processes, system processes and the cuts power

---
### OS failure modes, troubleshooting
- #### BSOD / critical error
	- fatal system failure, the PC can no longer run even basic processes
		- reboot
- #### protection errors 
	- driver failure 
	- corrupted files
	- invalid page faults
		- irregular operation
	- device management errors
	- missing system files
	- kernel errors
- #### what to do 
	- reading documentation
	- checking regedit
	- driver reinstalling
	- possibly a full reinstallation with backup
---
### Hardware installation
- Nowadays it's "plug-n-play", after plugging in, the system automatically installs the basic drivers.
- It is recommended to turn off the PC before removing a part, because safety is number one priority.

---
### Installing, configuring and uninstalling software
- #### install
	- usually installed with an installer software (Wizard)
	- quick installation
		- recommended for average users
	- advanced installation
		- for experts
			- installation location
			- partial installation
	- accepting license agreement
	- more and more OSes are using a store, which centralizes the download and installation of software
- #### uninstall
	- usually done via OS or uninstaller software
---
### Running softwares
- #### automatic startup
	- usually run at boot time
		- slows down the boot process
- #### manual startup
	- when the user starts the program
- #### task manager
	- used to view running programs
	- to stop them
	- to raise their priority
	- stopping unused programs to free up resources
---
### Disk management and file systems
- #### FAT (File Allocation Table)
	- developed for MS-DOS
	- simple, robust
	- designed to be compatible with Windows systems
- #### FAT32 (FAT 32-bit version)
	- an evolution of FAT
		- still used today
	- max partition size 8??TB
	- max file size 4??GB
- #### exFAT (extended FAT)
	- latest version of FAT
	- max partition size 128 PB
	- max file size 16 EB
- #### NTFS (New Technology File System)
	- standard file system for Windows NT and its successors
	- privilege system
	- file compression on the fly
	- creation of fault-tolerant partitions
	- max partition size 8 PB
	- max file size 16 EB
- #### EXT (Extended File System)
	- latest
		- ext4 (2008)
	- linux standard file system
	- max partition size 1 EB
	- max file size 16 GB
---
### Directory structure
- #### file ordering
	- hierarchical directory structure
	- a folder can have contents, subdirectories and one parent directory
	- in case of no subdirectory
		- closing directory
	- absolute path
		- from root directory we specify the path
	- relative path
		- from the working directory we specify the path
### Operations
- #### Windows
	- GUI
- #### Linux
	- create (mkdir)
	- delete (rm -r)
	- copy (cp -r)
	- move (mv)
	- rename
	- listing (ls)
	- directory changing (cd)
	- mounting partition/image file (mount)
---
### Files
- #### what is a file?
	- a coherent set of data with an identifier
- #### most common file types
	- can be executed
		- program files (.exe, .com)
			- machine-coded instructions, loaded int memory and executed when run
		- batch command files (.bat)
			- text commands, compiled by the system when executed
	- data files (.dat)
		- in which programs store the data they need to operate or input
	- text files
		- plain text (.txt)
			- contains only characters, sorted by input
		- formatted text (.doc, .docx, .odt)
			- texts created with a graphical editor
			- have formatting
			- may contain other objects
				- images
		- source files (.cs, .pas)
			- a set of instructions written in a particular programming language
			- made into an executable file by a compiler
	- system files (.sys)
		- essential parts of the OS
	- multimedia files
		- images (.jpg, .png, .gif)
		- sound files (.mp3, .wav)
		- video files (.mp4, .avi)
	- compressed files (.zip, .7z, .rar)
		- containing compressed files, which can function after unpacking
	- other
		- office (.xlsx, .pptx, .accdb)
			- files from spreadsheets, presentation softwares, database managers
		- HTML (.html)
			- web page
		- temp (.tmp)
			- temporary files
- #### naming 
	- consist of 2 parts
		- name
			- freely chosen, within limits
				- max 255 characters
				- no OS reserved characters
					- / \ : <> " | * ?
		- extension
			- file type
- #### properties stored about files
	- filename
	- extension
	- size (B)
	- creation/editing date
	- attributes
		- A (Archive)
			- indicates if the file has not yet been archived
				- not used
		- R (Read only)
		- H (Hidden)
		- S (System)
	- privileges
- #### association
	- windows
		- default programs
		- have to select a manager program
	- other OS
		- no specific association
- #### organizing the physical storage
	- the OS stores item in a save queue on disk
	- during modification, file size can rise -> too big for allocated space -> getting a new space -> creating a hole on the disk
	- filling the holes
		- the OS puts the new files in the first empty space of the right size
		- smaller holes may remain
			- fragmentation
				- holes occupy the space as they are empty, but cannot be filled
		- defragmentation
			- the system repackages files so that no holes are left
- #### physical implementation of operations
	- root catalog
		- contains the identifier, size, properties, sector number
	- data retrieval
		- As long as just deleting a file and not overwriting the sector, the file can be retrieved because it is just and indicator that a sector can be written to.
- #### searching
	- our files can "disappear"
		- the OS provides the search
	- searchable attributes
		- filename
		- extension
		- content
		- date
---
### Parameterized execution
- #### mandatory (specify the scope of the data)
	- without which the command cannot be interpreted
- #### optional (affects the conditions of execution)
	- other parameters, without which the command can be executed
---
### Maintenance of hard drives
- #### formatting
	- the contents of the disk are erased
		- selecting file system to which we want to format
			- quick format
				- only the catalog is erased
- #### partitioning
	- dividing the disk into parts
- #### scandisk
	- lock bad sectors
- #### defragmentation
	- eliminating small empty holes on the disk
---
### Compression
- #### Parkinson's law
	- data fills up the available space
		- compressing data into smaller space
			- increasing density
- #### Redundancy
	- safer, but takes up more space
		- easier to recover in a case of error
- #### error threshold 
	- extraction of unnecessary data
		- indistinguishable color tones
		- inaudible sounds
- #### lossy
	- lack of data outside our sensory limitations does not matter 
		- can be extracted
	- compressed material will not be recoverable
	- compression rate can be adjusted
	- significant space-saving
	- examples
		- JPEG (Joint Photographic Expert Group)
			- divides the image into 8x8 squares, stores the average of the dots
				- only the deviation of the pixels from the average is stored
		- MP3
			- most common audio compression method
			- extraction of inaudible sounds
			- noise filtering
				- bit density reduced
		- H-264 or H-265
			- video compression technique
			- 264
				- pixels within frames are related to each other
			- 265
				- successive frames in a sequence are related to each other
- #### lossless
	- Redundancy minimization
		- transcoding
			- longer code is made shorter
	- ensures perfect recoverability
	- degree depends not only on the procedure but also on the properties of the data set
	- examples
		- RLE (Run-Length Encoding)
			- used for images where it is common for adjacent pixels are the same color
			- color code is written once, then only the number of pixels of the same color
		- Huffman code
			- variable length encoding
			- frequent symbols
				- shorter code
			- rare symbols
				- longer code
			- the code tree containing the optimal code words must also be stored
		- LZW code
		- no preprocessing required
		- reads the file, builds the dictionary to use for encoding
		- dictionary can also be built at decoding
			- no need to store in archive
- #### compression of image, audio, video
	- most of the time we work with compressed files
		- text
			- mostly works on xml basis
				- has a complex folder structure
				- compressed zip-like
		- image
			- lossless
				- bitmap (.bmp)
			- lossy
				- .png, .jpg
			- conditionally lossy
				- .gif 
					- 256 color palette
		- audio
			- .mp3, .ogg
		- video
			- similar to image compression
				- .mp4, .avi
- #### compression programs
	- Windows integrated 
		- zip 
		- works on a folder basis
	- WinRar
		- right-click solution
	- 7z
		- lightweight
		- easy to use
- #### self-compressing, resizing and protected files
	- self extracting
		- no unpacker needed
		- unpacked by an executable file
			- installers
	- scalable
		- needed in the days of floppy disks and today for internet transmission
- #### protected files
	- cannot be unzipped by themselves
	- password needed
---
### Utilities
- #### basic utilities
	- disk/partition managers
		- creating and managing partitions
	- file managers
		- file and folder operations
	- compressors
		- archiving and compressing files
	- office programs
		- word processing, spreadsheets
		- mailing programs
	- multimedia
		- opening, creating and editing multimedia files
	- firewall
		- preventing network intrusions
	- virus protection
		- searching and disposing viruses
- #### types
	- internal
		- part of the OS
			- not compulsory
			- makes the computer easier to use
			- adding new features
	- external
		- installed by the user
---
### Viruses, anti viruses
##### Definition of computer viruses and pests, their properties
- operation: when it runs, it attaches itself to programs and scripts, which it spreads as it runs, it works conditionally: e.g. it activates only after running x times 
- source: flash drives, emails, foreign / cracked programs, unreliable websites
##### Changes in the way how your computer works which can be used to suspect viruses
- unreasonable increasement of file size / unreasonable increase in used storage space
- appearance of foreign files
- runtime problems in programs 
- network management slows down, indicates an error 
- peripheral malfunction 
- general machine deceleration (overloading, etc.)

##### Some examples of the historical development of viruses
- 1990 Chameleon (first polymorph)
	- the code changes with each infection -> hard to detect
- 2000 ILoveYou
	- the most successful of all time, it traveled around the world in 4 hours
- 2004 Bagle, Netsky, Sasser worms
##### Explanation of development
- old viruses
	- releasing a virus -> the programmer might get a job at a company
- new viruses
	- silent viruses
		- data collection, botnet, etc.
##### Types of viruses, their effects
- file virus (oldest)
	- builds into executable files
	- only runs when the infected file is ran
	- conditional operation
		- destructive only when a bool is changed to true (date reached, ran x times, etc.)
- boot virus
	- writes itself to the boot sector of the disk
- macro virus
	- writes itself into the document's commandlist
- trojan
	- a program disguised as something else
- worm
	- distributes copies of itself on the network 
	- consumes memory and bandwith
- spyware
	- data collection, keylogging
##### Methods of defense
- infection of a clean computer
	- virus comes from an external source
	- solution
		- inbound traffic control
		- inspection of data carriers 
		- memory-resident virus shields 
			- checks boot sector, memory and running programs, notifies you if there is a problem 
		- firewall 
			- checks network traffic prohibits incoming data packets for which no request has been initiated 
			- monitors outgoing data packets 
		- antivirus
			- information about viruses is stored in a database 
			- checks programs, looks for virus characteristics (signature search) 
				- advantage
					- gives fast, reliable results 
				- disadvantage
					- it does not detect unknown viruses, as polymorphs are difficult to detect
					- must be updated regularly because of situations where the virus can activate itself 
			- heuristic search 
				- advantage
					- it can detect unknown viruses 
				- disadvantage 
					- slowness, false positives
##### Integrated anti-virus services
- boot check (boot sector, system files)
- auto startup with the system (virus shield)
- browser integration
- virus scan
	- can be started and scheduled
- email scan
##### Some examples of anti-virus programs
- Bitdefender
- Malwarebytes
---
### networking
- #### use of software is needed for network connection
	- drivers
	- traffic control
		- these are usually included in the OS
- #### typical additional functions of a server's OS
	- remote access control
	- ssh server
	- file and printer sharing
	- web server
	- SMTP, POP, IMAP server 
		- mailing
	- FTP server
	- DNS server
	- proxy
	- firewall
	- more CPU focused hardware
- #### Network models (hierarchy)
	- Client - Server
		- Servers provide services to clients
	- Host - terminal
		- The host performs all tasks, the terminal just issues them
	- Peer-to-Peer
		- All machines are servers and workstations in one
- #### Network topologies
	- Bus
		- Each PC is connected to a single central cable
	- Ring
		- The transportation medium forms a circle
		- Data packet travels around until it reaches the receiving PC
		- No problem in the event of a single break
		- No central unit
		- Double ring equals higher reliability
	- Star
		- Central unit (HUB)
			- Everything passes through it
		- In the event of a line break only one machine is disconnected from the network
		- Efficient but expensive
	- Tree
		- Each machine can only be reached on one route
		- In case of a break the whole network can be interrupted
- #### implementation of network connectivity
	- Software
		- driver
		- settings
			- IP
			- DNS
			- gateway
			- subnet mask
			- proxy
			- encryption
			- channel
			- VPN
- #### ways of accessing network services
	- connectivity
		- appropriate infrastructure
		- transmission media
		- settings
	- conditions of use
		- protocols
		- privileges
- #### user identification, privilege management
	- username
	- password
	- 2FA (Two Factor Authenthication)
		- seperate code required for logging in
			- generated by sms or mobile app
	- biometric
		- fingerprint
		- handprint
		- retina scan
		- facial recognition 
- #### credentials
	- assigning privileges is the responsibility of the administrator, facilitated by the OS of the server
	- management is also the responsibility of the server OS
		- login
		- disk space usage
		- right to files, folders, drives
			- read, write, delete, rename. create, search