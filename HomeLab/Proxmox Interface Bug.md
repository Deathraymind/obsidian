sudo ```bash
nano /etc/network/interfaces
```

```plaintext
auto vmbr0
iface vmbr0 inet dhcp
    bridge_ports enp
    bridge_stp off
    bridge_fd 0
```