<h1>linux_joindomain</h1>
This is an ansible role to automaticaly join Linux Machine CentOS and Redhat using sssd, realm, samba and winbind. This role is tested on RedHat/CentOS 7.x, 8.x 6.6 and Ubuntu 22 20 18 16 and Debian 10 9

Note RH6 support has been dropped.

# Requirements

- source.list configured and updated for debian servers
- Ansible >= 2.7

# Installation

ansible-galaxy install mahdi22.linux_joindomain

# Role Configuration

file: defaults/main.yml
```yaml
#set this variable to True if the managed hosts are bihind a web proxy... default False
use_proxy: False
```
```yaml
proxy_env: []
#Set environmenet variable for web proxy sexample:
#  proxy_env:
#  http_proxy: http://proxy.local:8080/
#  https_proxy: http://proxy.local:8080/
```

# Role Variables

file: vars/main.yml
```yaml
Join_User: ADMDOMAIN # Replace ADMDOMAIN with the username domain admin
DomainName: linuxlab.local # Replace linuxlab.local with the domainname
Join_User_Pass: admdomainpassword # Replace admdomainpassword with the username domain admin password
realm: LINUXLAB.LOCAL # replace this value with by Domaine Name
server: linuxlab.local # replace this value with by active directory server
```
   
 # Example Playbook
```yaml
- hosts: servers
  roles:
    - role: mahdi22.linux_joindomain
      become: yes
```

## Testing

This role is tested on Linux distributions:

- RHEL/CentOS/Rocky 7/8/9
- Debian 8/9/10
- Ubuntu 22.04
- Ubuntu 20.04
- Ubuntu 19.10
- Ubuntu 18.04
- Ubuntu 16.04
