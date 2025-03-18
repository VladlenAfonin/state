# Virtual Machine State

This is my virtual machine setup. It is expected to work on both x86_64 and aarch64 Debian Linux of versions 10 to 12. Note that this is a complete development environment that takes a significant amount of disk space (~20GB).

# Known Issues

- after installing `nvm` it is necessary to restart Ansible playbook because `npm` community modules cannot find it right after installation

# Table of Contents

<!-- mtoc start -->

- [Setup](#setup)

<!-- mtoc end -->

# Setup

1. Install Ansible.

   ```bash
   pipx install --include-deps ansible
   ```

2. Install Ansible dependencies.

   ```bash
   ansible-galaxy collection install community.general
   ```

3. Create and edit your configuration.

   ```bash
   cp ./config.json.example ./config.json
   ```

4. Run the playbook.

   ```bash
   ansible-playbook src/bootstrap.yaml --extra-vars="@config.json" --ask-become-pass
   ```
