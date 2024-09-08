# Documentation: Setting Up a Steam Cache Server on TrueNAS SCALE

## Introduction
This guide explains how to set up a Steam cache server using TrueNAS SCALE. This setup will store game content locally, reducing bandwidth and speeding up downloads across your network.

## Prerequisites
- TrueNAS SCALE server
- Basic knowledge of networking and Docker
- pfSense router (for network configuration)
- Optional: Zentyal or AD/LDAP server for advanced network management

## Configuration Steps

### 1. Adjusting TrueNAS SCALE GUI Settings
- **Login** to TrueNAS SCALE.
- Navigate to **System Settings > GUI Settings**.
- **Change the web ports** to **444** and **81**. This is necessary because the LAN cache requires ports **443** and **80** to be open to function correctly.

### 2. Creating a Storage Pool
- Go to **Storage > Create Pool**.
- Select drives of similar sizes to enable a RAID-Z configuration. This allows drives to mirror each other, providing redundancy and data safety.

### 3. Setting Up Datasets
- Navigate to **Datasets > Add Datasets**.
- Create a new directory named `data` and within it, another directory called `cache`.
- This organization helps manage cached data, which can be multiple terabytes on large networks.

### 4. Configuring Kubernetes on TrueNAS SCALE
- TrueNAS SCALE uses Kubernetes and Rancher for scalable Docker deployments, differing from other TrueNAS versions that use Unix and don't support Docker.
- Go to **Apps > Settings > Advanced Settings**.
  - **Node IP**: Leave as `0.0.0.0` (localhost), as it shares the same IP as TrueNAS SCALE.
  - **Route Interface**: Use the same physical interface as TrueNAS, e.g., `enp0s25`.
  - **Route v4 Gateway**: Set this to your router's IP, e.g., `172.16.0.1`.
  - **Cluster CIDR**: Use a different subnet than your network, e.g., `172.17.0.0/16`. This avoids conflicts.
  - **Service CIDR**: This also needs a separate network, e.g., `172.18.0.0/16`.
  - **Cluster DNS IP**: Set this to an IP like `172.18.0.10`. These settings are crucial if you don't have a Kubernetes network and the setup is not intended to work with other devices in unison.

### 5. Setting Static IP in pfSense
- Set a static IP for TrueNAS SCALE in pfSense (e.g., `172.16.16.110`), then restart TrueNAS SCALE.

### 6. Installing Docker Compose on TrueNAS SCALE
- SSH into TrueNAS SCALE (`ssh admin@172.16.16.110`).
- Install Docker Compose using:
  ```bash
  sudo curl -L "https://github.com/docker/compose/releases/download/[latest-version]/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
  sudo chmod +x /usr/local/bin/docker-compose
  ```

### 7. Configuring Lancache
- Navigate to the cache directory: `cd /mnt/NAS/data/cache`.
- Clone the Lancache repository and navigate to it:
  ```bash
  git clone https://github.com/lancachenet/docker-compose lancache
  cd lancache
  ```
- Edit `.env` file (e.g., `sudo nano .env`) and set the necessary configurations:
  - `LANCACHE_IP` and `DNS_BIND_IP`: Set these to the static IP of TrueNAS SCALE (e.g., `172.16.16.110`).
  - `UPSTREAM_DNS`: Set this to your Pi-hole or primary DNS server IP (e.g., `172.16.16.40`).
  - `CACHE_ROOT`: Point to your cache directory (e.g., `/mnt/NAS/Data/cache`).

### 8. Launching Lancache
- Run `sudo docker-compose up -d` to start the Lancache Docker instance.

### 9. Integrating with Network DNS
- If using a Zentyal or AD/LDAP server:
  - Configure the DNS to forward requests to the Lancache server.
  - Set Lancache's IP (e.g., `172.16.16.110`) as the new forwarder.

### 10. Testing the Configuration
- Test with `nslookup steam.cache.lancache.net` (should resolve to the TrueNAS SCALE IP).
- Ensure connectivity to the internet and internal network resources like `cybersecurity.lan` or your AD/LDAP server.

## Conclusion
Following these steps sets up a Steam cache server on TrueNAS SCALE, optimizing game download speeds and managing network bandwidth more effectively. Regularly check and update your