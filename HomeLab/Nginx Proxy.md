# Nginx Proxy Manager Setup Documentation
#homelab
- ### Purpose
  To set up Nginx Proxy Manager using Docker Compose.
- ### Steps
- ### Make the Docker Bind Directories 
  
  ```bash
  mkdir -p /home/$(whoami)/dockerdata/NGINXProxyManager/letsencrypt
  mkdir -p /home/$(whoami)/dockerdata/NGINXProxyManager/data
  ```
- ## 1. Docker Compose File
- Create a `docker-compose.yml` file in the desired directory (e.g., `/home/#YourUsername#/dockerdata/NGINXProxyManager/`). Replace `#YourUsername#` with your actual username.
  
  ```bash
  nano docker-compose.yml
  ```
- Add the following content to the file:
  
  
  ```yaml
  version: '3.8'
  services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - /home/#YourUsername#/dockerdata/NGINXProxyManager/data:/data
      - /home/#YourUsername#/dockerdata/NGINXProxyManager/letsencrypt:/etc/letsencrypt
  ```
- ## Access pfSense Router
- ### Purpose
  To configure your network to allow traffic to your Nginx instance.
- ### Steps
- Access your pfSense router by navigating to `172.16.0.1` in a web browser.
- ## Configure NAT in pfSense
- ### Purpose
  To set up Network Address Translation (NAT) for secure connections.
- ### Steps
- Navigate to `Firewall > NAT > Add`.
- Adjust settings for Protocol (TCP/UDP), Destination Port (443), Redirect IP (address of Nginx host, replace with your actual IP, e.g., `172.16.16.10`), and Redirect Port (443).
- ## Create Firewall Rules in pfSense
- ### Purpose
  To define rules for incoming traffic.
- ### Steps
- Go to `Firewall > Rules > Add`.
- Set Source and Destination to "Any," and specify Port 443.
- ## Access Nginx Proxy Manager Web Interface
- ### Purpose
  To configure Nginx Proxy Manager.
- ### Steps
- Visit `http://172.16.16.10:81` (replace with your Nginx host IP) and log in with the default credentials.
  
  Email:    admin@example.com
  Password: changeme
- ## Creating SSL Certificates
- ### Purpose
  To secure your domains with SSL certificates.
- ### Steps
- In the Nginx Proxy Manager, navigate to SSL Certificates.
- Add a new SSL certificate for your domain (e.g., `*.example.com`).
- Choose Cloudflare for integration.
- ## Cloudflare API Token Setup
- ### Purpose
  To integrate Cloudflare with your setup for domain management.
- ### Steps
- Access the Cloudflare Dashboard and go to your profile in the upper right-hand corner.
- Navigate to API Tokens and create a new token with specific permissions for Zone Settings and DNS Editing.
- ## Configure Nginx Proxy Manager with Cloudflare
- ### Purpose
  To set up a proxy host using Cloudflare.
- ### Steps
- In Nginx Proxy Manager, add a proxy host (e.g., homarr).
- Configure domain (e.g., `homarr.example.com`), scheme, forward IP, port (e.g., `7575`), and SSL settings.
- Block common exploits and go to the SSL tab.
- Set it to the wildcard SSL certificate provisioned earlier and force SSL. Then save.
- ## Cloudflare DNS Configuration
- ### Purpose
  To configure DNS settings for your domain.
- ### Steps
- In your Cloudflare DNS settings, add a new CNAME record for your domain that points to your top-level domain (TLD).
- ### Completion
  Your setup of Nginx Proxy Manager with SSL certificates and Cloudflare integration is complete. This allows secure access to your home network services via `https://homarr.example.com`, utilizing Cloudflare for DNS management and SSL certificate provisioning.
  
  ---
  
  Remember to replace placeholders like `#YourUsername#` and specific IP addresses with your actual user details and network configuration settings.