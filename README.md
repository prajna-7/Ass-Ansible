# Ass-Ansible


#Pre-requisite for setting up the localhost or any VM in order to test the ansible playbook#

git clone https://github.com/prajna-7/Ass-Ansible

#Move into that directory#

cd Ass-Ansible

#Then move into ssh directory#

cd ssh_configurations

#Now copy all the files to ~/.ssh diectory#

cp * ~/.ssh

#Now move into ~/.ssh directory#

#Now change the permissions of ssh keys#

chmod 400 BastionNSO.pem
chmod 400 devA.pem
chmod 400 devB.pem
chmod 400 devC.pem
chmod 400 haproxy.pem

#To see if the ssh configuration is all set#

nano config

#Make sure all the private keyfile path are accurate then ssh to each host to verify if they are accessible.#

#It is necessary to do that in order to run playbook successfully#

ssh BastionNSO
ssh haproxy
ssh devA
ssh devB
ssh devC

#Note: all webservers are only accessible through BastionNSO and can't access directly as they are in private subnet.#

#Now install Ansible by running following commands#

sudo apt update

sudo apt install software-properties-common

sudo add-apt-repository --yes --update ppa:ansible/ansible

sudo apt install ansible


#Now move into the directory you clone from github#

#Check the path of the application.py and haproxy.cfg.j2 is accurate otherwise set it according to its location in you host by running following command#

nano site.yaml

#Now run the command to play ansible playbook#

ansible-playbook -i hosts site.yaml
