
## Create a New Project



new.yml calls a setup/config role. The setup/config role:
1: does a check for binaries. if they don't exist and it is a debian system then it installs the binaries
2: user can define version vars if they want a different version
3: setup checks for vault-password.txt in root of project dir. if it doesn’t exist it creates a new one and updates ansible.cfg by uncommenting the # in front of ansible-vault
4: then it calls new on the component
5: copies over group_vars/all/terraplate.yml if it doesn’t exist
6: creates inventory/{{ config.application_name }}
7: it copies over .gitignore from application/templates/ansible

