## Cloudflare DDNS Configuration for Deathraymind.net
#homelab
This section outlines the process of setting up a Docker container to automatically update `deathraymind.net` and its subdomains with the correct IP address.
- ### Creating the Docker Container in Portainer
  1. **Create a New Stack**
	- In your Portainer environment, create a new stack.
	  
	  2. **Paste the Following Configuration**
	- Use this Docker Compose configuration:
	  ```
	  `version: '2'`
	  `services:`
	  `cloudflare-ddns:`
	  `image: oznu/cloudflare-ddns:latest`
	  `restart: always`
	  `environment:`
	  `- API_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`
	  `- ZONE=deathraymind.net`
	  `- PROXIED=true`
	  
	  ```
- ## Obtaining the API Key from Cloudflare
- ### Steps to Generate a New API Key
  
  1. **Access Cloudflare Dashboard**
	- Log in to your Cloudflare account and access the dashboard.
	  
	  2. **Navigate to API Section**
	- Go to your profile in the upper right-hand corner.
	- Select 'API Tokens'.
	  
	  3. **Generate a New API Key**
	- Click on 'Create Token'.
	- Follow the prompts to create a new token with the necessary permissions.
	  
	  4. **Replacing the Placeholder in the Docker Configuration**
	- In your Docker Compose configuration, replace `XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX` with your newly generated API key.
- ### Purpose
  The purpose of this process is to automate the updating of DNS records for `deathraymind.net` and its subdomains. This ensures that they always point to the correct IP address.
- ### Completion
  Upon completing these steps and updating the API key in the Docker configuration, the Cloudflare DDNS service will automatically manage IP updates for your domain.