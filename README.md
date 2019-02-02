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
## exit from containe
```
Ctrl+pq
```
## diferrence betwen dcker attch and docker exec
```
Note: This command (attach) is not for running a new process in a container. See: docker exec.
ex : https://askubuntu.com/questions/505506/how-to-get-bash-or-ssh-into-a-running-container-in-background-mode/507009#507009
```
### Notes 
```
https://www.devopsschool.com/notes/docker/2019/classroom-jan-public-2019.txt

```

## how craete image,tar,save, and how to share images to hub,artifactory,tar

```

How to create a image?
Manual Way - Existing Container
140  docker run -itd ubuntu
  141  docker ps
  142  docker attach 89d7e9b6c359
  143  docker ps -a
  144  df -kh
  145  docker commit -m"ub-git-vim" -a "Rajesh Kumar" 89d7e9b6c359 ub-git-vim
  146  docker images
  147  docker history ubuntu
  148  docker history ub-git-vim
  149  history

How to share a images?
	Tar ball
 161  docker images
  162  docker save -o ub-git-vim.tar ub-git-vim
  163  ls
  164  docker rmi ub-git-vim
  165  docker images
  166  docker load -i ub-git-vim.tar
  167  docker images
  168  docker run -itd --name=ub-git-vim ub-git-vim
  169  docker ps
  170  docker rm 89d7e9b6c359
  171  docker stop 89d7e9b6c359
  172  docker rm 89d7e9b6c359
  173  docker ps
  174  docker run -itd ubuntu
  175  docker ps
  176  docker exec 4c7073c3ce7f git
  177  docker exec cf580b2707b0 git
  178  docker ps
  179  docker history ub-git-vim
  180  clear
  181  ls
  182  tar -xvf ub-git-vim.tar rr
  183  mkdir rr
  184  tar -xvf ub-git-vim.tar rr
  185  tar -xvf ub-git-vim.tar -d rr
  186  ls
  187  tar -xvf ub-git-vim.tar
  188  ls
  189  clear
  190  tree
  191  yum install tree
  192  tree
  193  ls
  194  grep -r bash .
  195  clear
  196  history


	hub.docker.com
 199  docker images
  200  docker login
  201  docker push ub-git-vim
  202  docker tag ub-git-vim scmgalaxy/saturday
  203  docker images
  204  docker push scmgalaxy/saturday
  205  history


	Nexus|Artifactory|Registry


Auto - Dockerfile
```
```
