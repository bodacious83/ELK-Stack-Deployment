Automated ELK Stack Deployment 

The files in this repository were used to configure the network depicted below.

Note: The following image link needs to be updated. Replace diagram_filename.png with the name of your diagram image file.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Red-Team Network Diagram file may be used to install only certain pieces of it, such as Filebeat.

https://lucid.app/lucidchart/invitations/accept/15590e23-dc60-448a-9c79-c378103e352a

This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration

Beats in Use
Machines Being Monitored


How to Use the Ansible Build


Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.


Load balancing is designed to ensure that the application will be available as well as added resiliency by distributing live traffic evenly across the multiple servers. 

The advantage of our Jump-Box is that it provides a true gateway router to the private network. Because of this, it ensures all other machines within the network do not directly face the internet which means an overall much more secure network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.


The configuration details of each machine may be found below.
Note: Use the Markdown Table Generator to add/remove values from the table.



Name
Function
IP Address
Operating System




Jump Box
Gateway
10.0.0.4
Linux




Web-1 DVWA
Server
10.0.0.5
Linux




Web-2 DVWA
Server
10.0.0.8
Linux





Web-3 DVWA
Server
10.0.0.9
Linux




ELK-SERVER
Monitoring
10.2.0.4
Linux




Access Policies

The machines on the internal network are not exposed to the public Internet.
Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

Jump-Box Machine may be accessed from IP address 51.143.15.182.

Machines within the network can only be accessed by Jump-Box.

The ELK-SERVER may be accessed from the Jump-Box Machine - 10.0.0.4

A summary of the access policies in place can be found in the table below.



Name
Publicly Accessible
Allowed IP Addresses




Jump-Box
Yes
51.143.15.182




Web-1 DVWA
No 
10.0.0.4




Web-2 DVWA
No 
10.0.0.4




Web-3 DVWA
No
10.0.0.4




ELK-SERVER
No
10.0.0.4


Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

By automating the configuration with ansible it ensured that our provisioning scripts run indentically anytime they run, anywhere. This allows for easy instillation of multiple versions and helps eleminate as much variablity between configurations.

The playbook implements the following tasks:

Step 1 - Configure ELK VM with Docker

Step 2 - Install docker.io

Step 3 - Install pip3

Step 4 - Install python module with Docker

Step 5 - Download & launch ELK container with Docker

Step 6 - Use systemctl to increase overall memory


The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Note: The following image link needs to be updated. Replace docker_ps_output.png with the name of your screenshot image file.


Target Machines & Beats
This ELK server is configured to monitor the following machines:

Web-1 DVWA 10.0.0.5

Web-2 DVWA 10.0.0.8

Web-3 DVWA 10.0.0.9
