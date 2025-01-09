# Video 2.1.1 Threat Actors #Security+
	- ### Threat Actor #card
	  background-color:: yellow
		- A person that have an effect on safety
		- Atributes
			- Internal
			- External
			- Resources/Funding
			- Level of sophistication
	- ### Nation State #card
	  background-color:: red
		- external entity
		- goverment
		- Motives
			- data exfiltration
			- philosophical
			- revenge
			- disruption
			- war
		- APT
		- High Sophistication
			- they work with a government
	- ### APT #card
	  background-color:: pink
		- Advanced Persistent Threat
			- They don't really know what they are doing
			- Motives
				- disruption
				- data
				- something philosophical
			- internal or external
			- limited resources
	- ### Hacktivist #card
	  background-color:: green
		- a hacker with a purpose
		- external
		- sophisticated
		- Motives
			- DoS
			- website defacing
			- private document
	- ### Insider threat #card
	  background-color:: blue
		- motivated by revenge and finacial gain
		- using the orginizations resources against themselves
		- internal
	- ### Organized crime #card
	  background-color:: purple
		- profesional criminals
		- motivated by money
		- very soophisticated
		- Organized/ multiple people with their own job
		- lots of funding
	- ### Shadow IT #card
	  background-color:: pink
		- working arounf the inernal it orginization builds their own infastructure
		- they put own roadblocks
		- limited budget
		- medium sophistication
- # Video 2.2.1 Common Threat Vectors
	- ### Message based vectors #card
	  background-color:: yellow
		- vulnerability in email
		- malicious links
		- Phishing attacks
		- SMS
	- ### Image-based vectors #card
	  background-color:: red
		- SVG  Scaleable vector graphic
			- it can contain code that gets executed by youre browser
			- HTML Injection through xml from a svg
	- ### File Based vectors #card
	  background-color:: green
		- PDF
			- a file containing other objects
		- ZIP/RAR
			- contains many files within it
		- Microsoft office
			- documents with macros
			- add-in files
	- ### Vishing based vectors #card
	  background-color:: pink
		- phishing over the phone to get personal information over phone
	- ### Removable device based vectors #card
	  background-color:: green
		- get arond the firewall
		- is malicious software on a usb software
		- usb drives can act as a keyboard
	- ### Vulnerable software vectores #card
	  background-color:: blue
		- infected executable
		- known or unknown vulnerabilities in software
		- agent-less apps stuff from a browser or central server
	- ### Unsupported system vectors #card
	  background-color:: green
		- pathcing device is no longer a option
		- stuck on old cruddy software with vulnerabilities
		- IT might not know the device exists
	- ### Insecure network vectors #card
	  background-color:: blue
		- wireless, use WPA3
		- unsecure interfaces
			- 802.1x to lock down ports
		- Bluetooth
	- ### Open services ports #card
	  background-color:: red
		- most network based attacks
		- every open port is a vulnerability
		- keep firewall rules tight
	- ### Default Credentials
	  background-color:: red
	- ### Supply Chain Vectors #card
	  background-color:: purple
		- Tamper with underlying infrastructure
		- MSPs
		- Vulnerability in a Cisco device
	- ### MSP #card
	  background-color:: blue
		- Managed service providers
		- access different costumers networks from a central location
- # Video 2.2.2 Phishing
	-
- # Video 2.2.3 Impersonation
	- ### Impersonation #card
	  background-color:: red
		- bad spelling, too good of a deal, out of no where.
		- They can use personal information to get some sort of trust
- # Video 2.2.4 Watering Hole Attacks
	- ### Watering hole attack #card
	  background-color:: pink
		- A attacker will poison the source where people will come to
		- infect a website that the users use with any type of attack including social networking
		- **You can prevent this by having a IPS monitor traffic that the firewall let in**
- # Video 2.2.5 Other types of social engineering attacks
	- ### Misinformation/disinformation #card
	  background-color:: red
		- create confusion and division
		- influence campaigns #card
			- sway public opinions
			- social media and advertising
		- Nation state actors #card
			- divide distract and persuade
		- Brand Impersonation
- # Video 2.3.1 Memory Injections
	- ### Memory injection #card
	  background-color:: yellow
		- add code into memory
		- hide malware in process
			- gives the malware the same permission as the process it hides in
		- DLL is a windows process
	- ### DLL #card
	  background-color:: red
		- Dynamic Link Library\
- # Video 2.3.2 Buffer Overflows
	- ### Buffer overflow attack #card
	  background-color:: red
		- overwriting a buffer of memory spills into other parts of a applications memoery
		- not simple
		- Sometimes does nothing
		- ![image.png](../assets/image_1736386862936_0.png)
- # Video 2.3.3 Race Conditions
	- ### Race Conditions #card
	  background-color:: green
		- When something happens at the same time and the program may not know it
	- ### TOCTOU #card
	  background-color:: red
		- Time of use attack
		- something that happens in between storing and running information
		- Its a race condition
		- ![image.png](../assets/image_1736387266558_0.png){:height 231, :width 466}
- # Video 2.3.4 Malicious Updates
	- ### Best Practive when updating #card
	  background-color:: pink
		- Keep backup
		- verify source
		- make sure their are no bugs or new vulnerabilities
- # Video 2.3.5 Operating Systems
	- An operating system is a common place to look for vulnerabilities as they are very complex #card
	  background-color:: pink
		- They get patched frequently
- # Video 2.3.6 SQL Injection
	- ### SQL Injection #card
	  background-color:: red
		- a common version of code injection where code is put into a database and the code will end up running it when it was just supposed to be something like a username.
		- ![image.png](../assets/image_1736388549108_0.png)
		- Instead of getting a simple username you get every username
- # Video 2.3.7 Cross Site Scripting
	- ### XSS #card
	  background-color:: yellow
		- Cross-site scripting
		- Originally called cross-site because of browser security flaws
		- one of the most common web based vulnerabilities
	- ### Non-persistant/reflected XSS attack #card
	  background-color:: red
		- search box is a common source
		- attacker runs script that sends credentials/session IDs to the attacker
		- ![image.png](../assets/image_1736400610380_0.png)
	- ### Persistent (Stored) XSS attack #card
	  background-color:: pink
		- attacker posts a malicouse payload to a social network
		- is persistent as everyone gets the payload
		- attacks anyone who visits the site
		- spreads
- # Video 2.3.8 Hardware vulnerabilities
	- ### Hardware devices #card
	  background-color:: yellow
		- dont have a OS or we dont have access to it like IOT
		  :LOGBOOK:
		  CLOCK: [2025-01-09 Thu 14:37:58]
		  :END:
		- Firmware the only people who can manage or update the system are the manufactures
	- ### EOL #card
	  background-color:: blue
		- End of life
		- in the future they will stop selling the device but security patches will be applied
	- ### EOSL #card
	  background-color:: red
		- End of service life
		- end of security patches
- # Video 2.3.9 Virtualization vulnerabilities
	- Quantity of resources between vms
	- complexity adds opportunities to physical machines
	- ### Virtual machine escape #card
	  background-color:: yellow
		- attacker can get into one machine and escape it to get to other vms on the hypervisor
		- you can have great control
	- ### Resource Reuse #card
	  background-color:: pink
		- the hypervisor manages the relationship between the phyiscal and virtual resoureces
		- Ram is shared between the vms on a hypervisor
		- memory areas shared between the vms
- # Video 2.3.1 cloud vulnerabilities
	- Cloud adoption has been nearly universal
	-
-