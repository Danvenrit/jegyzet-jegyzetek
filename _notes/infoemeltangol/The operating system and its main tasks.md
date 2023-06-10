# The operating system and its main tasks
---
### Tasks of operating systems (main ones)
- scheduling
- interruption management
- process control
- storage and memory management
- logging
- peripheral management
- resource management system
	- components can be accessed through it
	- provides a consistent environment for programs
### Types of operating systems
- one user, one task
	-  DOS (CLI, not open source)
- one user, multiple tasks
	-  old Windows (GUI, not open source)
- multi-user, multitask
	-  windows, Unix, Linux (GUI or CLI, can be open source)
	
---
### Operational structure
-  **kernel**
	- core of the OS
	- runs in the background
	- performs basic tasks
	- manages hardware resources
	- performs multiplexing
		- the kernel dictates how long a particular process can use a particular piece of hardware
	- no need for an OS or kernel if the programmer takes over the tasks when creating the program
		- this was the basic at first
		- restart was required to start a new program
		- **over time "boot tasks", utilities debuggers and routines became permanent** 
			- these were created so a programmer could automate the start-up process, or restart process of programs
		- OS-es appeared
	- types of kernel
		- monolithic
			- This is a type of operating system architecture in which the entire operating system works in the kernel space
		- exokernel
			- that exposes low-level hardware resources to application programs, allowing them to directly manage and control hardware resources.
		- nanokernel (microkernel)
			-  is the near-minimum amount of software that can provide the mechanisms needed to implement an operating system
			- It is designed to be minimalistic and provides only the essential functions and services necessary for the system to run
		- hybrid/modified microkernels
			- an operating system kernel architecture that attempts to combine aspects and benefits of microkernel and monolithic kernel
	- tasks 
		- peripheral management
		- memory access providing
		- processor time allocation
		- storage management
		- file system management

- **multiplexing**
	- This method is used in multitask capable systems where the kernel determines which program and for how long can use a specific hardware component

- in Unix bases operating systems, different types of command line interpreters are used, which are called shells in English.

-  **shell (system shell, console)**
	- interface between user and kernel
	- manages applications
	- uses much less resource than GUI 
		- most servers are Unix based with some type of shell
	- supports programmable scripts
		- uses some kind of special command language, that the OS understands, and which doesn't need compiling
	- executing user codes
	- usually supports scripts
- **internal commands** 
	- internal commands A.K.A built-in commands, are commands that are directly integrated into the shell. These commands are part of the shell's functionality and are executed within the shell's process. 
	- **file and folder operations**
		- copy, del, REM, md
	- **navigation in the filesystem**
		- cd, dir,
	- **date and time** 
		- time, date
	- **command line statements** 
		- clr, color
- **external commands**
	- External commands, A.K.A standalone commands, are separate executable files or programs that reside outside the shell or command-line interpreter.
	- **disk management**
		- format, scandisk, diskcopy, chkdsk, etc.
	- **memory information**
		- mem
	- **help** (types that help explain something to the user)
		- help, man, apropos
	- **text editing**
		- nano, vim
	- **network device management**
		- ipconfig, ip a, ping
- **Unix shells basic abilities** (also windows has most of these as well, inherited from old DOS interface)
	- creating pseudo commands
		- used to enhance functionality
	- running scripts
	- if statements (if, case, then)
	- cycles (while, for )
	- internal variables
	- redirecting I/O
	- transferring data between processes (pipe-line)
	- starting processes in the background
	- command line editing (nano, vim)
	- command history
	- command line completion (you start typing a command, and autocomplete it with pressing tab)
	- stopping and restarting running processes
	- waiting for another process or sleep
	
---
### typical operations of an operating system
- **memory management**
	- one of the most important resource
	- allocates memory as efficiently as possible
	- if there is not enough memory for all programs to be run at the same time, the programs which did not fit will be sent to swap memory, which is the backup memory, which is usually borrowed from system storage (which is quite a bit slower)
		- MMU (memory management unit)
			- it makes sures, that those parts of a program that have not yet been loaded into memory, and are still being held in swap memory, are not run until they have been loaded into.
	- 2 types of programs, based on memory usage
		- resident
			- always in memory (can be called upon faster)
				- antivirus
				- firewall
				- i.e.: most important programs / services of the operating system
		- transient
			- loads only when called (most programs, which you launch with an executable)

- **process control**
	- provides access to resources
		- it controls these processes so there will be no issues, usually it makes them split shareable resources
			- there are however cases where two processes want to use a un-shareable resources at the same time  
				- for example: two processes want to use the DVD reader at the same time, and this could create a scenario called dead lock --> usually DVD reader gets stuck, and both process has to be shutdown and DVD reader restarted.
	- processes 
		- are programs that have been launched already

- **interrupt management**
	- interruption
	- is a type of signal to the operating system that a given process should be stopped before it should have finished. 
		- this could be for several reasons, for example because a program has malfunctioned, or a person has no time to wait for the computer to finish a process, or some kind of power outage has occurred.
	- types
		- interrupt
			- for example: 
				- when a computer program stops, because it waits for an input from the user
				- when a program has a given time allocated to it, and is told to halt if it takes too long
		- exception
			- generated by the processor, when it detects an error in the process
		- non maskable interrupt
			- severe hardware error, for example a memory error
			- usually causes BSOD in windows, or Kernel panic in Linux
		- trap
			- interrupted by the software
			- if the process directly accesses the OS or would execute and instruction that it has no right to
			
	- how an interruption usually works
		1. an interrupt is received
			 - such as a hardware device, software request, or exceptional condition
		2. the system will stop the process as soon as it safely can
			- otherwise it will just wait until it can
		3. the system saves the state of the interrupted program, data that will be needed to resume the program later
		4. the CPU switches to privileged (kernel) mode, disabling all interrupts that are less than or equal priority of the interrupt signal
		5. the CPU determines the location of the interrupt request and restores the corresponding routine address from the interrupt vector table
		6. the CPU resets the interrupted process state vector, returning control

- **communication with peripherals** 
	- establish a connection between the user and the machine
		- not direct
	- the OS communicates with the hardware
		- only the useful parts are transmitted through the peripherals to the user
		
---
### Organizing the parallel execution of multiple tasks.
- back in the days when there weren't any way to run different tasks at the same, time you were only able to run a single program, and if you wanted to use a different one, you had to close the one you were using. 
- but with parallel execution you now can run several task at the same time
- with multitasking we can quickly switch between processes, and programs, which is handy in a lot of cases

- the OS is responsible for separating processes and managing parallel execution
	- in reality threads are running alternately (since todays computers are Neumann based, they handle instructions one by one), just at such high speed that it can't be noticed by the user
- There are two main techniques to achieve this
	- **TSM (Time-Slice-Multithreading)**
		- involve the use of multiple threads. It divides CPU time into time slices and switches between different threads during each time slice. 
		- this technique isn't as fast as actually running the tasks in parallel on different threads
	- **real multithreading** 
		- This is the preferred technique because, now this is actually running on different threads at the same time
		
---
### Installing the OS
- media device inserted into the PC
- in BIOS, boot sequence is set
- installation, defining partitions

---
### Booting the OS
- The system does a self check
- BIOS searches boot sector for boot file
- the first boot option get launched
	- if there are several options because of dual boot, and there is no default to which should be launched first, it will offer a choice to which one you want to launch
- kernel gets loaded up first
- after this the operation system starts to boot up different stages generally are
	- initializing devices
		- searching for new hardware
		- searching for drivers and loads them up
	- starting services
		- GUI, clock, network etc.
	- starting user interactions
	- logging page
	- starting up programs
	
---
### Shutting down the PC
- When the computer is switched off, the machine stops running programs, processes, system processes, virus protection is last and when everything is safe the operating system cuts power.

---
### OS failure modes, troubleshooting
- BSOD / critical error (windows)
	- fatal system failure, the PC can no longer run even basic processes
		- reboot
- Kernel Panic / Kernel Oops
	- In Linux
- protection errors 
	- driver failure 
	- corrupted files
	- invalid page faults
		- irregular operation
	- device management errors
	- missing system files
	- kernel errors
- what to do 
	- reading documentation
	- checking regedit
	- driver reinstalling
	- possibly a full reinstallation with backup
	- if problem persist checking hardware
	
---
### Hardware installation
- Nowadays it's "plug-n-play", after plugging in, the system automatically installs the basic drivers.
- It is recommended to turn off the PC before removing a part, because safety is number one priority.

---
### Installing, configuring and uninstalling software
- install
	- usually installed with an installer software (Wizard)
	- quick installation
		- recommended for average users
	- advanced installation
		- for advanced users
			- installation location
			- partial installation
			- optional installs
	- accepting license agreement
	- more and more OSes are using a store, which centralizes the download and installation of software
		- it's con is that it is much safer for the average user, but it lessens freedom, in what programs you could run
- setup
	- usually most applications have a settings tab, where you can change different settings
- uninstall
	- usually done via OS or uninstaller software
	- if a program does not have an uninstaller, you can either use third party uninstallers for example BCUninstaller, which searches for any leftover files that are likely to be connected to the given program and removes them from the system
	- You can also remove them manually, and you just have to delete all of the files which you know of, the remove any registry connections that are related to that program.
- it is common for programs to merge the installer and uninstaller, and if you want to uninstall the app you have to launch the installer again. It usually will give you 3 options:
	- reinstall
	- repair
	- uninstall
	
---
### Running softwares
- automatic start-up
	- usually run at boot time
		- slows down the boot process
		- but a lot of the time it is convenient 
- manual start-up
	- when the user starts the program usually by launching a executable file
- stopping a program
	- usually most programs have a stop button that stops the program. for example a red X button
	- if a program does not have one, or it does not respond to it, you have to run you operating system's task manager, and look for the running up, and force end it.
	- on Linux for example kill command will end programs
- task manager
	- used to view running programs
	- to stop them
	- to raise their priority
	- stopping unused programs to free up resources
- Freeing up memory
	- the easiest way to save up memory is to close some apps, that is not in use
	- If that's not enough using third party "optimizers" can be helpful, which will close a lot of programs which it deems not necessary. usually this is preferred when doing a single task, which requires a lot of ram space. This could be a demanding game, or some kind of rendering task.
	
---
### File organization and management methods
- The files are stored in various clusters on the hard disk, and in order to find them, we need to know the file path. This is where file systems come into play, as they keep track of which file occupies which portion of the disk, what its name is, what encoding it has, and so on.
- types
	- **Sequential File Organization:** In this method, files are stored one after another in a continuous manner. Each file has a logical order and can be accessed sequentially from the beginning to the end. It is simple but not suitable for frequent random access or modifications
	- **Indexed File Organization:** This method uses an index structure to store file records along with their corresponding disk addresses.
	- **File Access and Permissions:** Operating systems implement access control mechanisms to manage file permissions and protect file integrity. Access control lists (ACLs) or file permissions specify who can access, modify, or execute files, ensuring data security and privacy.
	
---
### File systems
- FAT (File Allocation Table)
	- developed for MS-DOS
	- simple, robust
	- designed to be compatible with Windows systems
- FAT32 (FAT 32-bit version)
	- an evolution of FAT
		- still used today
	- max partition size 8 TB
	- max file size 4 GB
- ExFAT (extended FAT)
	- latest version of FAT
	- max partition size 128 PB
	- max file size 16 EB
- NTFS (New Technology File System)
	- standard file system for Windows NT and its successors
	- hierarchy system 
		- different users can have different right to what they can do (read, right, etc.)
	- file compression on the fly
	- creation of fault-tolerant partitions
	- max partition size 8 PB
	- max file size 16 EB
- EXT (Extended File System)
	- latest
		- ext4 (2008)
	- Linux standard file system
	- max partition size 1 EB
	- max file size 16 GB
	
---
### Directory structure
- hierarchical directory structure
	- The files are organized using a hierarchical directory structure, where directories can contain files and subdirectories. The root directory forms the base. Files are accessed using absolute paths starting from the root or relative paths based on the working directory.
	
	- The system of directories forms the directory tree.
		- for example family tree or table of contents
		
	- the components of the file system are separated usually by a ''/'' in most operating systems like Windows, but in others it's ' \' like in Linux
	 
	- working directory
		- this is the directory you are currently in, it was 
		
	- root directory
		- is the basis of the directory structure
		
	- absolute path
		- from root directory we specify the path
		
	- relative path
		- from the working directory we specify the path 
		
	 - children directory
		- From a directory, we can branch out into further directories, which are the children of that directory.
		
	- leaf directory 
		- A directory without children is called a leaf directory.
		
	- parent
		- Each directory has exactly one immediate predecessor (parent)
		
---
### The stored properties of directories
- Name
- Location
- Size
- Permissions
- Creation and modification timestamps
- Parent directory
- Link count
	- The number of hard links pointing to the directory, indicating its level of accessibility and reference
	
---
### Directory operations
- #### Windows
	- create: mkdir
	- delete: del
	- copy: copy
	- move: move
	- rename: ren
	- list: dir
	- change directory: cd
- #### Linux (debian)
	- create: mkdir
	- delete: rm
	- copy: cp 
	- move: mv
	- rename: mv (you could move it to the same place it already is and call it a different name)
	- listing: ls
	- directory changing:  cd
	- mounting partition/image file: mnt
	
---
### Files
- what is a file?
	- a coherent set of data with an identifier
	
- #### Most common file types
	- executables
		- program files (.exe, .com)
			- machine-coded instructions, loaded int memory and executed when launched
		- batch command files (.bat)
			- text commands, compiled by the system when executed, usually it contains a list of commands which will be launched
	- data files (.dat)
		- programs store the data they need to operate or input inside these
	- text files
		- plain text (.txt)
			- contains characters only
		- formatted text (.doc, .docx, .odt)
			- texts created with a graphical editor
			- have formatting
			- may contain images, or videos even
		- source files (.cs, .pas)
			- a set of instructions written in a particular programming language
			- made into an executable file by a compiler
	- system files (.sys)
		- essential parts of an OS
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
			
- #### Naming of files, and syntax 
	- These requirements ensure consistency, compatibility, and proper functioning of the file system.
	- File naming conventions may vary depending on the operating system
	- Character limitations:
		- some characters need to be restricted from usage in file names mainly so they are reserved for special purposes like only the OS should use them, or because they could impact compatibility or security.
			- some characters which are usually restricted: ' / ', " () ", " : ", " ? ", " * ", " <>"
	- Case sensitivity:
		- some do some don't it depends on the operating system
	- File extensions (filetype):
	- Length limitations
	- Forbidden characters
		- these aren't the typical character which are limited, these are special characters which the system cannot really use property, these could be a special Chinese, or Arabic characters which the given operating system locked mainly for safety reasons, or compatibility reasons.
	
- #### Properties stored about files
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
	
- #### Association
	- Windows  and other mainstream operating systems typically associate files with a default program (e.g., .docx with Word, .xlsx with Excel, etc.). If we want to open a file for which Windows doesn't recognize a program, we need to associate it with one of the programs available on our computer. The default program can be changed as desired, in the properties tab of a file
	
- #### Organizing the physical storage
	- The operating system stores files sequentially on the disk. However, if we modify a file and its size increases, it may no longer fit in its original location. In such cases, the system will find the first available empty space that can accommodate the file. As a result, small unusable empty "gaps" are created on the disk, taking up space. To solve this problem, disk **defragmentation** was introduced. During defragmentation, the system rearranges files so that they are tightly packed next to each other, starting from the beginning sector of the disk. 
	- this problem is mainly a problem for hard drives, but for SSD-s these are not a problem at all, because those do not have moving parts, and it does not matter where each data is.
	- For SSD-s it is actually not recommended because those have limited rewrites on their transistors, so overwriting even more data when it is not necessary will degrade it sooner.
	
- ### The forms of specifying the file path.
	- Absolute path --> C:\Folder\Subfolder\File.txt"
	- relative path --> ..\ParentFolder\File.txt
	- UNC path --> \Server\Share\Folder\File.txt
		- it is path used for accessing files on a network share
		
- #### Physical implementation of operations
	- Root directory: This is where the identifiers, sizes, properties, and starting bits (sector numbers) of all files on the disk are stored. The data of a deleted file can be recovered with the help of special programs until the sectors where the file is located are overwritten. During deletion, the system only removes the file from the directory, so it makes the bits available to be overwritten.
	- root catalogue
		- contains the identifier, size, properties, sector number
	- data retrieval
		- As long as just deleting a file and not overwriting the sector, the file can be retrieved because it is just and indicator that a sector can be written to.
		
- #### Searching
	- This functionality allows users to find files or information based on specific search criteria or keywords.
	- searchable attributes (criteria)
		- file name
		- file type
		- file size
		- creation date
		- modification date
		- or even specific keywords or phrases within the file content.
		
- ### Executing commands with parameters, options, switches
	- executing commands with parameters refers to running commands or programs with additional information or arguments that modify their behaviour or specify the desired operation
	- for example Linux's rm (removes a file) command can have these two arguments
		- rm -rf 
		- the r part will remove all files recursively meaning it will delete all subfiles in the folder until there is nothing left
		- the f part will force every delete, even if that would hurt the operating systems wellbeing
		
---
### Maintenance of hard drives
- #### formatting
	- During formatting, the entire contents of the disk are erased. If a quick format is applied, the data remains on the disk, only the directory is deleted, which means that the files may still be recoverable. In such cases, we have the option to choose the file system.
 - #### changing file systems
	 - Certain specialized programs are capable of converting file systems, but for example, Windows can only modify them during formatting.
- #### partitioning
	- dividing the disk into parts, this is useful if we want to isolate parts of the disk for different purposes which could include safety, convenience or even just because of dual boot, and each operating system has one half of the main drive
- #### scandisk
	- On most operating systems scandisk will scan all parts of a hard disk and look for any anomalies, like bad sectors, integrity of files, or other disk errors.
	- On most operating systems these checks can even fix some of these problems like bad sector 
	- on windows its called chkdsk (short for: check disk)
	- on Linux its called fsck (short for: file system check)
- #### defragmentation
	- When a given file grows in size, it could happen that it does not fit in the given sector anymore, or even worse not even close to it, in these cases the files data will be scattered on a hard disk which will hinder performance when using that file. Defragmentation reorders the file so that all of its data will be close together so regular performance will be restored for these files.
	
---
### Compression
- Compression is the process of reducing the size of a file or data, typically by removing redundant or repetitive information. 
- The purpose of compression is to save storage space, reduce transmission time, and improve overall efficiency in storing and transferring data.
- Compression algorithms use various techniques to encode data in a more compact form, making it possible to restore the original data accurately when needed. The principles of compression involve identifying patterns or redundancies in the data and using algorithms to represent them more efficiently.

- #### Redundancy
	- safer, but takes up more space
		- easier to recover in a case of error
		
- #### error threshold 
	- extraction of unnecessary data
		- indistinguishable colour tones
		- inaudible sounds (for humans > 20khz)
		
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
			- used for images where it is common for adjacent pixels to be the same colour
			- colour code is written once, then only the number of pixels of the same colour in the given area
		- Huffman code
			- is a variable-length encoding technique that assigns shorter codes to more frequently occurring symbols and longer codes to less frequently occurring symbols. It is widely used in file compression algorithms such as ZIP and JPEG.
		- Arithmetic Coding
			- Arithmetic coding is a more advanced form of compression that uses fractional values to represent sequences of symbols. It achieves higher compression ratios compared to Huffman coding but requires more computational resources.
			
- #### compression of image, audio, video
	- Image Compression
		- jpeg 
			- It is a widely used lossy compression method for digital images, suitable for photographs and realistic images.
		- png
			- It is a lossless compression format that preserves image quality without significant loss, often used for graphics, logos, and images with transparency.
		- gif
			- support both lossless and lossy compression
			- it has a  maximum color pallete of 256
	- Audio Compression
		- mp3
			- It is a lossy audio compression format that achieves high compression ratios while maintaining acceptable audio quality.
		- aac
			- It is a more efficient and advanced audio compression format than MP3, commonly used for music streaming and digital audio.
		- flac
			- FLAC is a popular audio file format known for its lossless compression, which allows for high-quality audio playback while significantly reducing file size.
			- FLAC files can be converted back to the original uncompressed audio data, providing a bit-for-bit identical reproduction of the source audio.
	- Video Compression
		- mpeg, H.264, H.265,
			- are widely used video compression standards that employ both lossy and lossless techniques
		- mp4
			- It is a widely supported video container format that can use different video and audio codecs for compression.
			
- #### compression programs
	- Windows integrated 
		- zip 
		- works on a folder basis
		- not as versatile but it gets the job done for most use cases like zip files 
	- WinRAR
		- right-click solution
	- 7z
		- lightweight
		- easy to use
		- supports wide variety of compression options
		- open source
		
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
- Operating systems provide various utility programs that assist in different tasks and functions. Some of the common utility programs include:
	- File management utilities: These programs help in organizing, manipulating, and managing files and directories. They allow users to create, copy, move, delete, and rename files or folders, as well as perform other file-related operations.
    
	-  Archiving utilities: These tools enable the compression and decompression of files or folders, allowing for efficient storage and transfer of data. They can create compressed archives in various formats, such as ZIP, RAR, or TAR, and extract files from existing archives.
	
	-  Antivirus utilities: These programs are designed to detect, prevent, and remove malicious software, such as viruses, malware, and spyware. They perform scans on files, directories, and the entire system to identify and eliminate potential threats.
    
	-  Firewall utilities: Firewalls provide network security by monitoring and controlling incoming and outgoing network traffic. They act as a barrier between a computer or network and external networks, filtering network packets based on predetermined rules to protect against unauthorized access and malicious activities.
    
	-  Multimedia utilities: These tools are used for multimedia processing, such as playing audio or video files, editing images or videos, and managing media libraries. They provide features for playback, editing, conversion, and organization of multimedia content.
- #### types
	- internal
		- part of the OS
			- not compulsory
			- makes the computer easier to use
			- adding new features
	- external
		- installed by the user, can be anything
		
- #### the services and characteristics of utility programs
	- services
		- file management
		- system optimalisation 
		- security and privacy
		- backup and recovery
		- multimedia tools
		- networking
		- content creation
	- characteristics
		- special functionality
		- user-friendliness 
		- automation
		- integration
		- safety
		- stability 
		- usefulness 
		- etc.
		
---
### Data protection against unauthorized access, built-in capabilities of operating systems (access control: username, password; data encryption)
- Data protection is a critical aspect of computer systems, and operating systems provide built-in features to safeguard data from unauthorized access. 
- Access control allows the operating system to restrict access to resources and ensure that only authorized users can view, modify, or delete data.
- there are two main safety mechanism
- **usernames and passwords**
	- this is the most basic type of safety mechanisms in an operating system
- **data encryption**
	- Another essential aspect of data protection is data encryption, which involves converting the data into a coded form that can only be deciphered with the appropriate decryption key. Operating systems may provide mechanisms to encrypt specific files, folders, or entire disk drives. Encryption adds an additional layer of security to sensitive data, ensuring that even if unauthorized access occurs, the data remains unreadable and protected.
- by combining all three we can achieve a standard level of safety.

---
### Viruses, anti viruses
- ##### Definition of computer viruses and pests, their properties
	- operation: when it runs, it attaches itself to programs and scripts, which it spreads as it runs, it works conditionally: e.g. it activates only after running x times 
	- source: flash drives, emails, foreign / cracked programs, unreliable websites
	
- ##### Changes in the way how your computer works which can be used to suspect viruses
	- unreasonable increasement of file size / unreasonable increase in used storage space
	- appearance of foreign files
	- runtime problems in programs 
	- network management slows down, indicates an error 
	- peripheral malfunction 
	- general machine deceleration (overloading, etc.)

- ##### Some examples of the historical development of viruses
	- 1990 Chameleon (first polymorph)
		- the code changes with each infection -> hard to detect
	- 2000 ILoveYou
		- the most successful of all time, it traveled around the world in 4 hours
	- 2004 Bagle, Netsky, Sasser worms
	
- ##### Explanation of development
	- old viruses
		- releasing a virus -> the programmer might get a job at a company
	- new viruses
		- silent viruses
			- data collection, botnet, etc.
			
- ##### Types of viruses, their effects
	- file virus (oldest)
		- builds into executable files
		- only runs when the infected file is ran
		- conditional operation
			- destructive only when a bool is changed to true (date reached, ran x times, etc.)
	- boot virus
		- writes itself to the boot sector of the disk
	- macro virus
		- writes itself into the document's command list
	- trojan
		- a program disguised as something else
	- worm
		- distributes copies of itself on the network 
		- consumes memory and bandwidth
	- spyware
		- data collection, keylogging
		
- ##### Methods of defence
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
						
- ##### Integrated anti-virus services
	- boot check (boot sector, system files)
	- auto start-up with the system (virus shield)
	- browser integration
	- virus scan
		- can be started and scheduled
	- email scan
	
- ##### Some examples of anti-virus programs
	- Bitdefender
	- Malwarebytes
	- Avast
	- Windows defender
	- Norton
	
---
### networking
- #### use of software is needed for network connection
	- in order to establish network connections, we first need to activate our network devices, create interfaces (which require corresponding drivers), and configure programs that control the traffic and identify the available machines on the network. The configurations are stored in various files. The necessary programs for connecting a computer to a network are typically included in the operating system.
	- examples for some of these
		- network protocols (such as TCP/IP), network operating systems, network management tools, firewalls, routers, and network monitoring software, and drivers.
- #### typical additional functions of a server's OS
	- remote access control
	- SSH server
	- file and printer sharing
	- web server
	- mailing server 
		- SMTP, POP, IMAP
	- FTP server
	- DNS server
	- proxy
	- firewall
	- more CPU focused hardware
	- ACL-s
	
- #### The logical structure of network communication (server-client and peer-to-peer networks).
	- Network communication can be organized in different logical structures, including server-client networks and peer-to-peer networks.
	- Client - Server
		- In a server-client network, there is a central server that provides services and resources to multiple clients. Clients initiate requests to the server and receive responses in return.
		- these services include
			- data storage, processing, and resource management handles
		- real world examples for client-severs
			- a standard web server
			- cloud storage site
			- email client
	- Host - terminal
		- A host terminal is a computer or device that serves as a user interface for accessing and controlling a remote system or network
		- It allows users to enter commands, execute programs, and retrieve information.
		- Examples include 
			- remote desktop clients, SSH clients, and telnet clients.
	- Peer-to-Peer
		- in a peer-to-peer network, all devices or nodes in the network are considered equal, and they can act as both clients and servers
		- Each node can directly communicate and share resources with other nodes without relying on a central server.
		- Peer-to-peer networks are often used for decentralized file sharing, and pirating as well unfortunately
		- Examples of peer-to-peer networks include BitTorrent, where users can share files directly with each other without a central server
		
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
	- Hardware 
		- network card, Ethernet cable, router, wireless network card, antenna.
	- Software
		- drivers: 
		- settings: (IP, DNS auto/fix; default gateway; subnet mask; proxy)
		- WIFI: SSID
		- encryption type: (WEP, WPA/WPA2 PSK, 802.1x EAP), channel; VPN.
		
- #### ways of accessing network services
	- connectivity
		- appropriate infrastructure
		- transmission media
		- settings
	- conditions of use
		- protocols
		- privileges	
	1. Web browsing: Accessing websites and online services through web browsers like Chrome, Firefox, or Safari.
	2. Email clients: Using email client applications like Microsoft Outlook or Mozilla Thunderbird to send and receive emails.
	3. File transfer protocols (FTP): Transferring files between local and remote systems using FTP clients such as FileZilla or WinSCP.
	4. Remote Desktop Protocol (RDP): Accessing and controlling a remote computer or server using RDP clients like Remote Desktop Connection (Windows) or Remmina (Linux), anydesk.
	5. Virtual Private Network (VPN): Establishing a secure connection to a private network over the internet using VPN clients like Cisco AnyConnect or OpenVPN.
	6. Voice over IP (VoIP): Making voice or video calls over the internet using VoIP applications like Skype or Zoom.
	7. Instant messaging: Communicating in real-time with others using instant messaging platforms such as Slack, Microsoft Teams, or WhatsApp.
	8. Network file sharing: Accessing shared files and folders on a network using protocols like Server Message Block (SMB) or Network File System (NFS).
	
- #### user identification, privilege management
	- username
	- password
	- 2FA (Two Factor Authentication)
		- separate code required for logging in
			- generated by SMS or mobile app
			- or by 2FA code generator hub application
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
- User permissions:
	- Restricting login time and duration
	- Limiting the workstations that can be used for login
	- Limiting the size of writable disk space (quota)
	- Rights associated with files, folders, and drives (delete, rename, create, modify, search, read)
	- etc.
- These user permissions refer to various restrictions and privileges that can be assigned to users in a computer system. They include controlling login times and workstations, managing disk space usage, and defining rights and actions that users can perform on files, folders, and drives. These permissions help to enforce security, manage resources, and ensure proper access control within the system.