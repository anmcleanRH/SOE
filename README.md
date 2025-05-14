# RHEL9 SOE Ansible Automation

This repository contains modular Ansible roles to configure a Red Hat Enterprise Linux 9 Standard Operating Environment (SOE). It is intended for integration with Red Hat Satellite or used independently via the `site.yml` playbook.

## Features

- Active Directory join using `realm`
- Chrony/NTP configuration from group variables
- YubiKey and FIDO2 authentication setup
- Fapolicyd custom rule enforcement
- Optional integrations for:
  - LibreNMS
  - Nessus
  - Azure Backup
  - Veeam Agent
- OpenSCAP security hardening (ISM profile)
- Encrypted variable support using Ansible Vault
- Logging

## Usage

1. Clone the repository
2. Customize `inventory/hosts.yml` and `group_vars/all.yml`
3. Ensure `vault/secrets.yml` is created and encrypted:
   ```bash
   ansible-vault encrypt vault/secrets.yml
   ```
4. Run the playbook:
   ```bash
   ansible-playbook -i inventory site.yml --ask-vault-pass
   ```

## Directory Structure

```
.
├── ansible.cfg
├── inventory/
├── group_vars/
├── vault/
├── site.yml
└── roles/
```

## Requirements

- Ansible 2.12+
- Access to Red Hat repositories (via Satellite or RHSM)
- Vault password for secrets

## License

MIT or your organization’s internal license.
