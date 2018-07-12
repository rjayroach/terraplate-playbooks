# Terraplate

## Projects

A project is a user defined logical grouping of related cloudy resources, for example, everything needed to bring up an application in a K8s cluster on AWS.
Projects are stand-alone entities that contain all the relevant user configuation to realize the infrastructure.

### Applications

A project consists of one or more applications. An Application is a logical subset of resources needed to realize the overall project
For example the 'admin' application may contain one off DNS configuration of a domain and certain records, e.g. MX record for a domain
remote Git repositories to store the application code and SSH key generation for cloud servers

#### Artifacts

application.yml
globals.yml


### Environments

Most applications will have identical infrastructure resources with variations between environments for, e.g. development, staging and production.
Terraplate offers easy swapping of resource values based on the current configuration environment

### Services

Applications are composed of one or more services such as DNS, Git Repositories and SSH Key generation.
Services invoke Library Components in order to render the necessary Terraform artifacts

#### Artifacts

user playbook: project/playbooks/app/backend/network.yml
user playbook vars (manifest): project/playbooks/app/backend/network-vars.yml
user playbook env vars (manifest env): project/inventory/development/host_vars/app-backend-network.yml

##### Mapping hosts to environment variables

The value of hosts is mapped to a single instance of a 'component'
 if multiple components are needed then multiple hosts are defined
 so that host_vars can be defined indepednetly for each instance

```yaml
#!/usr/bin/env ansible-playbook
---
- name: Template an EC2
  hosts: app-backend-compute
```

## Library

### Components

Components bundle a set of related cloud resources. For example a DNS Zone component will encompass one TF aws_route53_zone and 
as many aws_route53_record resources as necessary for the Service configuration

### Artifacts

component tasks: roles/aws/vpc/tasks/public-only-subnet.yml


### Resources

### Artifacts

resource tasks: roles/aws/vpc/vpc/tasks/main.yml
resource vars: roles/aws/vpc/vpc/vars/main.yml
resource tasks: roles/aws/vpc/subnet/tasks/main.yml
resource vars: roles/aws/vpc/subnet/vars/main.yml


### Providers


## Terraplate Roles

### Application

### Component

### Resource

### Utils
