# Ansible lab2 homework
## Execute lab works on local computer

Example:
```
#!/usr/bin/env bash
# install necessary modules
ansible-galaxy collection install -r requirements.yaml
```
### run playbook locally
Option1: Provide local connection in playbook command
```
ansible-playbook  --connection=local \
        playbooks/task5.yaml
```
Option2: provide connetion in playbook file
```
ansible-playbook  playbooks/task5.yaml
```
```
---
- name: Task2
  connection: local
  tasks:

```

## Extra task
Use when condition to execute some task out of all in playbook


Useful links
[https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_delegation.html#local-playbooks]
[https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_conditionals.html]
