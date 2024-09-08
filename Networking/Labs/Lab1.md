- ![[Pasted image 20240408081716.png]]
  #gns3
  
  ---
- ### Accessing Router CLI
  1. **Enter Enable Mode**
   ```
   Router> enable
   ```
	- **Description**: Switches to privileged mode, which allows access to all other router commands.
- ### Displaying Interface Information
  1. **Show Interface Details**
   ```
   Router# show interface
   ```
	- **Description**: Displays detailed information about the router's interfaces, including status, protocol state, and more.
	  2. **Show IP Interface Brief**
	  ```
	  Router# show ip interface brief
	  ```
	- **Description**: Provides a summary of the IP addresses on all interfaces, along with their up/down status.
- ### Configuring an Interface
  1. **Enter Global Configuration Mode**
   ```
   Router# configure terminal
   ```
	- **Description**: Enters global configuration mode, allowing changes to the router's configuration.
	  2. **Configure Interface GigabitEthernet1/0**
	  ```
	  Router(config)# interface GigabitEthernet1/0
	  ```
	- **Description**: Selects the GigabitEthernet1/0 interface for configuration.
	  3. **Assign Static IP Address to Interface**
	  ```
	  Router(config-if)# ip address 192.168.1.1 255.255.255.0
	  ```
	- **Description**: Sets a static IP address and subnet mask for the selected interface.
	  4. **Enable Interface**
	  ```
	  Router(config-if)# no shutdown
	  ```
	- **Description**: Activates the interface, changing its status to up.
	  5. **Add Description to Interface (Optional)**
	  ```
	  Router(config-if)# description <Your Description Here>
	  ```
	- **Description**: Adds a descriptive label to the interface, helpful for documentation purposes.
	  6. **Exit Interface Configuration**
	  ```
	  Router(config-if)# exit
	  ```
	- **Description**: Exits from interface configuration mode back to global configuration mode.
- ### Writing Configuration to Memory
  1. **Exit Global Configuration Mode**
   ```
   Router(config)# exit
   ```
	- **Description**: Exits global configuration mode, returning to privileged EXEC mode.
	  2. **Save Configuration**
	  ```
	  Router# write memory
	  ```
	- **Description**: Saves the current configuration to the router's non-volatile memory, ensuring it persists across reboots.
- ### Configuring DHCP Server
  1. **Define DHCP Pool**
   ```
   Router(config)# ip dhcp pool LAN_POOL
   ```
	- **Description**: Creates a DHCP pool named "LAN_POOL" for dynamic IP address allocation.
	  2. **Set Network for DHCP Pool**
	  ```
	  Router(dhcp-config)# network 192.168.1.0 255.255.255.0
	  ```
	- **Description**: Defines the network and subnet mask for the DHCP pool.
	  3. **Set Default Gateway for DHCP Clients**
	  ```
	  Router(dhcp-config)# default-router 192.168.1.1
	  ```
	- **Description**: Specifies the default gateway for DHCP clients, typically the router's IP address.
	  4. **Set DNS Servers for DHCP Clients**
	  ```
	  Router(dhcp-config)# dns-server 8.8.8.8 8.8.4.4
	  ```
	- **Description**: Assigns DNS server addresses for DHCP clients, using Google's public DNS in this case.
	  5. **Exclude IP Addresses from DHCP Pool**
	  ```
	  Router(config)# ip dhcp excluded-address 192.168.1.1
	  Router(config)# ip dhcp excluded-address 192.168.1.10 192.168.1.20
	  ```
	- **Description**: Prevents specific IP addresses from being allocated by DHCP, useful for devices with static IP assignments.
- ### Configuring NAT
  1. **Specify Inside Source for NAT**
   ```
   Router(config)# ip nat inside source list 1 interface GigabitEthernet0/0 overload
   ```
	- **Description**: Enables NAT, allowing multiple devices on the private network to share a single public IP address for Internet access.
	  2. **Define Access List for NAT**
	  ```
	  Router(config)# access-list 1 permit 192.168.1.0 0.0.0.255
	  ```
	- **Description**: Creates an access list to specify which IP addresses are allowed to use NAT, based on the network defined.
- ### Saving Configuration and Verifying DHCP Bindings
  1. **Save Configuration**
   ```
   Router# write memory
   ```
	- **Description**: Saves the current router configuration to prevent loss after a reboot.
	  2. **Show DHCP Bindings**
	  ```
	  Router# show ip dhcp binding
	  ```
	- **Description**: Displays a list of all IP addresses assigned by the DHCP server, including the MAC address of each client.
	  
	  To test the network topology and ensure that everything is configured correctly, follow these steps on PC1:
	  
	  1. **Obtain an IP Address via DHCP**
	  
	  ```
	  DHCP
	  ```
	- On PC1, initiate a DHCP request to automatically obtain an IP address. During this process, a text might appear mentioning "DORA," which stands for Discover, Offer, Request, Acknowledge. This is the process by which a DHCP client obtains an IP address from a DHCP server.
	- **Expected Outcome**: PC1 should receive an IP address within the range of 192.168.1.x.
	  
	  2. **Test Ping to the Router**
	- After obtaining an IP address, test connectivity to the router by pinging its IP address.
	  ```
	  ping 192.168.1.1
	  ```
	- **Expected Outcome**: You should receive replies from 192.168.1.1, indicating successful communication with the router.
	  
	  3. **Test Ping to an External IP Address**
	- Next, test internet connectivity by pinging an external IP address, such as one of Google's public DNS servers.
	  ```
	  ping 8.8.8.8
	  ```
	- **Expected Outcome**: Receiving replies from 8.8.8.8 indicates that you have internet access through the router.
	  
	  4. **Test Ping to a Domain Name**
	- Finally, confirm that DNS resolution is working by pinging a domain name.
	  ```
	  ping google.com
	  ```
	- **Expected Outcome**: If you receive replies, it means DNS resolution is functioning correctly, and you've successfully set up DNS.
	  
	  These steps validate the configuration of the network, from obtaining an IP address via DHCP to ensuring internet access and DNS resolution are operational.