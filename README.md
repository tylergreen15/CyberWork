# CyberWork
All projects I have worked on so far in CyberBootCamp
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system resources.
-Filebeat watches for system logs and forward any changes to the Elasticsearch Host
-Metricbeat is used only for gathering metrics and system resources usage for display in Elasticsearch

The configuration details of each machine may be found below.

| Name     | Function   | IP Address | Operating System |   |
|----------|------------|------------|------------------|---|
| Jump Box | Gateway    | 10.0.0.1   | Linux            |   |
| Web 1    | Web Server | 10.0.0.5   | Linux            |   |
| Web 2    | Web Server | 10.0.0.6   | Linux            |   |
| ELK      | ELK Stack  | 10.1.0.4   | Linux            |   |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-174.25.13.120
Machines within the network can only be accessed by the Jump Box.
-Pblic IP: 23.100.33.68
-Private IP: 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Function            | IP Address           | Operating System |   |
|----------|---------------------|----------------------|------------------|---|
| Name     | Publicly Accessible | Allowed IP Addresses | Linux            |   |
| Jump Box | 22-Yes              | 174.25.13.120        | Linux            |   |
| Web 1/2  | No                  | --                   | Linux            |   |
| ELK      | 5601-Yes            | 174.25.13.120        | Linux            |   |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-It allows for full automation of the specified server and reduces configuration errors

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Python3_pip
- Install Docker
- Upgrade memory
- Download and Instal ELK container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-10.0.0.5
-10.0.0.6
-10.1.0.4

We have installed the following Beats on these machines:
-Metric Beat
-File Beat

These Beats allow us to collect the following information from each machine:
-Filebeats collects system type events such as logins to see who is actively logging into the system, while Metricbeats collects useful information such as cpu usage and memory.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the elk_install.yml file to /etc/ansible/roles/elk_install.yml.
- Update the hosts file to include the attribute, such as [elk], then include your destination ip of the ELK server directly below.
- Run the playbook, and navigate to http://[your_elk_server_ip]:5601/app/kibana  to check that the installation worked as expected.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
