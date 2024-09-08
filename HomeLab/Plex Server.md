# Add Plex APT Repository and Import GPG Key
#homelab

Execute the following commands to add the Plex APT repository to your system and import the repository's GPG key:

```bash
curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -
echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list
```
- # Update Package List and Install Plex Media Server
  
  Update your package list and install the latest version of the Plex Media Server:
  
  ```sql
  sudo apt update
  sudo apt install plexmediaserver
  ```
- # Verify Plex Service Status
  
  To confirm that Plex is running, check the service status with:
  
  ```lua
  sudo systemctl status plexmediaserver
  ```
  
  You should see an output indicating that the Plex Media Server is active and running.
- # Configure Plex Media Server
  
  Create directories to store Plex media files:
  
  ```bash
  sudo mkdir -p /opt/plexmedia/{movies,series}
  ```
  
  Set the correct ownership for these directories. The Plex Media Server runs as the user 'plex', which requires read and execute permissions:
  
  ```bash
  sudo chown -R plex: /opt/plexmedia
  ```
  
  Note: You can choose any location to store media files, but ensure to set the correct permissions.
- # Access Plex Server Configuration
  
  To proceed with server configuration, open your web browser and navigate to:
  
  ```arduino
  http://YOUR_SERVER_IP:32400/web
  ```
  
  This address will redirect you to the Plex website for further configuration.
- # File Browser Docker Setup Guide
  
  File Browser provides a convenient way to manage files and directories through a web interface. This guide covers setting up File Browser in a Docker container on a Linux-based system.
- ## Prerequisites
- Docker installed on your system.
- Basic knowledge of terminal commands.
- ## Installation Steps
  
  1. **Create Required Directory and Files**
  
   Set up the directory and necessary files for File Browser:
  
   ```bash
   mkdir -p /home/filebrowser
   touch /home/filebrowser/filebrowser.db
   touch /home/filebrowser/.filebrowser.json
   ```
  
   These commands create a directory for File Browser and two files: one for the database and another for the configuration.
  
  2. **Edit the Configuration File**
  
   Open the configuration file with a text editor (e.g., nano):
  
   ```bash
   sudo nano /home/filebrowser/.filebrowser.json
   ```
  
   Insert the following JSON configuration:
  
   ```json
   {
     "port": 80,
     "noAuth": false,
     "baseURL": "",
     "address": "",
     "log": "stdout",
     "database": "/database.db",
     "root": "/srv"
   }
   ```
  
   Save the file and exit the editor.
  
  3. **Set File Permissions**
  
   Adjust permissions for the database file to ensure File Browser can access it:
  
   ```bash
   chmod 666 /home/filebrowser/filebrowser.db
   ```
  
  4. **Run File Browser in Docker**
  
   Start the File Browser container in detached mode:
  
   ```bash
   sudo docker run -d \
       -v /home/filebrowser:/srv \
       -v /home/filebrowser/filebrowser.db:/database.db \
       -u $(id -u):$(id -g) \
       -p 8080:80 \
       --restart unless-stopped \
       filebrowser/filebrowser
   ```
- ## Setting file perms CAREFULL
  
  ```bash
  sudo chmod -R 777 /home/filebrowser
  ```
   This command will start File Browser in the background and map it to port 8080 on your host machine.
- ## Accessing File Browser
  
  After running the Docker command, File Browser will be accessible through your web browser:
- URL: `http://localhost:8080`
- Default Username: `admin`
- Default Password: `admin`
  
  Remember to change the default username and password for security reasons.
- ## Management Commands
- **View Logs**: `docker logs [container-id]`
- **Stop Container**: `docker stop [container-id]`
- **Start Container**: `docker start [container-id]`
  
  Find your container ID using `docker ps`.