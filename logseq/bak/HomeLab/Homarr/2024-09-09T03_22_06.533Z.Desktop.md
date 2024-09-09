

# Welcome to the HomeLab Wiki!

## Setting Up Homarr Dashboard

Homarr provides a simple yet powerful dashboard for your server. Here's how you can easily set it up using Docker Compose or a stack in Portainer.

### Steps to Set Up Homarr
1. create the directories for the container replace with your username. 

```bash
mkdir -p /home/#YourUsername#/dockerdata/homarr/configs
mkdir -p /home/#YourUsername#/dockerdata/homarr/data
mkdir -p /home/#YourUsername#/dockerdata/icons
```


2. **Create a Docker Compose File or a Stack in Portainer**
   - Prepare to add the configuration details.

3. **Paste the Following Configuration**
   - Use this Docker Compose configuration:

```yaml
version: '3'
#---------------------------------------------------------------------#
#     Homarr - A simple, yet powerful dashboard for your server.     #
#---------------------------------------------------------------------#
services:
  homarr:
    container_name: homarr
    image: ghcr.io/ajnart/homarr:latest
    restart: unless-stopped
    volumes:
      - /home/#YourUsername#/dockerdata/homarr/configs:/app/data/configs
      - /home/#YourUsername#/dockerdata/homarr/data:/data
      - /home/#YourUsername#/dockerdata/icons:/app/public/icons
    ports:
      - '7575:7575'


```

## Provision the Container

Run the command 
  ```  docker-compose up -d to provision it. ```

## Accessing the Homarr Dashboard

You can reach the Homarr dashboard at the IP address of your Docker server.
In this example, it is 172.16.16.10:7575.
Note: 7575 is the port for Homarr.


