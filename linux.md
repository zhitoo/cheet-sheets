### my headphone or speaker not working! waht should i do? run below command
```alsactl restore```

### How to Add SSH Public Key to Server

first u need create an ssh key  
```ssh-keygen```  
an then copy it to your server  
```ssh-copy-id -i ~/.ssh/id_rsa.pub YOUR_USER_NAME@IP_ADDRESS_OF_THE_SERVER```
