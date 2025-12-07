# BetonQuest Infrastructure

This project details the processes involved in setting up our self-managed infrastructure.

It is implemented via [Ansible](https://docs.ansible.com/projects/ansible/latest/index.html).

To set up the server just run:
```shell
ansible-playbook playbooks/setup.yaml --diff --check # to verify what would be changed
ansible-playbook playbooks/setup.yaml # to apply the changes
```
