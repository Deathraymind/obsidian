# Building a pfSense Router/Firewall on ESXi

## Introduction

In this documentation, we will create a separate network for PXE booting using pfSense on an ESXi hypervisor. This modular setup allows us to control when the network is active and prevents unintended desktop PXE booting. This is the main router in our network, and we need to do a lot of configuration.

## Step 2: Download pfSense

1. Download the pfSense image from [https://www.pfsense.org/download/](https://www.pfsense.org/download/).
2. Click the prominent "**Download**" button, which will redirect you to the download page.
3. Look for the "**amd.iso.gz**" file, click on it, and extract the ISO file from the .gz archive.
![Uploaded Image](https://github.com/Deathraymind/HomeLab/blob/main/image7.png)

## Step 3: Upload pfSense ISO to ESXi

1. Open a web browser and access your ESXi hypervisor.
2. Navigate to **Datastore > Datastore Browser > Upload**.
3. Locate the pfSense ISO you extracted and double-click it to upload. Wait for the upload to complete.

## Step 4: Create pfSense Virtual Machine (VM)

1. In the ESXi web interface, go to **Create / Register VM**.
2. Click **Next** and name the VM "**pfSense**."
3. For the guest OS family, select **Other**, and for the guest OS version, choose **FreeBSD (64-bit)**. Click **Next**.
![Uploaded Image](https://github.com/Deathraymind/HomeLab/blob/main/image8.png)
4. Leave storage settings as default and click **Next**.
5. Customize the VM settings as follows:
   - **CPU Cores:** 4
   - **RAM:** 8GB
   - **Hard Disk Storage:** 45GB
6. Scroll down to the network adapter section. Ensure the first adapter is set to "**port0**."
7. Click **Add Network Adapter** at the top, and you should see two network adapters. The top one should be set to "**port0**," and the second adapter should be set to "**port1**."
![Uploaded Image](https://github.com/Deathraymind/HomeLab/blob/main/image1.png)
8. Scroll down to **CD/DVD Drive 1**, select the dropdown, choose **Datastore ISO file**, and select your newly uploaded pfSense ISO.
9. Click **Next** and power on the VM.

## Step 5: Configure pfSense

1. Start the pfSense VM and select "**Multi-user mode**" to let pfSense boot (this may take some time).
2. Accept the terms and conditions.
3. Choose "**Install pfSense**."
4. Continue with the default keymap.
5. Select "**Auto ZFS**" for installation.
6. Choose "**Install**."
7. For storage configuration (assuming you want to use the entire disk):
   - Tab to the VMware virtual disk.
   - Press the spacebar to select it.
   - Confirm with "**OK**."
   - Select "**Yes**" to destroy the disk and proceed with installation.
8. After it's done loading, select **yes** to the shell.
9. Type **exit** and reboot.

## Step 7: Post-Installation Configuration

1. After the pfSense installation, the machine will reboot. When prompted, you may be asked if VLANs should be set up. Type "**n**" and press "**Enter**" for no.
2. Next, you'll be asked to select the WAN port. Choose "**vmx0**," which corresponds to Port 0 on your ESXi server. This port connects to the internet from outside your network.
3. Then, select the LAN interface, which will be "**vmx1**." This is the port connected to the PXE switch in your topology.
4. You'll be prompted to proceed; type "**yes**" and press "**Enter**."

## Step 8: Configuring IP Addresses

1. The default LAN IP and DHCP range is **192.168.1.1**, which may conflict with your main router. To change this, type "**2**" to set the LAN interface's IP address.
2. The WAN interface should already be configured with an IP address obtained via DHCP from your main network's router.
3. When asked for the LAN IPv4 address, enter "**192.168.4.1**" (or any unused address in your network). This address will also be used to access pfSense's web interface.
4. Choose "**24**" as the subnet mask, which is common and easy to work with.
5. When asked to set the upstream gateway address, press "**Enter**" for none.
6. Don't enter an IPv6 address.

## Step 9: Enabling DHCP Server on LAN

1. You'll reach a crucial step where it asks, "Do you want to enable the DHCP server on LAN?" Select "**yes**" since a PXE server requires DHCP.
2. For the start address range of the DHCP server, enter "**192.168.4.4**."
3. For the end address range, enter "**192.168.4.254**."
4. Choose to keep HTTPS by selecting "**no**."

By following these steps, you have configured pfSense for your PXE server on a separate subnet. Remember that you can only access the pfSense web interface when connected to the PXE switch, as it operates on a different subnet.


# Customizing pfSense with a GitHub Theme

## Finding and Applying a New Theme

### Step 1: Find a Theme for pfSense on GitHub
- **Description**: Locate a pfSense theme that you prefer on GitHub.
- **Example**: "Blunify Dark" theme available at [Blunify Dark Theme](https://github.com/everything-tech-related/pfSense-Firewall-themes/blob/master/pfSense-theme-blunify-dark.css).

### Step 2: Download the Theme File
- **Action**: Download the `.css` file for the theme onto your local computer.
- **File Name**: `pfSense-theme-blunify-dark.css`.

### Step 3: Use SCP to Transfer the File
- **Purpose**: SCP (Secure Copy Protocol) is used for secure file transfer between a local host and a remote host.
- **Command**:
    ```ruby
    scp pfSense-theme-blunify-dark.css admin@172.16.0.1:/usr/local/www/css/
    ```

#### Command Breakdown
- `scp`: Command to initiate the secure copy.
- `pfSense-theme-blunify-dark.css`: Local path to the downloaded theme file.
- `admin@172.16.0.1`: Replace `admin` with your pfSense username and `172.16.0.1` with the IP address of your pfSense router.
- `/usr/local/www/css/`: Destination directory on the pfSense router for the theme file.

### Step 4: Enable SSH on pfSense
- **Requirement**: Enable SSH if it's not already active on your pfSense router.
- **Method**: Access your pfSense console and select option 14 to enable SSH.

### Step 5: Apply the Theme
- **Next Steps**: After transferring the file, configure pfSense to use the new theme, which may involve editing configuration files or settings within the pfSense web interface.



