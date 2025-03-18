# Virtual Machine State

This is my virtual machine setup.
It is expected to work on both x86_64 and aarch64 Debian Linux of versions 10 to 12.
Note that this is a complete development environment that takes a significant amount of disk space (~20GB).

# Known Issues

- after installing `nvm` it is necessary to restart Ansible playbook because `npm` community modules cannot find it right after installation

# Table of Contents

<!-- mtoc start -->

- [Setup](#setup)

<!-- mtoc end -->

# Setup

1. Install Ansible.
   Ansible version >= 2.13.9 is required.

   - use either `pipx` (recommended)

     ```bash
     pipx install --include-deps ansible
     ```

   - or use `pip`

     ```bash
     python3 -m pip install --user ansible
     ```

2. Install Ansible dependencies.

   ```bash
   ansible-galaxy collection install community.general
   ```

   In case you do not have Ansible of version >= 2.13.9 you can still try the following command:

   ```bash
   ansible-galaxy install -r requirements.yml --server="https://old-galaxy.ansible.com" --ignore-certs
   ```

3. Create and edit your configuration.

   ```bash
   cp ./config.json.example ./config.json
   ```

4. Run the playbook.

   ```bash
   ansible-playbook src/bootstrap.yaml --extra-vars="@config.json" --ask-become-pass
   ```
