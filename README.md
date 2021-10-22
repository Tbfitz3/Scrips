# Scrips## Automated ELK Stack Deployment

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Filebeat.YML file may be used to install only certain pieces of it, such as Filebeat.
  - Project1-Week13/Ansible
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly Redundant, in addition to restricting access to the network.
- The load balancer makes it to where if the servers have high traffic it evens it out to prevent server crashes
- Using a jumpbox allows users to securely access the servers over secure protocals
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the File strutcure and system file.
- Filebeat monitors the log files or locations that the user selects, collects log events, and forwards them either to Elasticsearch or Logstash for indexing
- Metricbeat monitors your servers by collecting metrics from the system and services running on the server
The configuration details of each machine may be found below.
| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |     *
| WEB 1    | Gateway  | 10.1.0.3   | Linux            |      *
| WEB 2    | Gateway  | 10.1.0.4   | Linux            |     *
### Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 98.165.70.102     **
Machines within the network can only be accessed by SSH Key.
- The Jump box is able to access the elk machineusing the ip address of 10.0.0.4  **
A summary of the access policies in place can be found in the table below.
| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |        No           |  98.165.70.102       |  *
| Web 1    |        No           |      10.0.0.4        |  *
| Web 2    |        No           |      10.0.0.4        |  *
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- It does the install steps in order and if one fails it will notify you of where it failed.
The playbook implements the following tasks:
- Pulls the application from the web
- Downloads the contents
- Installs the conent to the file structure
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web 1 with a ip address of 10.1.0.4    *
- Web 2 with a ip address of 10.1.0.7   *
We have installed the following Beats on these machines:
- Filebeat and Metricbeat
These Beats allow us to collect the following information from each machine:
- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server, such as: Apache
