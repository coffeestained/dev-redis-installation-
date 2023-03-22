# dev-redis-installation-
A small guide on how to set up Redis on an external Ubuntu VM and access it via tunnel on your local machine.

## Update your apt packages
```
sudo apt update
```

## Install Redis Service
```
sudo apt install redis-server
```

## Edit /etc/redis/redis.conf
```
nano /etc/redis/redis.conf
```
or 
```
vi /etc/redis/redis.conf
```

## Adjust /etc/redis/redis.conf supervised key to use systemd
```
~~supervised no~~
```
to 
```
supervised systemd
```

## Optionally add a password by editing /etc/redis/redis.conf
```
nano /etc/redis/redis.conf
```
or 
```
vi /etc/redis/redis.conf
```

## Optionally add a password by adjusting requirepass key to your preferred password
```
~~# requirepass default~~
```
to 
```
requirepass 7verySecurePasswordNoCapOnGSheesh7
```

## Restart
```
sudo systemctl restart redis.service
```

## Note your redis cache is now ready to go locally.
## A few notes: use prefixes when interacting and storing data. 
## Otherwise you'll run into conflicts. 
## See: https://redis.com/redis-best-practices/introduction/ 
## For more information.

## Finally, if you wish to access this Redis cache from your local machine.
## Follow the following guide to create a tunnel to your VM via SSH.
## See: https://github.com/coffeestained/simple-ssh-config

## EZ PZ

  
