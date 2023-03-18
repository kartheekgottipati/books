# Ansible Templating with Jinja2

## Introduction to Jinja2

Jinja2 is a powerful templating engine for Python that allows you to generate dynamic content based on variables, control structures, and other elements. Ansible uses Jinja2 as its default templating engine, enabling you to create dynamic configuration files, scripts, and other resources.

## Basic Jinja2 Syntax

Jinja2 templates consist of plain text interspersed with special tags for variables, control structures, and expressions. The basic tags used in Jinja2 templates are:

- `{{ variable }}`: Renders the value of a variable.
- `{% control_structure %}`: Defines a control structure (e.g., loops or conditional statements).
- `{# comment #}`: Adds a comment that is not rendered in the final output.

## Variables and Filters

Variables are a fundamental part of Jinja2 templates. They represent dynamic values that are passed to the template by Ansible. You can use variables to customize the content of your templates based on the desired state of your infrastructure.

In addition to variables, Jinja2 also supports filters that allow you to modify variable values before rendering them in the template. Filters are applied using the `|` (pipe) character followed by the filter name and optional arguments.

For example, let's create a Jinja2 template for an Nginx configuration file that uses variables and filters:

```nginx
user {{ nginx_user }};
worker_processes {{ nginx_worker_processes | default('auto') }};
pid {{ nginx_pid_file | default('/run/nginx.pid') }};

events {
  worker_connections {{ nginx_worker_connections | default(768) }};
}

http {
  # ...
}
```

In this example, we use variables such as `nginx_user` and `nginx_worker_processes` to customize the Nginx configuration. We also use the `default` filter to provide default values for certain variables if they are not defined.

## Control Structures

Jinja2 supports various control structures, such as conditional statements and loops, which allow you to create more complex and dynamic templates.

### Conditional Statements

Conditional statements in Jinja2 use the `{% if %}`, `{% elif %}`, and `{% else %}` tags to define branches based on conditions. For example:

```ini
[app]
{% if app_debug %}
debug = true
{% else %}
debug = false
{% endif %}
```

### Loops

Jinja2 supports loops using the `{% for %}` and `{% endfor %}` tags. You can loop over lists, dictionaries, or other iterable objects. For example:

```yaml
users:
{% for user in users_list %}
  - name: {{ user.name }}
    uid: {{ user.uid }}
{% endfor %}
```

## Including and Extending Templates

Jinja2 allows you to include and extend templates, promoting reusability and modularity in your templates.

### Including Templates

You can include one template in another using the `{% include %}` tag. This is useful for breaking down large templates into smaller, more manageable components. For example:

```yaml
# main.yml
{% include 'users.yml' %}
{% include 'groups.yml' %}
```

### Extending Templates

You can create a base template with blocks that can be overridden by other templates using the `{% extends %}` and `{% block %}` tags. This is useful for creating a consistent structure across multiple templates. For example:

jinjaCopy code

```jinja
# base.j2
<html>
<head>
  <title>{% block title %}Default Title{% endblock %}</title>
</head>
<body>
  <div id="content">
    {% block content %}{% endblock %}
  </div>
</body>
</html>
```

```jinja
# page.j2
{% extends 'base.j2' %}
{% block title %}My Page Title{% endblock %}
{% block content %}
  <h1>Welcome to My Page</h1>
  <p>This is an example of a page that extends the base template.</p>
{% endblock %}
```

In this example, the `page.j2` template extends the `base.j2` template and overrides the `title` and `content` blocks.

## Using Jinja2 Templates in Ansible

To use Jinja2 templates in Ansible, you typically deploy them using the `template` module. The `template` module takes the source template file and destination path as arguments, along with optional parameters such as owner, group, and mode.

For example, let's create a playbook that deploys an Nginx configuration template:

```yaml
---
- name: Configure Nginx
  hosts: web
  become: yes
  tasks:
    - name: Deploy Nginx configuration
      ansible.builtin.template:
        src: nginx.conf.j2
        dest: /etc/nginx/nginx.conf
        owner: root
        group: root
        mode: 0644
      notify: Restart Nginx

  handlers:
    - name: Restart Nginx
      ansible.builtin.service:
        name: nginx
        state: restarted
```

In this chapter, we've explored Jinja2, the default templating engine used by Ansible. By leveraging Jinja2 templates, you can create dynamic, reusable configurations that adapt to the desired state of your infrastructure. In the next chapter, we'll delve into Ansible Vault, a powerful tool for managing sensitive data in your Ansible projects.
