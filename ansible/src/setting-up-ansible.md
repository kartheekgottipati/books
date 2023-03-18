# Setting Up Ansible

## Installing Ansible

Ansible is easy to install and is supported on various platforms, including Linux, macOS, and Windows (using WSL). In this section, we'll cover the installation process for different platforms.

### Linux (Debian/Ubuntu):

Install Ansible using the Advanced Package Tool (APT):

```bash
sudo apt update
```

```bash
sudo apt install ansible
```

### Linux (Red Hat/CentOS/Fedora):

First, enable the EPEL repository:

```bash
sudo yum install epel-release
```

Next, install Ansible using the Yellowdog Updater, Modified (YUM):

```bash
sudo yum install ansible
```

### macOS:

Use Homebrew to install Ansible:

```bash
brew install ansible
```

### Windows (WSL):

Enable the Windows Subsystem for Linux (WSL) and install a Linux distribution like Ubuntu from the Microsoft Store. Then, follow the Linux installation instructions above.

Verify the installation by running:

```bash
ansible --version
```

## Configuring Ansible

After installing Ansible, create a configuration file to customize its behavior. By default, Ansible looks for a configuration file in the following order:

1. `ANSIBLE_CONFIG` environment variable.
2. `ansible.cfg` in the current directory.
3. `~/.ansible.cfg` in the user's home directory.
4. `/etc/ansible/ansible.cfg` system-wide configuration.

Create a new `ansible.cfg` file in your project directory:

```cfg
[defaults] 
inventory = ./inventory.ini
remote_user = your_remote_user
```

Replace `your_remote_user` with the appropriate remote user for your managed nodes.

## Setting Up an Ansible Inventory

An inventory is a list of managed nodes organized into groups. Create an `inventory.ini` file in your project directory:

```ini
[web]
webserver1 ansible_host=192.168.1.10
webserver2 ansible_host=192.168.1.11

[db]
dbserver ansible_host=192.168.1.20

[all:vars]
ansible_ssh_private_key_file=/path/to/your/private_key
```

In this example, we've defined two groups, `web` and `db`, with three managed nodes. The `all:vars` section contains variables that apply to all nodes, such as the SSH private key file.

## Testing Your Setup

To test your Ansible setup, run a simple command on all managed nodes using the `ansible` command:

```bash
ansible all -m ping
```

This command uses the `ping` module to check if the managed nodes are reachable. If everything is set up correctly, you should see output similar to:

```javascript
webserver1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
webserver2 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
dbserver | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

With Ansible installed and configured, you're ready to start automating your infrastructure. In the next chapter, we'll introduce playbooks, the core component of Ansible that allows you to define and manage the desired state of your infrastructure.
