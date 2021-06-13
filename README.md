# tomcat-standalone

Reference:

Ansible Modules:
https://docs.ansible.com/ansible/2.8/user_guide/modules_intro.html

Ansible Vault:
https://docs.ansible.com/ansible/latest/user_guide/vault.html

`ansible-vault encrypt group_vars/main.yml` <br />
`ansible-vault decrypt group_vars/main.yml` <br />

`ansible-playbook -i production site.yml --ask-vault-pass` <br />
`ansible-playbook -i production site.yml --vault-password-file .mypass` <br />

Integrated this repo with Jenkins CI/CD pipeline and the the below git repo (Rel branch):
https://github.com/akmaharshi/petclinic <br />
Jenkins file location: https://github.com/akmaharshi/petclinic/blob/rel/Jenkinsfile

Jenkins credentials-binding Plugin:
https://www.jenkins.io/doc/pipeline/steps/credentials-binding

Pipeline Syntax:
https://www.jenkins.io/doc/book/pipeline/syntax

# group_vars/main.yml
admin_password: <br />
TOMCAT_HOME: /usr/share/tomcat <br />
NEXUS_PASS: <br />

# Make jenkins user to run sudo commands
`vi /etc/sudoers`

jenkins		ALL=(ALL)	NOPASSWD: ALL

# Launch AWS Instance
Use the file aws-launch.yml for launching AWS EC2 instance:

`ansible-playbook -i production aws-launch.yml` <br />

Even you have boto installed and still getting error "boto module is required", execute the below command:

`ansible-playbook -i localhost, aws-launch.yml --extra-vars "ansible_python_interpreter=/usr/bin/python3"`

Edit the below properties in the "groups/all" file: <br />

`ec2_access_key:` <br />
`ec2_secret_key:` <br />
`ec2_keypair: ohio` <br />
`ec2_security_group:` <br />
`ec2_instance_type: t2.micro` <br />
`ec2_image: ami-077e31c4939f6a2f3` <br />
`ec2_region: us-east-2` <br />
`ec2_instance_count: 2` <br />

### We need to install boto3 to execute aws-launch.yml script which is a pre-requisite
Make sure you have python3 installed <br />
`python3 --version`

Download pip <br />
`curl -O https://bootstrap.pypa.io/get-pip.py`

Execute pip script <br />
`python3 get-pip.py`

Ensure pip is installed successfully <br />
`pip --version`

Install boto3 and boto using pip <br />
`pip install boto3` <br />
`pip install boto`
