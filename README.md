This assignment deploys a python application, HAProxy and nginx as UDP loadbalancer using Ansible on 3 different servers. The deployment consists of three web servers and one load balancer running HAProxy and nginx with another server acting as a Bastion host for SSH access to all the other hosts.

The Ansible playbook (site.yaml) assumes that the necessary servers are already created and that SSH keys are configured for passwordless SSH access between the Bastion host and the other hosts. The playbook can be run outside of the site but via the Bastion host using an SSH config file that allows the host to use the Bastion host as a jump host.

The site.yaml playbook can be customized to specify user names, SSH key paths, python application settings, nginx configurations and other variables as needed.
