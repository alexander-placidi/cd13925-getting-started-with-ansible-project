# Getting Started with Ansible Project

You have a new project at your company that requires 3 new web servers. The requirements are that the web servers must be all consistent, configuration must be controlled and be quick to apply. Each web server must adhere to the given configuration parameters. All VMs will be running in AWS.

## Getting Started

Check out project
```
git clone https://github.com/alexander-placidi/cd13925-getting-started-with-ansible-project.git
```

### Installation

Step by step explanation of how to get a dev environment running.

1. Create an EC2 instance
2. Name it `ansible-master`
3. Connect to the instance via the AWS console
4. Perform the following tasks  
    a. Set the hostname to ansible-master: `sudo hostname ansible-master`    
    b. Install Ansible on the master node: `sudo dnf install ansible`   
    c. Run `ssh-keygen -t rsa` to generate an SSH key pair for use in other Ansible instances   
    d. Copy the contents of the file `~/.ssh/id_rsa.pub` to your clipboard      
5. Create 3 additional EC2 instances
6. Connect to each of the 3 instances and insert the key into the authorized_hosts file: `vi ~/.ssh/authorized_keys`    
7. Create your inventory file with the DNS information of the 3 instances you just spun up and put them in a group named aws in the inventory file.

## Project Instructions

Run the playbook: 
```
ansible-playbook playbook.yml -i inventory.ini
```