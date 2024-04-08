**DD-WRT Router Configuration Guide**

Tags [[Open-WRT AP Setup]] [[Aruba IAP Config]] [[Fresh-Tomato AP Setup]]

This guide will walk you through the process of configuring your DD-WRT router to ensure optimal performance and security. Please follow each step carefully to avoid any issues.

**Step 1: Hard Reset**

Perform a hard reset on your router to restore it to DD-WRT default settings.

**Step 2: Initial Connection**

1. Connect your computer to the router using an Ethernet cable.
2. Open a web browser and enter `http://192.168.1.1` in the address bar.

Note: If your router is connected to another router, disconnect it temporarily to avoid conflicts.

**Step 3: Basic Setup**

1. Navigate to the **"Setup"** tab and then select **"Basic Setup"**.
2. Configure the following settings:
   - **WAN Connection Type:** Disabled
   - **Local IP Address:** Set to an IP address outside the DHCP range of your primary router (e.g., 192.168.1.2)
   - **Subnet Mask:** 255.255.255.0
   - **DHCP Server:** Disable
   - **Gateway:** IP address of your primary router
   - (Optional) **Local DNS:** IP address of your primary router or local DNS server
   - (Optional) **Assign WAN Port to Switch:** Check this option if available
   - (Recommended) **NTP Client:** Enable
3. Click **"Save"**.

**Step 4: Advanced Routing**

1. Go to the **"Setup"** tab and select **"Advanced Routing"**.
2. Change the operating mode to **"Router"**.
3. Click **"Save"**.

**Step 5: Wireless Settings**

1. Navigate to the **"Wireless"** tab and select **"Basic Settings"**.
2. Set the Wireless Network Name (SSID) as desired.
3. (Optional) Adjust **Sensitivity Range** if needed.
4. Click **"Save"**.

**Step 6: Wireless Security**

1. Go to the **"Wireless"** tab and select **"Wireless Security"**.
2. Configure the following settings:
   - **Security Mode:** WPA2
   - **WPA Algorithm:** AES
   - **WPA Shared Key:** Choose a strong password (8 characters or more).
3. Click **"Save"**.

**Step 7: Services Configuration**

1. Navigate to the **"Services"** tab and select **"Services"**.
2. Disable **DNSMasq** and **ttraff Daemon**.
3. Click **"Save"**.

**Step 8: Firewall Settings**

1. Go to the **"Security"** tab and select **"Firewall"**.
2. Disable **SPI firewall**.
3. Check **"Filter Multicast"**.
4. Click **"Save"**.

**Step 9: Administration**

1. Navigate to the **"Administration"** tab and select **"Management"**.
2. Enable **Info Site Password Protection**.
3. Click **"Save"** and then **"Apply Settings"**.
4. Connect an Ethernet cable from the router to the main router's LAN port.
5. If needed, reboot the router to ensure all settings are applied.
6. You may need to reboot your computer or renew the IP configuration if necessary (e.g., "ipconfig /release" then "ipconfig /renew" in Windows).

