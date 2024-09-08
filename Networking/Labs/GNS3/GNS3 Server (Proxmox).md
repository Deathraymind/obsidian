# Setting Up GNS3 VM on Proxmox via ESXi Image
#gns3 
This documentation provides a step-by-step guide to help you set up the GNS3 VM on a Proxmox server using the ESXi image. The process involves downloading the ESXi-compatible image, transferring it to your Proxmox server, configuring the VM, and accessing it through the Proxmox web interface.
- ## Step 1: Download the ESXi Image
  
  1. Visit the GNS3 download page at [https://www.gns3.com/software/download-vm](https://www.gns3.com/software/download-vm).
  
  2. Select the option for ESXi and download the GNS3 VM OVA file. (We will convert this to qcow for more info on what this means [[ESXi to Proxmox]])
- ## Step 2: Transfer the OVA File to Your Proxmox Server
  
  1. Open a command prompt (Windows) or a Linux terminal.
  
  2. Navigate to the directory where you downloaded the GNS3 VM OVA file. This is usually in the "Downloads" folder.
  
  3. Use the `scp` command to securely copy the OVA file to your Proxmox server. Replace `<your_proxmox_ip>` with the IP address of your Proxmox server:
  
   ```bash
   scp './GNS3 VM.ova' user@<your_proxmox_ip>:/tmp
   ```
- ## Step 3: Access Your Proxmox Server
  
  1. Open an SSH session to your Proxmox server. Replace `<your_proxmox_ip>` with the IP address of your Proxmox server:
  
   ```bash
   ssh user@<your_proxmox_ip>
   ```
  
  2. Change the directory to `/tmp`:
  
   ```bash
   cd /tmp
   ```
  
  3. Extract the contents of the OVA file using the `tar` command:
  
   ```bash
   tar xvf 'GNS3 VM.ova'
   ```
  
  4. Import the OVF (Open Virtualization Format) file using the `qm` command. Replace `<drive_name>` with the name of the drive where you want to install the Proxmox VM. You can find the drive name in the Proxmox web interface under "Disks" in the "Datacenter" section. Also, replace `<vm_id>` with a unique ID for your VM:
  
   ```bash
   qm importovf <vm_id> "GNS3 VM.ovf" <drive_name>
   ```
- ## Step 4: Configure the VM in Proxmox
  
  1. Open a web browser and access the Proxmox web interface using your Proxmox server's IP address. The URL should look like this: `https://<your_proxmox_ip>`.
  
  2. Log in to the Proxmox web interface.
  
  3. In the Proxmox web interface, locate the newly created VM. In this example, it was assigned an ID of 113.
  
  4. Select the VM, go to the "Hardware" section, and adjust the following settings:
	- **Memory**: Increase the memory allocation. More memory is better, but adjust according to your server's capabilities. Set the minimum RAM to 1200.
	- **CPU**: Add more cores and set the type to "host."
	- **Network Device**: Add a network device and set it to "vmbro1."
- ## Step 5: Boot and Access the VM
  
  1. Start the VM.
  
  2. Take note of the IP address assigned to the VM. You can usually find this information in your VM's console or by checking your DHCP server.
  
  With these steps, you should have successfully set up the GNS3 VM on your Proxmox server using the ESXi image and can now access and use it for your network simulations.