# Working with Ansible Roles

## Introduction to Ansible Roles

Ansible roles are a way to group related tasks, variables, files, and templates into a reusable and shareable format. Roles promote reusability, modularity, and separation of concerns in your infrastructure automation. They also make it easier to manage complex playbooks by breaking them down into smaller, more focused components.

## Role Directory Structure

A typical role directory structure consists of several subdirectories:

- `tasks`: Contains the main list of tasks to be executed.
- `handlers`: Contains handlers that are invoked by tasks.
- `vars`: Contains role-specific variables.
- `defaults`: Contains default variables with the lowest precedence.
- `files`: Contains files that can be deployed using the `copy` or `template` modules.
- `templates`: Contains Jinja2 templates that can be deployed using the `template` module.
- `meta`: Contains metadata about the role, such as dependencies and supported platforms.

A role named `my_role` would have the following directory structure:

```css
my_role/
  ├── tasks/
  │   └── main.yml
  ├── handlers/
  │   └── main.yml
  ├── vars/
  │   └── main.yml
  ├── defaults/
  │   └── main.yml
  ├── files/
  ├── templates/
  └── meta/
      └── main.yml
```

## Creating a Basic Role

To create a role, first, create a directory named `roles` in your Ansible project. Then, create a new directory for your role using the desired name (e.g., `my_role`). Finally, create the necessary subdirectories and files for your role, as described in the previous section.

For example, let's create a role that installs and configures Nginx on a group of web servers:

- Create the role directory structure:

  ```bash
  mkdir -p roles/nginx/{tasks,handlers,vars,defaults,files,templates}
  ```

- Define the tasks in `roles/nginx/tasks/main.yml`:

  ```yaml
  ---
  - name: Install Nginx
    ansible.builtin.apt:
      name: nginx
      state: present

  - name: Deploy Nginx configuration
    ansible.builtin.template:
      src: nginx.conf.j2
      dest: /etc/nginx/nginx.conf
    notify: Restart Nginx
  ```

- Define the handler in `roles/nginx/handlers/main.yml`:

  ```yaml
  ---
  - name: Restart Nginx
    ansible.builtin.service:
      name: nginx
      state: restarted
  ```

- Add a configuration template to `roles/nginx/templates/nginx.conf.j2`:

  ```bash
  user www-data;
  worker_processes auto;
  pid /run/nginx.pid;

  events {
    worker_connections 768;
  }

  http {
    # ...
  }
  ```

- Use the role in a playbook:

  ```yaml
  ---
  - name: Configure web servers
    hosts: web
    become: yes
    roles:
      - nginx
  ```

## Role Variables and Defaults

Roles can have their own variables and defaults. Variables are defined in the `vars` directory, while defaults are defined in the `defaults` directory. Variables in the `defaults` directory have the lowest precedence and can be easily overridden by other sources, such as inventory variables or command-line arguments.

For example, let's add a default variable for the Nginx worker processes in our `nginx` role:

- Define the default variable in `roles/nginx/defaults/main.yml`:

  ```yaml
  ---
  nginx_worker_processes: auto
  ```

- Use the variable in the `roles/nginx/templates/nginx.conf.j2` template:

  ```bash
  user www-data;
  worker_processes {{ nginx_worker_processes }};
  pid /run/nginx.pid;

  events {
    worker_connections 768;
  }

  http {
    # ...
  }
  ```

Now, the number of worker processes is controlled by the `nginx_worker_processes` variable, which can be overridden as needed.

## Role Dependencies

Roles can have dependencies on other roles, which allows you to create modular, reusable components that build upon each other. Role dependencies are defined in the `meta/main.yml` file of a role.

For example, let's create a new role called `my_app` that depends on the `nginx` role:

- Create the role directory structure:

  ```bash
  mkdir -p roles/my_app/{tasks,meta}
  ```

- Define the tasks in `roles/my_app/tasks/main.yml`:

  ```yaml
  ---
  - name: Deploy application files
    ansible.builtin.copy:
      src: "{{ item }}"
      dest: /var/www/my_app/
    loop:
      - index.html
      - app.js
  ```

- Define the role dependencies in `roles/my_app/meta/main.yml`:

  ```yaml
  ---
  dependencies:
    - nginx
  ```

Now, when you include the `my_app` role in a playbook, the `nginx` role will be executed first, followed by the tasks in the `my_app` role.

## Sharing and Reusing Roles

Roles can be easily shared and reused across projects, either by copying the role directory or by using Ansible Galaxy, a centralized repository for Ansible roles. You can publish your own roles to Ansible Galaxy or install roles created by others.

To install a role from Ansible Galaxy, use the `ansible-galaxy` command:

```bash
ansible-galaxy install username.role_name
```

For example, to install the `geerlingguy.nginx` role:

```bash
ansible-galaxy install geerlingguy.nginx
```

Installed roles are stored in the default roles directory (`~/.ansible/roles`) or the directory specified by the `roles_path` configuration option in your `ansible.cfg` file.

In this chapter, we've explored Ansible roles, a powerful way to organize and reuse your Ansible code. By using roles, you can create modular, maintainable, and shareable components that simplify the management of complex infrastructure automation tasks. In the next chapter, we'll discuss Ansible inventory, an essential component for targeting and configuring your managed nodes.
