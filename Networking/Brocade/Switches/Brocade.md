## Documentation: Configuring VLANs on a Switch
- ### Objective: #switch #brocade
  This documentation outlines the steps to configure VLANs on a network switch, specifically tagging and untagging ports for VLAN 10.
- ### Prerequisites:
- Access to the switch's command line interface (CLI) or management interface.
- Basic understanding of VLANs and switch configuration.
- ### Procedure:
  
  1. **Access Configuration Mode:**
	- Enter configuration mode on the switch by typing:
	  ```
	  Conf t
	  ```
	  
	  2. **Create VLAN 10:**
	- Create VLAN 10 by typing:
	  ```
	  Vlan 10
	  ```
	  
	  3. **Tag Port Connecting to pfSense:**
	- Tag VLANs to the port connecting to the pfSense firewall. For example, if the port is `1/1/1`, tag VLAN 10 to it:
	  ```
	  Tagg e 1/1/1
	  ```
	  
	  4. **Untag Interface for VLAN 10 Device:**
	- Untag the interface where your VLAN 10 device is connected. For example, if the port is `1/1/8`, untag VLAN 10 from it:
	  ```
	  Vlan 10
	  Untagg e 1/1/8
	  ```
	  
	  5. **Verify Configuration:**
	- To confirm that the configuration changes have taken effect, use the `show vlan` command:
	  ```
	  show vlan
	  ```
- ### Expected Output:
  The `show vlan` command should display VLAN information, including the ports tagged and untagged for VLAN 10. Verify that port `1/1/1` is tagged for VLAN 10, and port `1/1/8` is untagged for VLAN 10.
- ### Conclusion:
  By following the outlined steps, you have successfully configured VLAN 10 on the network switch. The port connecting to the pfSense firewall is tagged for VLAN 10, while the interface where the VLAN 10 device is connected is untagged, allowing for proper network segmentation and traffic isolation.
  
  **Note:** Ensure to save the configuration changes appropriately to make them persistent across reboots, typically by issuing a `write memory` or `copy running-config startup-config` command, depending on your switch's syntax.