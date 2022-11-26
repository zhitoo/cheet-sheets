# How can I use docker without sudo?
1- Add the docker group if it doesn't already exist:
```bash
 sudo groupadd docker
```
2- Add the connected user "$USER" to the docker group. Change the user name to match your preferred user if you do not want to use your current user:
```bash
sudo gpasswd -a $USER docker
```