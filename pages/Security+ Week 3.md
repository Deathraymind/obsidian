- #Security+
- # Video 3.1.1 Cloud Infrastructure
	- ### Cloud responsibility matrix #card
	  background-color:: yellow
		- shows whos is responsible for security
		- ![image.png](../assets/image_1737435325630_0.png)
	- ### Hybrid consideration #card
	  background-color:: green
		- more than one public or private cloud
	- ### Vendor risk management policy #card
	  background-color:: blue
		- assess the security of your cloud providers
	- ### Infrastructure as code
	  background-color:: pink
		- define servers network and applications as code
		- ![image.png](../assets/image_1737435643861_0.png){:height 179, :width 180}
	- ### FaaS #card
	  background-color:: pink
		- function as a service
		- remove the operating system from the equation
		- applications are separated into individual autonomous functions
	- ### Monolithic applications
	  background-color:: red
		- one big app does everything
	- ### APIs and micro services #card
	  background-color:: pink
		- application programming interfaces
		- is the glue for the microservices
		- more resilient
		- ![image.png](../assets/image_1737435926909_0.png){:height 379, :width 381}
- # Video 3.1.2 Network Infrastructure Concepts
	- ### SDN #card
	  background-color:: red
		- software defined networking
		- network devices have different functional planes like data control and management planes
		- perfect for cloud
		- ### Infastructure Layer / Data Plane #card
		  background-color:: green
			- The data on the lines
			- process the network frames and packets
			- forwarding trunking encryption and NAT
		- ### Control Layer / Control plane #card
		  background-color:: blue
			- telling the data where to go
			- manage the actions of the data plane
			- routing tables sessions tables nat tables
		- ### Application Layer #card
		  background-color:: purple
			- configure and manage the device
			- ssh browser api
		- ![image.png](../assets/image_1737436450815_0.png){:height 151, :width 405}
- # Video 3.1.3 Other Infrastructure Concepts
	- ### Containerization #card
	  background-color:: red
		- containes everything you need to run an applciation
		- code and dependcies
		- everything but the OS
		- ![image.png](../assets/image_1737436886966_0.png){:height 323, :width 292}
	- ### SCADA / ICS #card
	  background-color:: pink
		- Supervisory control and data acquisition system
		- Industrial Control System (ICS)
		- Monitor equipment from central panel
		- Completely segmented from outside
	- ### RTOS Real-Time Operating Systems #card
	  background-color:: green
		- A process takes priority
		- military environments and automobiles need priority
		- need to always be available
	- # Video 3.1.4 Infrastructure Considerations
		- ### MTTR #card
		  background-color:: red
			- Mean Time to Repair
		- ### Risk transference #card
		  background-color:: yellow
			- transfer the risk to a third-part
			- cyber security insurance
	- ---
- # Video 3.2.1 Secure Infrastructures
	- ### Firewalls #card
	  background-color:: red
		- segment the network from outside
		- also can use honeypots jump server sensros and load blancer
	- ### Security-Zone #card
	  background-color:: pink
		- Logically segment a network based on the functions of the devices
		- IOT would be on a seperate vlan
		- Simplifies security
- # Video 3.2.2 Intrusion Prevention
	- ### IPS #card
	  background-color:: red
		- Intrusion prevention system
		- watch the network traffic
	- ### IDS #card
	  background-color:: pink
		- Intrusions detection system
	- ### Fail-open #card
	  background-color:: green
		- when it crashes data will continue to flow without security
	- ### Fail-closed #card
	  background-color:: blue
		- security and network connection will be severed
	- ### Passive monitoring #card
	  background-color:: green
		- copies of data are sent to the IPS kind of a IDS since it cant block traffic real time
		- uses port mirror/ SPAN or network tap
		- ![image.png](../assets/image_1737441032553_0.png){:height 286, :width 398}
	- ### Active Monitoring #card
	  background-color:: blue
		- ![image.png](../assets/image_1737441011068_0.png){:height 141, :width 407}
		-
- # Video 3.2.3 Network Appliances
	- ### Jump Server #card
	  background-color:: yellow
		- A server that is accsessible from outside of the network limited to very few admins
		- hardened
		- ![image.png](../assets/image_1737441174700_0.png)
	- ### Proxy Server #card
	  background-color:: pink
		- sits between the users
		- useful for caching, URL filtering, content scanning
		- NAT is a proxy
		- nginx is a application proxy
	- ### Explicit Proxy #card
	  background-color:: red
		- You have to tell the OS or browser to go through the proxy
	- ### Transparent Proxy #card
	  background-color:: blue
		- invisible to the user
	- ### Forward Proxy #card
	  background-color:: purple
		- an internal proxy
		- managing data exiting a network
	- ### Reverse Proxy #card
	  background-color:: green
		- inbound traffic from the internet to youre network
		- nginx proxy on my network
	- ### Open Proxy #card
	  background-color:: blue
		- third party proxy available to anyone to use
		- third party can see your data and inject data
	- ### Active/active load balencing #card
	  background-color:: green
		- all servers are active and being used by the load balencer
		- tcp offload
		- ssl encryption can be done by load balance
		- can cache
		- QoS prioritization
	- ### Active/passive load balancing #card
	  background-color:: red
		- some servers are being active and others are on standby
	- ### SIEM #card
	  background-color:: purple
		- Security information event manager
		- collects logs from many different sensors on the network
- # Video 3.2.4 Port Security
	- Lock down yo ports
	- ### EAP
	  background-color:: red
		- Extensible Authentication Protocol
		- 802.1x prevent access to the network until the authentication succeeds
	- ### 802.1x
	  background-color:: green
		- NAC or port-based network access control EAP works with 802.1x
		- used with RADIUS LDAP TACACS+ Kerberos etc
- # Video 3.2.5 Firewall Types
	- ### Network Based Firewalls #card
	  background-color:: red
		- OSI layer 4 or newer ones can do 7
		- VPN
		- Can act as Layer 3
		- NAT
	- ### UTM #card
	  background-color:: blue
		- Unified Thray Managment Device
		- Web Security gateway
		- URL Filtering/content inspection
		- block malware
		- filter spam
		- CSU/DSU
		- Rout and switching
		- Firewall
		- IPS/IDS
		- VPN
		- Layer 4 lower performance
	- ### NGFW #card
	  background-color:: green
		- Next Gen firewall
		- OSI 7
		- look at all data on network get all the details
		- can read twitter but not post
		- doesn't look just at the port but the actual application
		- opnsense + zenarmor
	- ### WAF
	  background-color:: pink
		- web application firewall
		- works with http/https
		- allow and deny based on expected input
		- can see sql injection
- # Video 3.2.6 Secure Communication                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
  
  ---
- # Video 3.3.1 Data Types and Classifications
	- ### Regulated Data #card
	  background-color:: yellow
		- managed by third party
		- credit card stuff
		- trade secrets for organization
		- intellectual data such as trademarks and patents
	- ### Legal information #card
	  background-color:: red
		- court records documents attory information is public
		- but PII is secret
	- ### PHI #card
	  background-color:: green
		- protected health information
		- health status health care records
- # Video 3.3.2 States of Data
	- ### GDPR #card
	  background-color:: yellow
		- General Data Protection Regulation
		- European data laws any data collected from Europeans must be held in the EU
	- ### Data Sovereignty #card
	  background-color:: green
		- data that resides in a country has to follow its regulations
- # Video 3.3.3 Protecting Data
  
  ---
- # Video 3.4.1 Resiliency
- # Video 3.4.2 Capacity Planning
- # Video 3.4.3 Recovery Testing
- # Video 3.4.4 Backups
- # Video 3.4.5 Power Resiliency