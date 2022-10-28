## Sample Ansible playbook to install and configure nginx and postgres

Before running the playbook, make sure that you have your VMs running and modify hosts in inventory.yaml accordingly.

Modify, if needed, the contents of ansible.cfg file which contains following default variables:
 - inventory = default inventory file
 - remote_user = default root user when connecting to a VM
 - host_key_checking = whether to ask for permission before connection
 - DEFAULT_VAULT_PASSWORD_FILE = file with ansible-vault password which is needed to decrypt secret variables

Variables which contain sensitive information like `user_name_pg` and `user_password_pg` are hidden with `ansible-vault encrypt_string` command. Password for encryption-decryption of these variables should be written into a file which is indicated with DEFAULT_VALUT_PASSWORD_FILE variable in `group_vars/otusvms`.

To make a 'dry run' of the playbook, use the command: `ansible-playbook playbook.yaml --check`

When you are sure that everything is correct, run the same command without `--check` flag:

`ansible-playbook playbook.yaml`

The playbook installs nginx and postgres (with additional dependencies) via apt, psycopg2 via pip and creates a user, a sample database and an empty table in Postgres.
