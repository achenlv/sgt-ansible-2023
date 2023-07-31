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


## Install Ansible on local Ubuntu 22.04 if pip3 install failed
```
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible -y
```
Then do example work
```
git clone https://github.com/achenlv/sgt-ansible-2023.git
cd sgt-ansible-2023
ansible-galaxy collection install -r requirements.yaml
ansible-playbook playbooks/task_local.yaml
```
Result should look like:
<pre>
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'

PLAY [Task2] **************************************************************************************************************************************************************

TASK [Gathering Facts] ****************************************************************************************************************************************************
ok: [localhost]

TASK [Execute the command in remote shell; stdout goes to the specified file on the remote] *******************************************************************************
changed: [localhost]

TASK [debug] **************************************************************************************************************************************************************
ok: [localhost] => {
    "ans_version.stdout_lines": [
        "ansible [core 2.15.2]",
        "  config file = /etc/ansible/ansible.cfg",
        "  configured module search path = ['/home/ange/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']",
        "  ansible python module location = /home/ange/.local/lib/python3.10/site-packages/ansible",
        "  ansible collection location = /home/ange/.ansible/collections:/usr/share/ansible/collections",
        "  executable location = /usr/bin/ansible",
        "  python version = 3.10.6 (main, May 29 2023, 11:10:38) [GCC 11.3.0] (/usr/bin/python3)",
        "  jinja version = 3.1.2",
        "  libyaml = True"
    ]
}

PLAY RECAP ****************************************************************************************************************************************************************
localhost                  : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
</pre>