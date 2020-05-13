# ElkStack_Project1
Creating a cloud monitoring system by configuring an ELK stack server
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

[Diagram.png]

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  Filebeat-playbook.yml.txt

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting overflow to the network.
- Load balancing covers the Administrating aspect in security.A jump box is a secure computer that all admins first connect to before launching any administrative task or use as an origination point to connect to other servers or untrusted environments.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the infrastructure and system logs.
- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch for indexing.
-Metricbeat is configured to use the system module which collects server system metrics, such as CPU and memory usage and network.

The configuration details of each machine may be found below.

| Name       | Function | IP Address | Operating System |
|------------|----------|------------|------------------|
| Jump Box   | Gateway  | 10.1.0.4   | Linux            |
| DVWA       | Docker   | 10.0.0.5   | Linux            |
| DVWA 2     | Docker   | 10.0.0.6   | Linux            |
| Elk Stack  | Monitor  | 10.0.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Elk machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-104.62.47.48
-104.40.2.200
-40.78.23.49

Machines within the network can only be accessed by Elk.
-DVWA,DVWA2
-104.40.2.200,40.78.23.49

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | IP addressess                         |
|----------|---------------------|---------------------------------------|
| Jump Box | yes/no              | 10.1.0.4 / 104.62.47.48               |
| DVWA     | no                  | 10.1.0.4                              |
| DVWA 2   | no                  | 10.1.0.4                              |
| ELK      | yes                 | 104.62.47.48,104.40.2.200,40.78.23.49 |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible is an open-source tool using playbooks to orchestrate entire application environment.

The playbook implements the following tasks:
- Take machines in and out of load balancers and monitoring windows
- Have one server know the IP address of all the others using facts gathered about those particular servers - and use those to dynamically build out configuration files
-Set some variables and prompt for others, and set defaults for when they are not set
-Use the result of one command to decide whether to run another

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Image description](https://github.com/MarionAPerez/ElkStack_Project1/blob/master/Docker%20ps.png.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?


