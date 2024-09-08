# Proxmox Network Configuration Guide

This guide covers the steps to configure network settings in Proxmox using either DHCP or a static IP address.
- ## DHCP Configuration
- ### 1. Identify Your Network Interface
- Default network interface in Proxmox is often named `ens18`.
- Run `ip a` to check available network interfaces.
  
    ```bash
    ip a
    ```
- ### 2. Edit Network Configuration
- Open the network configuration file:
  
    ```bash
    sudo nano /etc/netplan/01-netcfg.yml
    ```
- Update the file with the following YAML configuration:
  
    ```yaml
    network:
      version: 2
      ethernets:
        ens18:
          dhcp4: true
    ```
	- Ensure correct indentation and specify your network interface (e.g., `ens18`).
	- Set `dhcp4` to `true` to enable DHCP.
- ### 3. Save and Apply Configuration
- Save the changes (Ctrl + X, Y, Enter).
- Apply the configuration:
  
    ```bash
    sudo netplan apply
    ```
- ## Static IP Configuration
- ### 1. Identify Your Network Interface
- Typically `ens18` in Proxmox.
- Confirm by running `ip a`.
  
    ```bash
    ip a
    ```
- ### 2. Edit Network Configuration
- Open the configuration file:
  
    ```bash
    sudo nano /etc/netplan/01-netcfg.yml
    ```
- Configure a static IP address:
  
    ```yaml
    network:
      version: 2
      renderer: networkd
      ethernets:
        ens18:
          dhcp4: no
          addresses:
            - 172.16.16.16/16   # Desired static IP and subnet
          gateway4: 172.16.0.1   # Actual gateway address
          nameservers:
            addresses:
              - 172.16.0.1       # DNS server(s)
              - 8.8.8.8           # DNS server(s)
    ```
	- Correctly indent and specify your network interface (`ens18`).
	- Replace IP and DNS addresses as necessary.
- ### 3. Save and Apply Configuration
- Save the changes (Ctrl + X, Y, Enter).
- Apply the static IP configuration:
  
    ```bash
    sudo netplan apply
    ```
- ## Explanation
- ### DHCP Configuration Process
  
  1. **Identify Network Interface**: Usually `ens18`.
  2. **Open Network Configuration**: Edit with `nano`.
  3. **Edit Configuration File**: Modify to enable DHCP.
  4. **Save and Apply**: Use Ctrl + X, Y, Enter, then `sudo netplan apply`.
- ### Static IP Configuration Process
  
  1. **Identify Network Interface**: Typically `ens18`.
  2. **Open Network Configuration**: Edit with `nano`.
  3. **Edit Configuration File**: Set up a static IP.
  4. **Save and Apply**: Save and run `sudo netplan apply`.