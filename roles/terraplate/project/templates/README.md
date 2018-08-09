## {{ project_name }}

## Running

### Create a Module


### Create a Config


### Create a Plan


## Misc

### Default values

cli values can be set in the inventory file
terraplate values can bet set in host_vars/terraplate.yml

### Secrets

When this project was create a UUID was generated as a password for encryping values in this project
The value can be found/changed in project_root/.vault-password.txt
The .vault-password file is in .gitignore so it will not be accidentally committed to the repo


## Credits

The [excellent ansible prompt module](https://github.com/andrewvaughan/ansible-role-prompt)
