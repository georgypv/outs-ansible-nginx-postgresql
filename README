## Sample Ansible playbook to install and configure nginx and postgres

Before running the playbook, make sure that you have your VMs running and modify hosts in inventory.yaml.


To make a 'dry run' of the playbook, use the command: `ansible-playbook -i inventory.yaml playbook.yaml` --check

When you are sure that everything is correct, run the same command without `--check` flag:

`ansible-playbook -i inventory.yaml playbook.yaml`


The playbook installs nginx and postgres (with additional dependencies) via apt, psycopg2 via pip and creates a user, a sample database and an empty table in Postgres.
