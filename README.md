#NOTE all below steps are to aid in forming your own images. 
#The names/values change depending on when the note was added. 
#Software version will change, names should be your own, etc.

#Software environment/dependancies: Git, Docker.
#Have your own github account and docker account
#The following example is to be run on your own laptop.
#If a server is used, we need to vary the ports to prevent port conflicts.
#The point is to develop an understanding of docker, not create a usable product.
#The author points out that the users would pull the offical tomcat image rather than making one themselves. 

#Download files

git clone https://github.com/leefrankpierce/docker_training

#Cd into the cloned repo and find the Dockerfile, update to your usage. 
#Update the Node JS for your usage.

#docker build
#Please change to your own name, the period at the end is important
#"docker build", Cleanup "--t", Name the image "-t", look in the current dir for a Dockerfile "."

docker build --rm -t centos-tomcat-leedogs:v2.1 . 
#Run the image in the local docker environment (desktop) 
#"docker run", name the container "--name", create a termninal "-it", map ports from laptop to into docker "-dp", image to run

docker run --name dog -it -dp 8888:8080 centos-tomcat-leedogs:v2.1  
#From a web browser "localhost" is your laptop, Port mapped above ":", Path to trigger tomcat.

http://localhost:8888/leeJS/
#or if running from a server

http://server IP:8888/leeJS/

#To log into the running container.

docker attach dog
#What docker containers are running, stopping and cleaning up.

docker ps -a

docker stop b461816a7b69

docker rm $(docker ps -a -q)

#Upload to dockerhub
#determine what images are local to your docker environment.
#The author finds the column names confusing, but just roll with it.

docker image ls

REPOSITORY              TAG       IMAGE ID       CREATED         SIZE

ubuntu-tomcat-leedogs   V1.1      ce02eec7376d   8 minutes ago   680MB

#Log into Docker hub. This connection remains for your session.
#Expectations = you are logging into your own docker account.

docker login 

#Tag or alias the image pointing to the dockerhub repo. Docker commands presume dockerhub. 
#The idea is to make a "tag" that tells dockerhub were to place the image.
#This should include your personal repo and whatever you want to call your image
#docker image tag, "name found in above ls command", "dockerhub repository name/", image name with version. 

docker image tag ubuntu-tomcat-leedogs:V1.1 leefrankpierce/leedogs:40

docker image ls
#See the new tag local to your docker environment.
#Push the image to dockerhub
#docker image push "name you created when making the tag"

docker image push leefrankpierce/leedogs:40
