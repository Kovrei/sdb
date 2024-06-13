[install docker](https://github.com/Kovrei/home_work/blob/main/docker/docker%20install.md)
### вариант 1
```
docker run --name mem -p 11211:11211 -d memcached
docker ps
telnet localhost 11211
```
### вариант 2
```
sudo apt update && sudo apt install memcached
systemctl status memcached
telnet localhost 11211
```
**проверка через команду**  
stats
