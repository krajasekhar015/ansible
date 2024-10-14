Welcome to the ansible wiki!

# **What is Ansible?**?
Ansible is an open-source automation tool used primarily for configuration management, application deployment, and task automation. It is known for its simplicity and ease of use, making it a popular choice for managing both small and large-scale IT environments.
# Key Features of Ansible

1. **Agentless**: Ansible does not require any special agents or daemons to be installed on the target machines. It uses SSH (or WinRM for Windows) to communicate with remote hosts, which simplifies setup and management.

2. **Declarative Language**: Ansible uses a declarative language to describe the desired state of your systems. This means you define what you want to achieve, and Ansible takes care of making it happen.

3. **Playbooks**: Ansible configurations are written in YAML (Yet Another Markup Language) format, which is human-readable and easy to write. Playbooks are files where you define the tasks and roles to be executed.

4. **Idempotent**: Ansible operations are idempotent, meaning that running the same playbook multiple times will not change the system state beyond the initial application. This helps ensure consistency and reliability.

5. **Modules**: Ansible provides a wide range of built-in modules for various tasks, such as managing files, installing packages, and configuring services. You can also create custom modules if needed.(modules are same commands in shell or other scripts)

6. **Roles**: Roles in Ansible allow you to organize playbooks and tasks into reusable components, making it easier to manage complex configurations and promote code reuse.

7. **Inventory**: Ansible uses inventory files to define the list of hosts and groups of hosts that it will manage. This allows you to target specific groups of servers or individual machines.

# Basic Concepts

1. **Inventory**: A file or a dynamic source that lists all the hosts (servers) Ansible will manage. It defines groups and individual machines.

2. **Playbook**: A YAML file that defines a set of tasks to be executed on the managed hosts. Playbooks are the heart of Ansible automation.

3. **Task**: A single action that Ansible performs, such as installing a package or copying a file.

4. **Role**: A way to group related tasks, handlers, and variables. Roles help in organizing playbooks and reusing code.

5. **Handler**: Special tasks that are only run when notified by other tasks. They are typically used for actions that need to be performed when changes occur, such as restarting a service.
# Example Playbook
Here is a simple example of an Ansible playbook that installs Nginx on a group of servers:

``` ---
- name: Install and start Nginx
  hosts: webservers
  become: yes  # Run tasks with sudo
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present

    - name: Start Nginx service
      service:
        name: nginx
        state: started
 ```

# Running the playbook

``` ansible-playbook -i inventory_file nginx_playbook.yml```
# How Ansible Works

1. **Define the Desired State**: You write a playbook describing the desired state of your systems.
2. **Execute the Playbook**: Ansible connects to the target hosts, executes the tasks defined in the playbook, and ensures the systems reach the desired state.
3. **Report and Verify**: Ansible provides feedback on what was changed, allowing you to verify the state of your systems.
# Use Cases
* Configuration Management: Ensuring systems are configured correctly and consistently.
* Application Deployment: Automating the deployment of applications and updates.
* Orchestration: Managing and coordinating complex IT workflows and processes.
* Provisioning: Setting up and configuring new servers or cloud instances.

Ansible is widely used in various IT environments due to its simplicity, flexibility, and powerful features.



