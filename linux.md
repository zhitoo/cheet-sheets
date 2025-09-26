### my headphone or speaker not working! waht should i do? run below command
```alsactl restore```

### How to Add SSH Public Key to Server

first u need create an ssh key  
```ssh-keygen```  
an then copy it to your server  
```ssh-copy-id -i ~/.ssh/id_rsa.pub YOUR_USER_NAME@IP_ADDRESS_OF_THE_SERVER```
#### change host name
```hostnamectl set-hostname server1.example.com```
#### show host name
```hostname```
### docker swarm
```docker swarm init --advertise-addr <MANAGER-IP>```
```docker swarm join-token worker```
```docker swarm join-token manager```
```docker swarm join --token <WORKER-TOKEN> <MANAGER-IP>:2377```
```docker node ls```
```docker network create -d overlay my-overlay-net```
```docker stack deploy -c docker-compose.yml mystack```
```docker stack services mystack```
```docker stack ps mystack```
```docker stack rm mystack```
```docker stack rm mystack```
```docker service scale mystack_web=5```
```docker service update --image myimage:tag mystack_web```
```docker service update --update-parallelism 1 --update-delay 10s --image myimage:tag mystack_web```
```docker node promote <NODE-ID-or-HOSTNAME>```
```docker node demote <NODE-ID-or-HOSTNAME>```
```docker node rm <NODE-ID>```
```docker swarm leave```
```docker swarm leave --force```
