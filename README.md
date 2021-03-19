# tomcat-standalone

Reference:

Ansible Modules:
https://docs.ansible.com/ansible/2.8/user_guide/modules_intro.html

Ansible Vault:
https://docs.ansible.com/ansible/latest/user_guide/vault.html

ansible-vault encrypt group_vars/main.yml <br />
ansible-vault decrypt group_vars/main.yml <br />

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
vi /etc/sudoers

jenkins		ALL=(ALL)	NOPASSWD: ALL
