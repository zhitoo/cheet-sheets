#### install gluster
```
sudo apt update
sudo apt install -y glusterfs-server
sudo systemctl start glusterd
sudo systemctl enable glusterd
```
#### create peer
```
sudo gluster peer probe node2
sudo gluster peer probe node3
```
#### check peers
```
sudo gluster peer status
```   
#### brick dir
```
udo mkdir -p /gluster/brick1
sudo chown nobody:nogroup /gluster/brick1  
```
#### create volume
```
sudo gluster volume create shared-vol replica 3 \
  node1:/gluster/brick1 \
  node2:/gluster/brick1 \
  node3:/gluster/brick1 force
```
#### start volume
```
sudo gluster volume start shared-vol
sudo gluster volume status shared-vol
```
#### check share info
```
gluster volume info share
```
#### stop and remove volume
```
gluster volume stop share-vol
gluster volume delete share-vol
```
#### mount volume
```
mount -t glusterfs server1:/shared-vol /mnt/shared
```   
