# How can I use docker without sudo?
1- Add the docker group if it doesn't already exist:
```bash
 sudo groupadd docker
```
2- Add the connected user "$USER" to the docker group. Change the user name to match your preferred user if you do not want to use your current user:
```bash
sudo usermod -aG docker $USER
newgrp docker
```
3- remove extra files 
```bash
truncate -s 0 /var/lib/docker/containers/**/*-json.log
docker builder prune --all
docker image prune --all
```
