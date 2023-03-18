# Ansible Modules

## What are Modules?

Ansible modules are pre-written code snippets that perform specific actions on managed nodes. They abstract away the underlying complexity, allowing you to focus on the desired state of your infrastructure. Ansible has hundreds of built-in modules that cater to various tasks, such as package management, file manipulation, and service control.

## Commonly Used Modules

Here are some commonly used Ansible modules:

- `ansible.builtin.command`: Executes a command on the managed node.
- `ansible.builtin.shell`: Executes a shell command on the managed node, with support for pipes and redirection.
- `ansible.builtin.copy`: Copies a file from the control node to the managed node.
- `ansible.builtin.template`: Creates a file on the managed node from a Jinja2 template.
- `ansible.builtin.fetch`: Retrieves a file from the managed node and stores it on the control node.
- `ansible.builtin.file`: Sets attributes of files, symlinks, and directories.
- `ansible.builtin.lineinfile`: Ensures that a particular line is present or absent in a file.
- `ansible.builtin.apt` / `ansible.builtin.yum` / `ansible.builtin.dnf`: Manages packages on Debian, Red Hat, or Fedora-based systems, respectively.
- `ansible.builtin.service`: Controls services using the system's service manager (e.g., systemd, sysvinit, or upstart).

You can find a complete list of Ansible modules in the official documentation: <https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html>

## Installing and Managing Packages

Package management is a common task in infrastructure automation. In this example, we'll create a playbook that installs the Nginx web server on a group of hosts called "web":

```yaml
---
- name: Install Nginx on web servers
  hosts: web
  become: yes
  tasks:
    - name: Ensure Nginx is installed
      ansible.builtin.apt:
        name: nginx
        state: present
```

The `ansible.builtin.apt` module is used to ensure that the Nginx package is installed on the target hosts. For Red Hat-based systems, replace `ansible.builtin.apt` with `ansible.builtin.yum` or `ansible.builtin.dnf`, as appropriate.

## Managing Files and Directories

File and directory management is another essential task in infrastructure automation. Let's create a playbook that sets up a directory structure and a configuration file for a custom application:

```yaml
---
- name: Set up application directories and configuration
  hosts: all
  become: yes
  tasks:
    - name: Create application directories
      ansible.builtin.file:
        path: "/opt/{{ item }}"
        state: directory
        owner: appuser
        group: appuser
        mode: 0755
      loop:
        - myapp
        - myapp/data
        - myapp/logs

    - name: Deploy application configuration file
      ansible.builtin.template:
        src: app_config.j2
        dest: /opt/myapp/app_config.ini
        owner: appuser
        group: appuser
        mode: 0644
```

The `ansible.builtin.file` module is used to create the required directories, while the `ansible.builtin.template` module deploys the configuration file using a Jinja2 template (`app_config.j2`).

## Managing Services

Managing services is another crucial aspect of infrastructure automation. In this example, we'll create a playbook that starts the Nginx service and enables it to start at boot:

```yaml
---
- name: Manage Nginx service
  hosts: web
  become: yes
  tasks:
    - name: Ensure Nginx service is running
      ansible.builtin.service:
        name: nginx
        state: started
        enabled: yes
```

The `ansible.builtin.service` module is used to start the Nginx service and enable it to start at boot on the target hosts. This module is compatible with various service managers, such as systemd, sysvinit, and upstart, and automatically detects the appropriate manager for the managed node.

## Using Custom Modules

While Ansible has a vast library of built-in modules, there might be cases where you need to create your own custom module to perform specific tasks. Custom modules can be written in any language that returns JSON output, though Python is the most common choice due to its extensive standard library and compatibility with the Ansible ecosystem.

To create a custom module:

1. Write the module code in a file with the desired module name (e.g., `my_module.py`).
2. Place the module file in a `library` directory within your Ansible project or in a directory specified by the `library` configuration option in your `ansible.cfg` file.
3. Use the custom module in your playbooks like any other Ansible module.

For more information and best practices on writing custom modules, refer to the official Ansible documentation: <https://docs.ansible.com/ansible/latest/dev_guide/developing_modules_general.html>

In this chapter, we've covered the basics of Ansible modules, including commonly used modules for package management, file manipulation, and service control. Modules are the building blocks of Ansible playbooks, allowing you to define the desired state of your infrastructure in an abstract and straightforward manner. In the next chapter, we'll explore Ansible roles, a powerful feature that enables you to organize and reuse your Ansible code more effectively.
