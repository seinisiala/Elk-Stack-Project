# Elk-Stack-Project

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.


![Elk Stack Project Diagram](https://github.com/seinisiala/Elk-Stack-Project/blob/main/Elk%20Stack%20Project%20Diagram.jpg)


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the filebeat.yml file may be used to install only certain pieces of it, such as Filebeat.

  [Install Elk](https://github.com/seinisiala/Elk-Stack-Project/blob/main/Playbook.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting access/traffic to the network.
- Load balancing allows someone to evenly distribute network/traffic to prevent failure caused by overloading. This strategy will improve the performance and availability of applications, websites, and databases. Benefits to using a jump box include ip restrictions that communicate with the Jump Box, remote connectivity, and allows monitoring and logging on a single box. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- Filebeat monitors log files and log events. 
- Metricbeat collects metrics and statistics and sends the info to a chosen output location. 

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   |  Linux           |
| Web1     |webserver | 10.0.0.5   |  Linux           |
| Web2     |webserver | 10.0.0.6   |  Linux           |
| Elk VM   |Elk Server| 10.1.0.4   |  Linux           |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Access to this machine is allowed only from my public IP. 

Machines within the network can only be accessed by Jump Box.
- Jump Box machine has access to Elk VM. Elk VM: 10.1.0.4. Jump Box ip: 10.0.01. Elk machine has access from personal IP. 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1 & personal  |
| Web1     | No                  | 10.0.0.5             |
| Web2     | No                  | 10.0.0.6             |
| ElkVM    | No                  | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- running services can be controlled and limited as well as a more streamlined system installation. 

The playbook implements the following tasks:
- Install docker.io
- Install pip3
- Install python

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Docker ps Screenshot](https://github.com/seinisiala/Elk-Stack-Project/blob/main/list%20of%20containers.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web1: 10.0.0.5
- Web2: 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat colletcts log events and data and forwards the information to Elasticsearch while Metricbeat collects stats and metrics. Metricbeat helps monitor a server by running services on the server such as MySQL and Apache. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the configuration file to Ansible container;
- Update the /etc/ansible/hosts file to include the webservers IP addresses and the Elk VM IP address; 
- Run the playbook, and navigate to https://[public IP address of Elk VM]/app/kibana to check that the installation worked as expected.
- The file
- Which file do you update to make Ansible run the playbook on a specific machine: update filebeat-config.yml How do I specify which machine to install the ELK server on versus   which to install Filebeat on: you can determine which machine to install by revising the host files with ip addresses of elk/webservers and choosing which group to run in         Ansible. 
- Which URL do you navigate to in order to check that the ELK server is running: https://[public IP address of Elk VM]/app/kibana


 ### The specific commands the user will need to run to download the playbook, update the files, etc:
 - Filebeat
 [Filebeat Playbook](https://github.com/seinisiala/Elk-Stack-Project/blob/main/File_Beat_Playbook)
 - Metricbeat
 [Metricbeat Playbook](https://github.com/seinisiala/Elk-Stack-Project/blob/main/Metric_Beat_Playbook)

 
