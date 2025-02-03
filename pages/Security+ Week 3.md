- #Security+
- # Video 3.1.1 Cloud Infrastructure
	- ### Cloud responsibility matrix #card
	  background-color:: yellow
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:48:09.580Z
	  card-last-reviewed:: 2025-01-25T06:48:09.580Z
	  card-last-score:: 5
		- shows whos is responsible for security
		- ![image.png](../assets/image_1737435325630_0.png)
	- ### Hybrid consideration #card
	  background-color:: green
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T07:02:45.915Z
	  card-last-score:: 1
		- more than one public or private cloud
	- ### Vendor risk management policy #card
	  background-color:: blue
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:57:32.596Z
	  card-last-reviewed:: 2025-01-25T06:57:32.597Z
	  card-last-score:: 5
		- assess the security of your cloud providers
	- ### Infrastructure as code
	  background-color:: pink
		- define servers network and applications as code
		- ![image.png](../assets/image_1737435643861_0.png){:height 179, :width 180}
	- ### FaaS #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:53:57.878Z
	  card-last-reviewed:: 2025-01-25T06:53:57.879Z
	  card-last-score:: 5
		- function as a service
		- remove the operating system from the equation
		- applications are separated into individual autonomous functions
	- ### Monolithic applications
	  background-color:: red
		- one big app does everything
	- ### APIs and micro services #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:58:58.739Z
	  card-last-reviewed:: 2025-01-25T06:58:58.739Z
	  card-last-score:: 5
		- application programming interfaces
		- is the glue for the microservices
		- more resilient
		- ![image.png](../assets/image_1737435926909_0.png){:height 379, :width 381}
- # Video 3.1.2 Network Infrastructure Concepts
	- ### SDN #card
	  background-color:: red
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T07:03:54.782Z
	  card-last-score:: 1
		- software defined networking
		- network devices have different functional planes like data control and management planes
		- perfect for cloud
		- ### Infastructure Layer / Data Plane #card
		  background-color:: green
		  card-last-interval:: -1
		  card-repeats:: 1
		  card-ease-factor:: 2.5
		  card-next-schedule:: 2025-01-25T15:00:00.000Z
		  card-last-reviewed:: 2025-01-25T06:53:15.751Z
		  card-last-score:: 1
			- The data on the lines
			- process the network frames and packets
			- forwarding trunking encryption and NAT
		- ### Control Layer / Control plane #card
		  background-color:: blue
		  card-last-interval:: 13.8
		  card-repeats:: 1
		  card-ease-factor:: 2.6
		  card-next-schedule:: 2025-02-08T01:54:54.222Z
		  card-last-reviewed:: 2025-01-25T06:54:54.223Z
		  card-last-score:: 5
			- telling the data where to go
			- manage the actions of the data plane
			- routing tables sessions tables nat tables
		- ### Application Layer #card
		  background-color:: purple
		  card-last-interval:: 13.8
		  card-repeats:: 1
		  card-ease-factor:: 2.6
		  card-next-schedule:: 2025-02-08T02:03:30.734Z
		  card-last-reviewed:: 2025-01-25T07:03:30.738Z
		  card-last-score:: 5
			- configure and manage the device
			- ssh browser api
		- ![image.png](../assets/image_1737436450815_0.png){:height 151, :width 405}
- # Video 3.1.3 Other Infrastructure Concepts
	- ### Containerization #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:59:30.340Z
	  card-last-reviewed:: 2025-01-25T06:59:30.341Z
	  card-last-score:: 5
		- containes everything you need to run an applciation
		- code and dependcies
		- everything but the OS
		- ![image.png](../assets/image_1737436886966_0.png){:height 323, :width 292}
	- ### SCADA / ICS #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:53:36.130Z
	  card-last-reviewed:: 2025-01-25T06:53:36.131Z
	  card-last-score:: 5
		- Supervisory control and data acquisition system
		- Industrial Control System (ICS)
		- Monitor equipment from central panel
		- Completely segmented from outside
	- ### RTOS Real-Time Operating Systems #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:48:15.011Z
	  card-last-reviewed:: 2025-01-25T06:48:15.011Z
	  card-last-score:: 5
		- A process takes priority
		- military environments and automobiles need priority
		- need to always be available
	- # Video 3.1.4 Infrastructure Considerations
		- ### MTTR #card
		  background-color:: red
		  card-last-interval:: -1
		  card-repeats:: 1
		  card-ease-factor:: 2.5
		  card-next-schedule:: 2025-01-25T15:00:00.000Z
		  card-last-reviewed:: 2025-01-25T07:02:31.160Z
		  card-last-score:: 1
			- Mean Time to Repair
		- ### Risk transference #card
		  background-color:: yellow
		  card-last-interval:: 13.8
		  card-repeats:: 1
		  card-ease-factor:: 2.6
		  card-next-schedule:: 2025-02-08T01:56:36.548Z
		  card-last-reviewed:: 2025-01-25T06:56:36.549Z
		  card-last-score:: 5
			- transfer the risk to a third-part
			- cyber security insurance
	- ---
- # Video 3.2.1 Secure Infrastructures
	- ### Firewalls #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:48:46.789Z
	  card-last-reviewed:: 2025-01-25T06:48:46.790Z
	  card-last-score:: 5
		- segment the network from outside
		- also can use honeypots jump server sensros and load blancer
	- ### Security-Zone #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:55:39.441Z
	  card-last-reviewed:: 2025-01-25T06:55:39.442Z
	  card-last-score:: 5
		- Logically segment a network based on the functions of the devices
		- IOT would be on a seperate vlan
		- Simplifies security
- # Video 3.2.2 Intrusion Prevention
	- ### IPS #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:52:37.569Z
	  card-last-reviewed:: 2025-01-25T06:52:37.570Z
	  card-last-score:: 5
		- Intrusion prevention system
		- watch the network traffic
	- ### IDS #card
	  background-color:: pink
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:54:20.110Z
	  card-last-score:: 1
		- Intrusions detection system
	- ### Fail-open #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:57:58.906Z
	  card-last-reviewed:: 2025-01-25T06:57:58.907Z
	  card-last-score:: 5
		- when it crashes data will continue to flow without security
	- ### Fail-closed #card
	  background-color:: blue
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:55:18.573Z
	  card-last-score:: 1
		- security and network connection will be severed
	- ### Passive monitoring #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:54:34.777Z
	  card-last-reviewed:: 2025-01-25T06:54:34.778Z
	  card-last-score:: 5
		- copies of data are sent to the IPS kind of a IDS since it cant block traffic real time
		- uses port mirror/ SPAN or network tap
		- ![image.png](../assets/image_1737441032553_0.png){:height 286, :width 398}
	- ### Active Monitoring #card
	  background-color:: blue
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T07:02:22.756Z
	  card-last-score:: 1
		- ![image.png](../assets/image_1737441011068_0.png){:height 141, :width 407}
		-
- # Video 3.2.3 Network Appliances
	- ### Jump Server #card
	  background-color:: yellow
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:58:19.030Z
	  card-last-reviewed:: 2025-01-25T06:58:19.030Z
	  card-last-score:: 5
		- A server that is accsessible from outside of the network limited to very few admins
		- hardened
		- ![image.png](../assets/image_1737441174700_0.png)
	- ### Proxy Server #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T02:03:05.135Z
	  card-last-reviewed:: 2025-01-25T07:03:05.136Z
	  card-last-score:: 5
		- sits between the users
		- useful for caching, URL filtering, content scanning
		- NAT is a proxy
		- nginx is a application proxy
	- ### Explicit Proxy #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:56:26.039Z
	  card-last-reviewed:: 2025-01-25T06:56:26.040Z
	  card-last-score:: 5
		- You have to tell the OS or browser to go through the proxy
	- ### Transparent Proxy #card
	  background-color:: blue
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:48:39.026Z
	  card-last-reviewed:: 2025-01-25T06:48:39.026Z
	  card-last-score:: 5
		- invisible to the user
	- ### Forward Proxy #card
	  background-color:: purple
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:55:51.128Z
	  card-last-reviewed:: 2025-01-25T06:55:51.129Z
	  card-last-score:: 5
		- an internal proxy
		- managing data exiting a network
	- ### Reverse Proxy #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:53:44.684Z
	  card-last-reviewed:: 2025-01-25T06:53:44.685Z
	  card-last-score:: 5
		- inbound traffic from the internet to youre network
		- nginx proxy on my network
	- ### Open Proxy #card
	  background-color:: blue
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:55:28.282Z
	  card-last-reviewed:: 2025-01-25T06:55:28.283Z
	  card-last-score:: 5
		- third party proxy available to anyone to use
		- third party can see your data and inject data
	- ### Active/active load balencing #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T02:02:36.382Z
	  card-last-reviewed:: 2025-01-25T07:02:36.383Z
	  card-last-score:: 5
		- all servers are active and being used by the load balencer
		- tcp offload
		- ssl encryption can be done by load balance
		- can cache
		- QoS prioritization
	- ### Active/passive load balancing #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:58:35.307Z
	  card-last-reviewed:: 2025-01-25T06:58:35.308Z
	  card-last-score:: 5
		- some servers are being active and others are on standby
	- ### SIEM #card
	  background-color:: purple
	  card-last-interval:: 1.36
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2025-01-26T14:56:02.436Z
	  card-last-reviewed:: 2025-01-25T06:56:02.436Z
	  card-last-score:: 3
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
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:59:16.522Z
	  card-last-reviewed:: 2025-01-25T06:59:16.523Z
	  card-last-score:: 5
		- OSI layer 4 or newer ones can do 7
		- VPN
		- Can act as Layer 3
		- NAT
	- ### UTM #card
	  background-color:: blue
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:47:52.177Z
	  card-last-score:: 1
		- Unified Threat Management Device
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
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:52:30.500Z
	  card-last-reviewed:: 2025-01-25T06:52:30.501Z
	  card-last-score:: 5
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
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:54:26.864Z
	  card-last-reviewed:: 2025-01-25T06:54:26.865Z
	  card-last-score:: 5
		- managed by third party
		- credit card stuff
		- trade secrets for organization
		- intellectual data such as trademarks and patents
	- ### Legal information #card
	  background-color:: red
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:47:16.814Z
	  card-last-score:: 1
		- court records documents attory information is public
		- but PII is secret
	- ### PHI #card
	  background-color:: green
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:54:06.662Z
	  card-last-score:: 1
		- protected health information
		- health status health care records
- # Video 3.3.2 States of Data
	- ### GDPR #card
	  background-color:: yellow
	  card-last-interval:: 1.36
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2025-01-26T15:03:17.281Z
	  card-last-reviewed:: 2025-01-25T07:03:17.281Z
	  card-last-score:: 3
		- General Data Protection Regulation
		- European data laws any data collected from Europeans must be held in the EU
	- ### Data Sovereignty #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:52:32.585Z
	  card-last-reviewed:: 2025-01-25T06:52:32.586Z
	  card-last-score:: 5
		- data that resides in a country has to follow its regulations
- # Video 3.3.3 Protecting Data
	- ### network location  mobile #card
	  background-color:: red
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:52:48.757Z
	  card-last-score:: 1
		- identify based on ip subnet
		- GPS
		- 802.11
		- Ip addresses, not accurate
	- ### Geo Fencing
	  background-color:: yellow
		- locking data based on where the user is
		- if a dude is in the building he can access the data if hes at home he cant
- ---
- # Video 3.4.1 Resiliency
	- ### HA #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:57:42.653Z
	  card-last-reviewed:: 2025-01-25T06:57:42.654Z
	  card-last-score:: 5
		- High Availability
		- system running in parallel for if the main one fails
		- $$$
	- ### Server Clustering #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:59:07.727Z
	  card-last-reviewed:: 2025-01-25T06:59:07.728Z
	  card-last-score:: 5
		- combine two or more servers
		- scalable
		- usually within the OS
		- ![image.png](../assets/image_1737455763879_0.png){:height 239, :width 323}
	- ### Site resiliency #card
	  background-color:: blue
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:48:31.150Z
	  card-last-score:: 1
		- where a whole network is off site when the main one fails
	- ### Hot site #card
	  background-color:: green
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T02:02:51.919Z
	  card-last-reviewed:: 2025-01-25T07:02:51.920Z
	  card-last-score:: 5
		- a data center where are the data is duplicated
	- ### Cold Site #card
	  background-color:: blue
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:58:04.234Z
	  card-last-reviewed:: 2025-01-25T06:58:04.234Z
	  card-last-score:: 5
		- Empty Building
		- bring all data and equipment and people to run the site
	- ### Warm Site #card
	  background-color:: purple
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2025-01-25T15:00:00.000Z
	  card-last-reviewed:: 2025-01-25T06:52:56.950Z
	  card-last-score:: 1
		- some equipment is on site
	- ### Geographic dispersion #card
	  background-color:: red
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T02:03:34.731Z
	  card-last-reviewed:: 2025-01-25T07:03:34.732Z
	  card-last-score:: 5
		- these sites should be physically different than the organizations primary location
	- ### Platform Diversity #card
	  background-color:: pink
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:56:15.705Z
	  card-last-reviewed:: 2025-01-25T06:56:15.706Z
	  card-last-score:: 5
		- keep systems diverse in case one OS has a vulnerability
	- ### COOP #card
	  background-color:: blue
	  card-last-interval:: 13.8
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2025-02-08T01:52:21.859Z
	  card-last-reviewed:: 2025-01-25T06:52:21.860Z
	  card-last-score:: 5
		- Continuity of operation planning
		- in case tech fails how do  we do things manually or differently
- # Video 3.4.2 Capacity Planning
	- Try to predict supply and demand
- # Video 3.4.3 Recovery Testing
	- Fake a scenerio
	- follow procedures and recover
	- revise and improve
- ### Tabletop exercise #card
  background-color:: yellow
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2025-01-25T15:00:00.000Z
  card-last-reviewed:: 2025-01-25T06:47:27.584Z
  card-last-score:: 1
	- Virtually testing a recovery system
- # Video 3.4.4 Backups
- # Video 3.4.5 Power Resiliency