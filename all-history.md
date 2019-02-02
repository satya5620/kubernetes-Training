```
https://www.devopsschool.com/notes/docker/

1 13.232.31.197
2 35.154.165.106
3 13.233.107.212
4 13.127.250.191
5 13.232.55.74
6 13.233.41.164
7 13.233.34.22
8 13.127.44.217
9  13.234.59.1
10 13.234.33.75

ec2-user


What is Docker?
	Container mgmt tool.
	Release -
		CE - Communtity Edi
		EE - Enterprse - 12 Hours --

What is Container?

- Collection of Image
- Isolation of process
- Soft Pack....


Why we needd multiple Server to Run multiple App?
- Scalibility -> Monitoring Tool -> nEtwork - OS -> KERNAL -> NAMESPACE (NET)
- Availability -> LB -> Network  -  - OS -> KERNAL -> -> NAMESPACE (NET)
- Isolation -> OS -> USER ENV -->  -  - OS -> KERNAL -> -> NAMESPACE (USER)
- Security --> 
- 
========================================================
How to install docker?
https://www.devopsschool.com/tutorial/docker/install-config/
https://www.devopsschool.com/tutorial/docker/install-config/docker-install-commuityedition-centos-rhel.html

13.232.31.197

  7  clear
    8  ls
    9  clear
   10  docker
   11  clear
   12  ps -eaf | grep docker
   13  ifconfig
   14  sudo systemctl start docker
   15  ifconfig
   16  clear
   17  ls
   18  sudo systemctl enable docker
   19  clear
   20  ls
   21  docker info
   22  docker version
   23  which docker
   24  ps -eaf | grep docker
   25  clear
   26  which docker
   27  history
================================
Docker Componets are....
	Docker Engine				DONE
	Docker Images = Files system of Base OS + APps files
	Docker Container - 
		The moment, you run Image 1 time - 1 container get created
					  1000 times - 1000 	
	Docker registry
			hub.docker.com
--------------------------------------------
ngnix
apache
redis
jboss
ws
mysql
wordpress
mongodb
rabbit
----------------------------------------------------
jenkins
---------------------------------------------------

   28  clear
   29  ls
   30  ls
   31  clear
   32  docker images
   33  cd /var/lib/docker
   34  ls
   35  docker info
   36  ls
   37  clear
   38  docker info
   39  ls
   40  cd overlay2
   41  ls
   42  pwd
   43  pwd
   44  ls
   45  cd ..
   46  ls
   47  du -sh overlay2/
   48  docker pull jenkins
   49  docker images
   50  du -sh overlay2/
   51  docker info
   52  docker ps
   53  docker ps -a
   54  history
   55  docker run jenkins

  1  clear
    2  docker ps
    3  docker run -d jenkins
    4  docker ps
    5  docker run -d jenkins
    6  docker ps
    7  docker run -d jenkins
    8  docker run -d jenkins
    9  docker ps
   10  docker ps
   11  docker ps -a
   12  history

Container is a userspace( get a PID)
		- Net
		- mtn
		- pmap
 12  history
   13  cler
   14  clear
   15  ls
   16  ps -eaf | grep docker
   17  ps -eaf | grep docker | wc -l
   18  docker ps
   19  docker run -d jenkins
   20  ps -eaf | grep docker | wc -l
   21  ps -eaf | grep docker | wc -l
   22  clear
   23  docker ps
   24  docker inspect 10815f666e08 | grep -i ip
   25  docker inspect cacdd47ea295 | grep -i ip
   26  docker inspect 9d800137b9a9 | grep -i ip
   27  docker inspect 251828536dd0 | grep -i ip
   28  clear
   29  ls
   30  docker ps
   31  docker exec 10815f666e08 df -kh
   32  docker exec cacdd47ea295 df -kh
   33  docker exec 10815f666e08 touch /var/jenkins_home/rajesh.txt
   34  docker exec 10815f666e08 ls /var/jenkins_home
   35  docker exec cacdd47ea295 ls /var/jenkins_home
   36  clelar
   37  clear
   38  docker ps
   39  docker exec 10815f666e08 ps -eaf
   40  docker exec cacdd47ea295 ps -eaf
   41  history

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
========================================
EACH CONTAINER IS ALIVE ONLY COZ OF PID 1
 4  docker run -d jenkins
    5  docker ps
    6  docker run -d ubuntu
    7  docker ps
    8  docker ps -a
    9  docker run -it -d ubuntu /bin/bash
   10  docker ps -a


STOP ALL CONTAINER
docker stop $(docker ps -aq)

DELETE ALL CONTAINER
docker rm $(docker ps -aq)

How to access a container?
	Web
	$ docker run -d jenkins
	$ docker run -d -p 8080:8080 -p 50000:50000 jenkins
	$ docker run -d -p 8090:8080 -p 50001:50000 jenkins
	
	Command
	exec
	--- exec will execute a executables insdie a container n give a output on consolve
		docker exec cont-id df -kh
		docker exec cont-id ls
		docker exec cont-id more
		docker exec cont-id touch
		Everytime it craetes a new terminal....	
		You can interact with -it & bin bash
	
	attach
	- Attach to a PID 1
========================================
docker help
https://www.devopsschool.com/tutorial/docker/commands/index.html

 67  touch devopsschool.com
   68  docker cp devopsschool.com dae3c3429941:/opt
   69  docker exec dae3c3429941 ls /opt
   70  ls
   71  rm -rf devopsschool.com
   72  docker exec dae3c3429941 ls /opt
   73  docker cp dae3c3429941/opt/devopsschool.com .
   74  docker cp dae3c3429941:/opt/devopsschool.com .
   75  ls
   76  history
   77  clear
   78  clear
   79  docker ps
   80  docker attach ubuntu
   81  docker attach dae3c3429941
   82  docker ps
   83  docker diff dae3c3429941
   84  clear
   85  docker images
   86  docker inspect jenkins
   87  clear
   88  docker ps
   89  docker inspect dae3c3429941
   90  clear
   91  docker ps -a
   92  docker rename 9eedf97622c6 rajesh
   93  docker ps -a
   94  docker run -d --name=rajesh1 jenkins
   95  docker ps -a
   96  clear
   97  docker ps
   98  docker logs 7cc1bee10ffc
   99  docker stats
  100  history
https://www.devopsschool.com/tutorial/docker/commands/index.html


6  history
   77  clear
   78  clear
   79  docker ps
   80  docker attach ubuntu
   81  docker attach dae3c3429941
   82  docker ps
   83  docker diff dae3c3429941
   84  clear
   85  docker images
   86  docker inspect jenkins
   87  clear
   88  docker ps
   89  docker inspect dae3c3429941
   90  clear
   91  docker ps -a
   92  docker rename 9eedf97622c6 rajesh
   93  docker ps -a
   94  docker run -d --name=rajesh1 jenkins
   95  docker ps -a
   96  clear
   97  docker ps
   98  docker logs 7cc1bee10ffc
   99  docker stats
  100  history
  101  clear
  102  docker stop $(docker ps -aq)
  103  docker rm $(docker ps -aq)
  104  clear
  105  ls
  106  docker images
  107  docker rmi jenkins
  108  clear
  109  ls
  110  docker images
  111  cd /var/lib/docker
  112  ls
  113  cd overlay2
  114  clear
  115  ls
  116  docker images
  117  docker history ubuntu
  118  docker inspect ubuntu
  119  clear
  120  ls
  121  df -kh
  122  docker run -itd ubuntu
  123  docker ps
  124  df -kh
  125  docker ps
  126  docker attach f81bb555767c
  127  find . -name rajesh.txt
  128  history
[root@ip-172-31-24-25 overlay2]#
==============================================================================
How the jenekins Image has been created....
jenkins
	openjdk:8-jdk
		buildpack-deps:stretch-scm
			buildpack-deps:stretch-curl
					debian:stretch
							scratch

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
===========================================
INSTRUCTIONS 		OPTIONS...


FROM ubuntu
MAINTAINER Rajesh Kumar DevOps@RajeshKumar.xyz
RUN apt-get update && apt-get install git

==============================
8  ls
  219  vi Dockerfile
  220  docker build -t image-ub-git .
  221  vi Dockerfile
  222  docker build -t image-ub-git .
  223  docker images


=============================
CMD Vs EntryPoint
----------------------
CMD can be replaced

ENRTYPOINT
	IT CAN NOT BE REPLACED.
	ANY INPUT WHICH YOU MAKE - ITS GET APPENDDED AS PARAMETE..
	docker run -d jenkins
	docker exec 7e03be18268b ps -eaf
	/bin/tini -- /usr/local/bin/jenkins.sh

	docker run jenkins sdfsf
	/bin/tini -- /usr/local/bin/jenkins.sh sdfsf



=============================================================
Docker volume
=============================================================
https://www.devopsschool.com/blog/understand-docker-volume-from-beginner-to-deep-dive-level/
	Types of Volume in Docker
	- volume
	- mount
	- memory




259  clear
  260  history
  261  docker stop $(docker ps -aq)
  262  docker rm $(docker ps -aq)
  263  clear
  264  docker ps -a
  265  docker volume ls
  266  cd 37ed6de5c8839387dc4186fd563d71fed25f3377187b28270914df84b3bedab6
  267  ls
  268  cd /var/lib/docker/volumes/
  269  ls
  270  cd 750b8145333cb479167cc6b3f6c125a114017ce6a7c35297c356bf8325d1a6c8
  271  ls
  272  cd _data/
  273  ls
  274  docker volume prune
  275  docker volume ls
  276  docker volume create common
  277  ls
  278  du -sh co
  279  ls
  280  cd ..
  281  ls
  282  pwd
  283  cd /var/lib/docker/volumes/
  284  ls
  285  du -sh
  286  du -sh common/
  287  docker run -itd ubuntu
  288  docker ps
  289  docker run -itd -v common:/opt/raj ubuntu
  290  docker ps
  291  docker attach 825f3a24f8aa
  292  ls
  293  cd common/
  294  ls
  295  cd _data/
  296  ls
  297  touch ffffff.txt
  298  docker attach 825f3a24f8aa
  299  docker ps -a
  300  docker stop 825f3a24f8aa ba7db6d6cd50
  301  docker rm 825f3a24f8aa ba7db6d6cd50
  302  cd ..
  303  cd ..
  304  ls
  305  ls
  306  docker volume ls
  307  pwd
  308  cd /opt/
  309  ls
  310  cd /tmp/
  311  ls
  312  mkdir devops
  313  ls
  314  pwd
  315  pwd
  316  cd devops/
  317  ls
  318  pwd
  319  ls
  320  pwd
  321  docker run -itd -v /tmp/devops:/opt/rr ubuntu
  322  docker ps
  323  ls
  324  ls
  325* touch fsfdsd
  326  touch fsdf fdsf dsf ds f sdf d f
  327  ls
  328  docker ps
  329  docker attach c5b5794f1090
  330  ls
  331  pwd
  332  history
===============================================================================
Docker Networking
===============
	3 TYPES OF NETWORKING
	- BRIDGE
	- HOST
	- NONE

334  docker network ls
  335  ifconfig
  336  docker network ls
  337  docker inspect 2ea7277a954e
  338  clear
  339  ls
  340  docker network dev ---driver=bridge
  341  docker network dev --driver=bridge
  342  docker network create dev --driver=bridge
  343  docker network ls
  344  docker inspect 6980e6af4062
  345  clear
  346  docker netowkr
  347  docker inspect 6980e6af4062
  348  docker network ls
  349  docker inspect 2ea7277a954e
  350  clear
  351  docker help network create
  352  docker network create qa --driver=bridge --subnet=172.20.0.0/16
  353  docker network ls
  354  docker inspect 4896002d36ad
  355  docker network ls
  356  docker run -itd --net=qa ubuntu
  357  docker ps
  358  docker inspect 926a46bc1fdb
  359  clear
  360  docker help run
  361  docker run -itd --net=qa --ip=172.20.0.20 ubuntu
  362  docker ps
  363  docker inspect bb6700da8f03
  364  docker ps
  365  docker stop bb6700da8f03
  366  docker start bb6700da8f03
  367  docker inspect bb6700da8f03
  368  history

NOne network
  366  docker start bb6700da8f03
  367  docker inspect bb6700da8f03
  368  history
  369  clear
  370  ls
  371  ifconfig
  372  docker run -itd --net=host ubuntu
  373  docker ps
  374  docker attach 9c632eddbbed
  375  docker network ls
  376  docker run -itd --net=none ubuntu
  377  docker attach 345ba812708f38a6d798b9ebe4e5344f5efc746327723dfddc11fb650229ae94
  378  docker attach 345ba812708f38a6d798b9ebe4e5344f5efc746327723dfddc11fb650229ae94
  379  history



172.17.0.0/16
172.18.0.0/16

172.20.0.0/16

172.20.0.2

172.20.0.20
```
