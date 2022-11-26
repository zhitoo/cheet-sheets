## How to install portainer?
### You must first create volume
```bash
docker volume create portainer_data
```
### and then run portainer you can change port 8000 and 9000 with your favorite port
```bash
# run on port 8000 and 9000
docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```
```bash
# run on port 7000 adn 3000
docker run -d -p 7000:8000 -p 3000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```