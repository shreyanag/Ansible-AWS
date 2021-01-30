# Ansible-AWS
Creation of ec2 instance using ansible YAML scripts
#######
pre requisite install ansible,python,boto,boto3 

#####create ansible user and add it in /etc/sudoers
#####MAke password authention as yes in /etc/sshd/ssh_config file and then restart service sshd restart
####
Create the Ansible directory structure mkdir -p AWS_Ansible/group_vars/all/ cd AWS_Ansible touch playbook.yml

ansible-vault create group_vars/all/pass.yml
New Vault password: 
Confirm New Vault password:

openssl rand -base64 2048 > vault.pass
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass

ansible-vault edit group_vars/all/pass.yml
Vault password:
ec2_access_key:access key
ec2_secret_key: secret key

AWS_Ansible tree . ├── group_vars
                       │ └── all
                           │ └── pass.yml
                   └── playbook.yml
2 directories, 2 files

ansible-playbook playbook.yml --ask-vault-pass
