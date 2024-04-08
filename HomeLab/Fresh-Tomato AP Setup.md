

---
Tags [[DD-WRT AP Setup]] [[Aruba IAP Config]] [[Open-WRT AP Setup]]
# Configuring Router as a Dumb Access Point (AP)

This guide outlines the steps to configure a router to function as a Dumb Access Point (AP) within an existing network. By following these instructions, you can repurpose a router to act as a switch or additional access point, extending your network coverage.

## Prerequisites

- Access to the router's configuration interface.
- Basic understanding of networking concepts.

## Steps

### 1. Access WAN Settings

Navigate to the WAN settings section of the router's configuration interface:

1. Access the router's web-based configuration interface.
2. Navigate to the **Basic** tab.
3. Click on **WAN** settings.

### 2. Disable WAN Connection

Disable the WAN connection to use the router solely as a LAN device:

- Change the **Type** to **Disabled**.

### 3. Bridge WAN Port to LAN

Optionally, bridge the WAN port to the primary LAN to utilize the WAN port as an additional LAN port:

- Enable **Bridge WAN port to primary LAN**.

### 4. Configure LAN Settings

Configure LAN settings to set a static IP address and disable DHCP:

1. Under the **LAN** settings:
   - Assign a static IP Address within your network range.
   - Disable the DHCP server.

### 5. Set Default Gateway and DNS

Specify the default gateway and DNS server(s) for the router:

- Set the **Default Gateway** and **DNS server(s)** to the IP address of your main router.

### 6. Save Settings

Save the changes made to the router's configuration:

- Click **OK** or **Save** to apply the settings.

### 7. Connect Ethernet Cable

If the WAN port wasn't assigned to act as another LAN port, move the Ethernet cable to one of the actual LAN ports:

- Ensure the Ethernet cable is connected to one of the LAN ports to proceed with configuring the router as a Dumb AP.

## Conclusion

By following these steps, you can repurpose a router as a Dumb Access Point within your network. This setup allows you to extend network coverage and improve connectivity without the need for additional hardware.

---
