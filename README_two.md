# Jenkins
```
docker container exec -u 0 -it mycontainer bash
#if you want to switch to container as root
```
How to give access to user in repo and add repo to jenkins

create deployer user on server2
adduser and generate key ssh-keygen

1. copy deployer user public key and paste in jenkins user on server1 and
2. also paste public key of deployer user in bitbucket setting ssh access.

git clone with SSH on server 2.

Now you have access on bitbucket with deloyer user with ssh.
```
if you are not able to switch to jenkisn user
sudo usermod -s /bin/bash jenkins
```
3. add public key of jenkins user in bitbucket.

## To give access to repo to jenkins

4. COPY public key pf jenkins and paste in bitbucket Repository settings ==> Access keys ==> paste public key of jenkins

5. add private key of jenkins user in jenkins credentials GUI www.jenkins.com

su - jenkins ===> ssh deployer@server2  # you have already add public key of deployer user in jenkins server

## For bitbucket 

Job Name ==> Source Code Management ==> Git ==> Repository URL <SSH link>
git@bitbucket.org:gauravsonu/maven-project.git

# Ansible

server 3 => ansible

server 2 => deployer
paste public key of ansible server 3 into deployer server 2. So that you can access  deployer server 2 without password.

on ansible server in the /etc/ansible/hosts file eneter IP of deployer server 2. If you are using particular user example deployer then you have to enter "ansible_user=user_name_of_deployer_server_2" to tell ansible to check that particular user.
```
[deployer]
IP ansible_user=user_name_of_deployer_server_2
```



