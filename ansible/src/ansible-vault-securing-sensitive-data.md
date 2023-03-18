# Ansible Vault: Securing Sensitive Data

## Introduction to Ansible Vault

Ansible Vault is a built-in feature that allows you to encrypt sensitive data, such as passwords, API keys, and certificates, within your Ansible projects. By using Ansible Vault, you can protect sensitive information from unauthorized access while still being able to use it in your playbooks and templates.

## Creating an Encrypted File

To create a new encrypted file with Ansible Vault, use the `ansible-vault create` command followed by the desired file name:

```bash
ansible-vault create secrets.yml
```

You'll be prompted to enter a password that will be used to encrypt and decrypt the file. After entering the password, a text editor will open, allowing you to edit the file. Once you save and exit the editor, the file will be encrypted using the provided password.

## Editing an Encrypted File

To edit an existing encrypted file, use the `ansible-vault edit` command followed by the file name:

```bash
ansible-vault edit secrets.yml
```

You'll be prompted to enter the password used to encrypt the file. The file will be decrypted, opened in a text editor, and re-encrypted when you save and exit the editor.

## Encrypting an Existing File

To encrypt an existing plaintext file, use the `ansible-vault encrypt` command followed by the file name:

```bash
ansible-vault encrypt secrets.yml
```

You'll be prompted to enter a password that will be used to encrypt the file. The file will be encrypted in place, replacing the original plaintext content.

## Decrypting an Encrypted File

To decrypt an encrypted file, use the `ansible-vault decrypt` command followed by the file name:

```bash
ansible-vault decrypt secrets.yml
```

You'll be prompted to enter the password used to encrypt the file. The file will be decrypted in place, replacing the encrypted content with the original plaintext content.

## Changing the Encryption Password

To change the password used to encrypt a file, use the `ansible-vault rekey` command followed by the file name:

```
ansible-vault rekey secrets.yml
```

You'll be prompted to enter the current password and the new password for the file. The file will be re-encrypted using the new password.

## Using Encrypted Files in Playbooks and Roles

To use an encrypted file in your playbooks and roles, include it as you would include a regular file, using the `include_vars`, `vars_files`, or other mechanisms for loading variables. When running the playbook, you'll need to provide the encryption password using the `--ask-vault-pass` or `--vault-password-file` command-line options.

For example, let's create a playbook that uses an encrypted file containing sensitive data:

```yaml
---
- name: Deploy an application with sensitive data
  hosts: app_servers
  tasks:
    - name: Include sensitive data
      ansible.builtin.include_vars:
        file: secrets.yml

    - name: Deploy configuration file with sensitive data
      ansible.builtin.template:
        src: app_config.j2
        dest: /etc/app/config.ini
```

To run the playbook, use the `ansible-playbook` command with the `--ask-vault-pass` option:

```bash
ansible-playbook deploy_app.yml --ask-vault-pass
```

Alternatively, you can use the `--vault-password-file` option to specify a file containing the encryption password:

```bash
ansible-playbook deploy_app.yml --vault-password-file vault_password.txt
```

In this chapter, we've explored Ansible Vault, a powerful tool for managing sensitive data in your Ansible projects. By using Ansible Vault, you can ensure that sensitive information, such as passwords, API keys, and certificates, is protected from unauthorized access while still being usable in your playbooks and templates.

## Best Practices for Managing Vault Passwords

While using Ansible Vault, it is important to follow some best practices for managing the vault passwords.

1. Don't store vault passwords in your version control system. Instead, store them securely using a password manager, a secret management tool, or an environment variable in your CI/CD system.

2. Use different vault passwords for different environments (e.g., development, staging, and production) to minimize the impact of a compromised password.

3. Regularly rotate vault passwords to reduce the risk of unauthorized access.

4. When working with multiple vault files, consider using a single password for all files or use a script to manage multiple passwords.

5. Implement a proper process for sharing and distributing vault passwords among team members, such as using a password manager with team sharing functionality or a secret management tool with access control.

In this guide, we've explored Ansible Vault, a powerful tool for managing sensitive data in your Ansible projects. By using Ansible Vault, you can ensure that sensitive information, such as passwords, API keys, and certificates, is protected from unauthorized access while still being usable in your playbooks and templates.

In the next chapter, well explore ansible best practices.
