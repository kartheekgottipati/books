# Real-World Ansible Scenarios

In this chapter, we will explore some real-world scenarios where Ansible can be used to automate common tasks and manage infrastructure. These examples demonstrate how Ansible can be applied to solve various challenges and streamline your operations.

## Deploying a Web Application

Ansible can be used to automate the deployment of web applications, ensuring a consistent and efficient process. By creating a playbook that performs tasks such as deploying application code, installing dependencies, and configuring web servers, you can simplify the deployment process and minimize errors.

Example Scenario: Deploying a Node.js Application

In this scenario, you create a playbook to automate the deployment of a Node.js web application. The playbook performs the following tasks:

1. Install Node.js and npm (Node Package Manager) on the target server.
2. Clone the application code from a Git repository.
3. Install the required Node.js packages and dependencies.
4. Configure the application using a Jinja2 template for the configuration file.
5. Start the Node.js application using a process manager like PM2.

## Managing a Multi-Tier Application

Ansible can be used to manage the deployment and configuration of multi-tier applications, which often consist of multiple components such as web servers, application servers, and databases. By creating playbooks and roles for each component, you can ensure a consistent and maintainable infrastructure.

Example Scenario: Managing a Multi-Tier Django Application

In this scenario, you create a playbook to automate the deployment and configuration of a multi-tier Django application, which consists of an Nginx web server, a Django application server (using Gunicorn), and a PostgreSQL database. The playbook performs the following tasks:

1. Install and configure the Nginx web server.
2. Install and configure the Gunicorn application server.
3. Install and configure the PostgreSQL database server.
4. Deploy the Django application code from a Git repository.
5. Configure the Django settings using a Jinja2 template.
6. Run database migrations and collect static files for the Django application.

## Automating Server Hardening and Security

Ansible can be used to automate the process of hardening your servers and implementing security best practices. By creating playbooks that perform tasks such as installing security updates, configuring firewalls, and managing user access, you can ensure a consistent and secure environment.

Example Scenario: Automating Server Hardening on Ubuntu

In this scenario, you create a playbook to automate the hardening of an Ubuntu server. The playbook performs the following tasks:

1. Update the package repository and install security updates.
2. Install and configure the Uncomplicated Firewall (UFW) to allow only required ports.
3. Disable root login and password-based authentication for SSH.
4. Install and configure the Fail2Ban intrusion prevention software.
5. Remove unnecessary services and packages.
6. Configure automatic security updates and log monitoring.

## Provisioning and Managing Cloud Infrastructure

Ansible can be used to automate the provisioning and management of cloud infrastructure, ensuring a consistent and maintainable environment. By creating playbooks that use cloud provider-specific modules, you can manage resources such as virtual machines, storage, and networking.

Example Scenario: Provisioning and Managing Azure Infrastructure

In this scenario, you create a playbook to automate the provisioning and management of your Azure infrastructure. The playbook performs the following tasks:

1. Create a resource group in Azure.
2. Provision a virtual network and subnet.
3. Create a network security group and configure rules to allow incoming traffic.
4. Provision a virtual machine and attach it to the virtual network and security group.
5. Install and configure a web server on the virtual machine. 6
