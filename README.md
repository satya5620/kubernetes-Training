# kubernetes-Training
```
Docker Container Life Cycle
=================================
https://www.devopsschool.com/blog/lifecycle-of-docker-containers/

 44  docker create jenkins
   45  docker ps -a
   46  docker start fef7316f5ca1
   47  docker ps -a
   48  docker stop fef7316f5ca1
   49  docker ps -a
   50  docker restart fef7316f5ca1
   51  docker ps -a
   52  docker pause fef7316f5ca1
   53  docker ps -a
   54  docker upause fef7316f5ca1
   55  docker unpause fef7316f5ca1
   56  docker upause fef7316f5ca1
   57  docker ps -a
   58  docker kill fef7316f5ca1
   59  docker ps -a
   60  history
   61  docker ps -a
   62  docker rm fef7316f5ca1
   63  docker ps -a
   64  history
   ```
   # checks the container or docker ip
   ```
   docker inspect <container-id> | grep -i ip
   ```
   #Rename the contaibner name
   ```
   Ex : docker rename <container-id> <conmtainer-new-name>
   Ex: docker rename fef7316f5ca1 Satya
   ```
   # docker all comands uasage 
   ```
   https://www.devopsschool.com/tutorial/docker/commands/index.html
   ```


### Notes 
```
https://www.devopsschool.com/notes/docker/2019/classroom-jan-public-2019.txt

```
