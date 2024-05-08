

---

## Network Configuration Setup

### Editing Network Interfaces

To configure network interfaces on your system, follow these steps:

1. Open the network interfaces configuration file using your preferred text editor. In this example, we'll use `nano`.

    ```bash
    sudo nano /etc/network/interfaces
    ```

2. Add the following configuration for `vmbr0`:

    ```plaintext
    auto vmbr0
    iface vmbr0 inet dhcp
        bridge_ports enp3s0f0
        bridge_stp off
        bridge_fd 0
    ```

    - `auto vmbr0`: Automatically bring up the `vmbr0` interface on system startup.
    - `iface vmbr0 inet dhcp`: Configure the interface `vmbr0` to obtain an IP address dynamically using DHCP.
    - `bridge_ports enp3s0f0`: Specify the physical interface `enp3s0f0` to be bridged with `vmbr0`.
    - `bridge_stp off`: Disable Spanning Tree Protocol (STP) on the bridge interface.
    - `bridge_fd 0`: Set the bridge forward delay to 0 seconds.

### Restarting Networking Service

After making changes to the network configuration, it's essential to restart the networking service for the changes to take effect. Run the following command:

```bash
sudo systemctl restart networking
```

This command will restart the networking service, applying any recent configuration changes.

---
