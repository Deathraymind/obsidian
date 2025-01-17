- #homelab
- apt install docker.io docker-compose
- ```
  sudo  docker volume create portainer_data
  ```
- ```bash 
  sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.21.5
  ```
- ```
  https://localhost:9443
  ```