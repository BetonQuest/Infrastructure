# BetonQuest Infrastructure

This project details the processes involved in setting up our self-managed infrastructure.

It is implemented via [Ansible](https://docs.ansible.com/projects/ansible/latest/index.html).

To set up the server just run:
```shell
ansible-playbook playbooks/setup.yaml --check # to verify what would be changed
ansible-playbook playbooks/setup.yaml # to apply the changes
```

## Secrets

There are some secrets that need to be configured, but they must not be commited.

To provide these secrets you can choose one of multiple options:

* set them via `-e` / `--extra-vars`
* put them into `inventory/group_vars/all/secrets.yaml`
* put them in a secure file outside the project directory and provide the file via `-e @path/to/file.yaml`

For the file-based variants you can use [Ansible vault](https://docs.ansible.com/projects/ansible/latest/vault_guide/index.html) to encrypt the secrets locally.

To skip all tasks that require secrets you can use `--skip-tags secret-required`
