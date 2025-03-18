# Setup

1. Install Ansible.

   ```bash
   pipx install --include-deps ansible
   ```

1. Install Ansible dependencies.

   ```bash
   ansible-galaxy collection install community.general
   ```

1. Create and edit your configuration.

   ```bash
   cp ./config.json.example ./config.json
   ```

1. Run the playbook.

   ```bash
   ansible-playbook bootstrap.yaml --extra-vars="@config.json"
   ```
