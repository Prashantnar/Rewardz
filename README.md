# Rewardz
first i have launch three vm first for ansible configuration and other two as a node
i have configured ansible user in all machine
i have given hosts in ansible hosts file
generated ssh-key in ansible controller for other nodes
i have copied key in other nodes
i have clone Rewardz git repo in my ansible controller and have executed command "ansible-playbook ansible-playbook.yaml"
in this step i have created one dockerfile in that i have created database to store all these data and have taken database image mysql:5.7
after this i have created volumes to store this persistant data and restarted the database after that i have some environments and user ,password .
then i have taken wordpress image that open on port 80 and created environment with user and password, and it opens on port no 3306.
after this dockerfile i have created an ansible playbook  in this playbook i done following conf.
1) given host ip , given permission to become- root user, configured with ansible user with ssh connection
2) after this i done docker installation with yum module and started the docker with service module.
3) in shell i have first install docker-compose and given chmod permission 
4) after this given docker compose down to remove running container 
5) docker system prune -af to remove all services
6) rm -rf * to remove all the containt which are present 
7) after this i have copied my "docker-compose.yaml" file in my hosts 
8) and again in shell i have given "docker-compose up -d" to run these docker-compose
