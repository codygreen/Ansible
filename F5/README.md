## Description
This is an example of deploying F5s in AWS and using Declarative Onboarding (DO) and Application Services 3 (AS3) Extensions via Ansible to provision a BIG-IP in a declarative manner.

### Commands

#### Deploy BIG-IP
ansible-playbook deploy_bigip.yaml --vault-password-file ./group_vars/aws_ec2/vault_pass.txt

#### Get Inventory 
ansible-inventory -i f5.aws_ec2.yaml --graph

#### Create AS3 Declaration
ansible-playbook create_app.yaml -e "@app-inputs/App1.yaml"

#### Deploy Application
ansible-playbook -i f5.aws_ec2.yaml push_config.yaml --vault-password-file ./group_vars/aws_ec2/vault_pass.txt
