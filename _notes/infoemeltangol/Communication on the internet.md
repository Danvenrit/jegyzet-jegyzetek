# Communication on the internet
---
### World Wide Web
- hypertext principle
	- one document is related to another (links)
	- pages are written in HTML
	- traditional text, which includes formatting instructions
	- protocol: HTTP - Hypertext Transfer Protocol
- multimedia compatible
- client-server based
	- web server software runs on servers
	- connection is only established for the duration of the data transfer
	- all requests and responses are independent
- the most popular service on the internet
- browsers: Google Chrome, Microsoft Edge, Firefox, Opera

---
### Internet services and their characteristics:
- IRC (Internet Relay Chat) - a chat protocol used for real-time text communication over the internet.
- Internet telephony - VoIP (Voice over Internet Protocol), for example, Skype, allows voice calls over the internet.
- Email - electronic mail for sending and receiving messages over the internet.
- Telnet, now: SSH (Secure Shell) - remote computer access through a terminal (console, command prompt), for example, PuTTY.
- FTP (File Transfer Protocol, scp/ftp/sftp protocols) - used for transferring files between computers over a network.
- WWW (World Wide Web, http/https protocols) - client-server based system for accessing and viewing web pages.
- WAP (Wireless Application Protocol) - a protocol designed for mobile devices, reducing data traffic by omitting elements like CSS and JavaScript.
- Torrent - peer-to-peer file sharing, where users exchange files directly with each other; as users download, they also upload completed parts for others to download; NOT illegal, although often associated with illegal downloading of movies, music, and software.
- Online streaming: Provides access to audio and video content in real-time without the need for downloading. Services like Netflix, YouTube, and Spotify fall under this category.
- Social media: Platforms that facilitate social interaction and content sharing among users. Examples include Facebook, Instagram, Twitter, and LinkedIn.
- Cloud storage: Offers remote storage space for users to store and access their files and data from anywhere with an internet connection. Examples include Google Drive, Dropbox, Mega.
- Online shopping: Allows users to browse and purchase products or services through e-commerce websites, such as Amazon or eBay.

---
### Terms
- URL (Uniform Resource Locator)
	- standardized address
		- structure: `https://hu.megolds.org:80/oki`
			- https - protocol
			- hu - subdomain
			- megolds - second-level domain
			- org - top-level domain
			- :80 - port (not required)
			- /oki - subdirectory
- HTML 
	- HyperText Markup Language
		- descriptive language
		- <> commands
		- text documents
- CSS (Cascading Style Sheets)
	- descriptive language
	- provides structured display
	- gives consistent look across multiple web pages
- http/https (HyperText Transfer Protocol (Safe))
	- information transfer protocol
	- for collaborative, hypermedia information systems
- website/webpage
	- computer document accessed via the web
- home page
	- the default page of a website
- updating
	- web page refresh (repeated retrieval)
	- web page refresh (updating information)
- history
	- our browsing history
- cookie: a data file placed on the user's PC via the browser
	- used for identification 
		- persistent until delete
		- session: persists until leaving the website
- TCP/IP (Transmission Control Protocol/Internet Protocol)
	- the basic protocol structure that builds the interned
	- named after its two main protocols
- IP address
	- network identifier
		- used by machines to identify each other
		- every machine connected to the Internet has one
			- permanent
			- dynamic
			
---
###  The rules for using and accessing internet services
- Internet services typically have their own terms of use. These define the expected usage and may provide additional guidance or help. 
	- For example, Google's Terms of Service.
	
---
### Examples of services available through the internet (e.g., online commerce):
- Online commerce, online stores (eBay, Amazon): Allows users to browse and shop for products from the comfort of their homes, view product details and prices, and place orders for delivery, even from international sellers.
- Search engines: Google (google.com), Yahoo (yahoo.com), Bing (bing.com).
- Timetables: Public transportation schedules like Volán (menetrendek.hu), railway (elvira.hu), public transportation in Budapest (bkk.hu), or using Google Maps.
- Route planning: Google Maps (maps.google.com).
- Cloud storage: Google Drive, Dropbox, OneDrive, Mega.
- Social media platforms: Facebook (facebook.com), Google+ (plus.google.com), Twitter (twitter.com).
- Video sharing: YouTube (youtube.com).
- Email services: Gmail (mail.google.com), Outlook (outlook.com).
- Office applications: Google Docs/Sheets (docs.google.com), Microsoft Office (office.live.com).
- Phone directories: telefonkonyv.hu, tudakozo.telekom.hu, telefonkonyv.telekom.hu.
- E-tax filing: nav.gov.hu (Hungarian Tax and Customs Administration).
- Online university admission: felvi.hu (Hungarian higher education admission system).

---
### User identification 
- User identification is performed on the server side, typically using SSL/TLS encryption. The server may require user registration or subscription for access and authorization.

---
### structure of an email
- An email consists of two parts: the header and the body. The body contains the actual message, while the header carries necessary information for the email system. The header is created by the email program used to send the email, and each computer adds a bit of information as it passes through.

- Components of an email:
	- Recipient: The email address of the person to whom the email is being sent, for example: [xy@yx.hu](mailto:xy@yx.hu)
	- Carbon Copy (CC): If we want to send the same email to multiple people, we can specify their email addresses here. The recipients can see each other's addresses, as well as the address of the first recipient, allowing them to reply to all.
	- Blind Carbon Copy (BCC): The recipients listed here receive the email, but their names will not be visible in the email.
	- Attachments: Files (such as photos, audio, video, saved documents, etc.) sent within the email are placed here. It is useful to upload large files to an online storage and share the link with the recipient.
	- Subject: A brief summary or title of the email. This is the first thing the recipient sees and determines whether they will read the email. It is recommended (though not mandatory, as some spam filters may filter it out) to fill in the subject field.
	- Email Content: This is where the actual text message is written. The size of the text doesn't matter much, but the size of attachments does.
	
---
### functions of an email service
- **Writing:** Composing and creating a new email message.
- **Receiving:** Receiving incoming email messages in the inbox.
- **Replying:** Responding to an email message that has been received.
- **Forwarding:** Sending a received email message to another recipient.
- **Deleting:** Removing unwanted or unnecessary email messages.
- **Saving:** Storing email messages for future reference or archiving.
- **Printing:** Printing out email messages on a physical paper format.

---
### The problems related to email exchanges:
- Encoding
	- Issues related to the encoding or character set used in email messages, which can result in garbled or unreadable text if not properly handled.
	
- Mailer Daemon: 
	- The Mailer Daemon is an automated system that sends error messages or notifications when an email fails to be delivered. It notifies the sender about delivery issues such as an invalid recipient address or a full mailbox. The presence of a Mailer Daemon message indicates a problem with the email delivery process.
	
---
### The typical error messages in email sending, their meanings, and how to handle the problems.
- When sending emails, various error messages may occur, indicating different issues with the delivery process. Here are some common error messages and their meanings:

1. "Invalid recipient address": This error occurs when the email address of the recipient is incorrect or doesn't exist. To resolve this, double-check the recipient's email address for any typos or contact the recipient to obtain the correct address.
    
2. "Mailbox full": This error indicates that the recipient's mailbox is full and cannot accept any new messages. The sender can either wait until the recipient clears their mailbox or contact the recipient through an alternative means to notify them of the issue.
    
3. "Delivery timed out": This error message suggests that the email server failed to deliver the message within a specified time limit. It could be due to network issues or problems with the recipient's email server. Resending the email or contacting the recipient to verify their email server's status may be necessary.
    
4. "Message rejected as spam": This error occurs when the recipient's email server identifies the message as spam and blocks its delivery. Reviewing the email content, avoiding suspicious or spam-like language, and considering sender authentication methods (such as SPF, DKIM, or DMARC) can help minimize this issue.
    
5. "Authentication failed": This error indicates that the sender's email server failed to authenticate properly with the recipient's server. Checking the authentication settings, ensuring correct login credentials, and verifying the server's security protocols (such as SSL/TLS) can help resolve this problem.

---
### Managing incoming emails:
- Reading
- Marking as read/unread
- Labelling
- Moving
- Archiving
- Deleting

---
### transmission options for internet
- Fibre optic 
	- the fastest transmission channel today; its operation is based on total internal reflection of light, and since it involves light, its speed is equal to the speed of light. 
- Satellite
	- data transmission using low Earth orbit artificial satellites; accessible anywhere, but costly and cumbersome.
- WLAN 
	- wireless local area networks are commonly used for local networks, especially due to the popularity of mobile devices. 
- Mobile network
	- utilizes the 3G (or 4G) mobile network established by service providers.
	
### types of connection providers
- Modem connection
	- Solution for data transmission over a telephone line using a modem.
- Leased line
	- Separate internet line setup, primarily available for business customers.
- ADSL (Asymmetric Digital Subscriber Line)
	- Broadband connection with different download and upload speeds.
- Cable TV
	- Broadband service provided through the infrastructure of cable television companies.
	
---
### Characteristics of FTP service, its problems.
- FTP (File Transfer Protocol) is a standard for file transfer over a TCP/IP-based network.
- It enables downloading or making files accessible to others over a network, even across different operating systems.
- It is client-server based, with both server and client programs available for most operating systems (excluding mobile).

### Methods of connecting to FTP server (with or without a username)
- Anonymous connection refers to when login credentials are not required, and a portion of the server's content is public.
- Closed server refers to the need for authentication before login. Various types of authentication are possible, typically using a username-password pair. In the case of SFTP connection, the password can be replaced with a private key used during SSH login. Two-factor authentication may also be necessary.
- connection with email is also possible

---
### File transfer options and limitations via email.
- Email is a widely used method for communication, but it also offers limited capabilities for file transfer. While email allows attachments to be sent alongside messages, there are certain restrictions and limitations to consider:

1. Attachment Size
	-  Most email services impose a limit on the size of attachments that can be sent. This limit can vary depending on the email provider and the recipient's email system. Common attachment size limits range from a few megabytes to tens of megabytes. Sending larger files may result in delivery failures or the need to compress files.
    
2. File Types
	- Certain file types may be restricted by email providers due to security concerns. Executable files (.exe), script files (.bat, .sh), and certain compressed file formats (.zip, .rar) are often subject to restrictions or scanning for potential malware. Additionally, some email systems may block certain file types for security reasons.
    
3. Transfer Speed
	- Email is not optimized for large file transfers, especially when compared to other file transfer methods like FTP or cloud storage. Uploading and downloading large attachments via email can be time-consuming and may impact email server performance.
    
4. Reliability
	- While email is generally reliable for text-based communication, the reliability of file transfer via email can vary. Delivery failures, file corruption, or incomplete downloads can occur due to network issues or email server limitations.
    
5. Security
	- Email attachments are typically not encrypted by default, which means the contents of the attachment could potentially be intercepted or accessed by unauthorized individuals. For sensitive or confidential files, additional encryption methods or secure file transfer options should be considered.

### Cloud-based file transfer options, their similarities, and differences.

- Cloud-based file transfer refers to the process of transferring files over the internet using cloud storage services. It offers several advantages, such as easy accessibility, scalability, and collaboration. Here are some common cloud-based file transfer options, along with their similarities and differences:

- File Hosting Services: File hosting services, such as Dropbox, Google Drive, and OneDrive, allow users to upload and store files in the cloud. These services provide features for sharing files with others, syncing files across devices, and accessing files from anywhere with an internet connection.

- File Transfer Protocols (FTP/SFTP): FTP (File Transfer Protocol) and SFTP (Secure File Transfer Protocol) are standard protocols for transferring files over a network. Cloud-based FTP/SFTP services, like FileZilla and WinSCP, provide a convenient way to transfer files to and from cloud servers.

- Online Collaboration Platforms: Online collaboration platforms, such as Google classroom and Google Workspace (formerly G Suite), provide file storage, sharing, and collaboration features. Users can create, edit, and collaborate on files in real-time, ensuring seamless teamwork. These platforms often integrate other productivity tools like document editing, project management, and communication features.

### Sharing files for read-only or editing purposes

- refers to the ability to share files with others while specifying whether they have only read access or can also make edits to the files. When sharing files, you can choose to grant different levels of permissions to recipients, allowing them either to view and read the files without making any changes or to edit and modify the files as needed.

---
### The concept, structure, and components of a URL.

- URL stands for Uniform Resource Locator. It is a standard format used to specify the address or location of a resource on the internet, such as a web page, image, video, or document. The URL provides a way to identify and access resources on the World Wide Web.

- The structure of a URL typically consists of several parts:

	1. Protocol
		- It indicates the communication protocol to be used when accessing the resource. Common protocols include HTTP (Hypertext Transfer Protocol), HTTPS (HTTP Secure), FTP (File Transfer Protocol), and others.
    
	2. Domain
		- Also known as the hostname or web address, it identifies the specific website or server where the resource is hosted. For example, in "[https://www.example.com](https://www.example.com)," the domain is "[www.example.com](http://www.example.com)."
    
	3. Path 
		- It represents the specific location or directory on the server where the resource is located. It helps identify the file or page within the website's structure. For example, in "[https://www.example.com/blog/article.html](https://www.example.com/blog/article.html)," the path is "/blog/article.html."
    
	4. Query Parameters
		- They are additional information appended to the URL that provides specific instructions or data to the server. Query parameters are preceded by a question mark "?" and separated by ampersands "&." They are commonly used in dynamic web pages to pass parameters to scripts or applications.
    
	5. Fragment Identifier
		- It refers to a specific section or anchor within a web page. The fragment identifier is indicated by a hash "#" followed by the section's identifier. It is used to navigate to a specific part of a long web page.
		
---
### The structure of a web address.

- A web address, also known as a URL (Uniform Resource Locator), has a specific structure that identifies the location of a resource on the World Wide Web. The components of a web address include:

1. Protocol
	- It specifies the communication protocol used to access the resource, such as HTTP or HTTPS.
    
2. Domain
	- This is the main part of the web address and represents the website's name or address. It typically starts with "www" followed by the domain name, such as "example.com".
    
3. Subdomain
	- In some cases, a web address may include a subdomain, which is an additional prefix before the main domain. For example, "blog.example.com" has the subdomain "blog" in addition to the domain "example.com".
    
4. Top-Level Domain (TLD)
	- It is the last part of the domain and represents the type or category of the website. Common TLDs include ".com", ".org", ".net", and country-specific TLDs like ".uk" or ".fr".
    
5. Path
	- The path refers to the specific location or directory within the website where the resource is located. It helps identify the page or file within the website's structure. For example, "/products" or "/blog/article".
    
6. Query Parameters
	- If applicable, query parameters can be included after the path. They provide additional information to the server and are separated by the "?" symbol. Query parameters are commonly used in dynamic web pages to pass data or parameters to scripts or applications.
    
7. Fragment Identifier
	- It is an optional component indicated by the "#" symbol, followed by a specific section or anchor within a web page. The fragment identifier helps navigate to a specific part of a page.
	
### Browser error messages

- 304 Not Modified
	- no change, loaded from cache (nothing to do)
	
- 400 Bad Request 
	- incorrect request (return, retry differently)
	
- 401 Unauthorized
	- no identification
	- unavailable (reload)
	
- 403 Forbidden
	- no access rights (identify as authorized, reload)
	
- 404 Not Found 
	- requested material not found (check url, retry)
	
- 500 Internal Server Error
	- server error (reload)
	
- 501 Not Implemented 
	- the requested function is not available (reload)
	
- 502 Bad Gateway
	- incorrect gateway/proxy data (reload)
	
- 503 Server Unavailable 
	- server not available (reload later)
	
---
### Searching on the internet, search engines
- the internet is a sequence of connected computers, and there are way too many websites
- searching is needed for us to find the correct information
	- search engines help us achieve that by ranking these websites by different filters like searches, how many users use these websites, and today even by taking money from websites to rank them higher.
		- search engine examples
			- Google, Yahoo, Bing, Yandex, etc.

##### Searching strategies
- search engines use databases (titles, keywords, description, sitemap)
	- they monitor the web, find new websites
- thematic search
	- smaller data sets are more appropriate
		- by geographical location 
		- by multimedia type 
		- by document type
		- by specialization
	- not the most accurate system if we are looking for something specific
- keyword search
	- bigger data sets are more appropriate
		- we search with specific keywords and/or phrases
		- more accurate phrase -> more accurate result
	- clarifier characters can be used
		- "", accurate expression
		- +, must include
		- -, must NOT include
		- `*`, character replacement
		- ~, synonym
		- logical connections
			- AND, OR, NOT, NEAR