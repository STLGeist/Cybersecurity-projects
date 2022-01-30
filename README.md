## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Images/CyberProjectDrawing.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the .yml file may be used to install only certain pieces of it, such as Filebeat.

  [filebeat_metricbeat-playbook.yml.txt](https://github.com/STLGeist/Cybersecurity-projects/files/7715493/filebeat_metricbeat-playbook.yml.txt)


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting excessive network traffic to the network.
-What aspect of security do load balancers protect? What is the advantage of a jump box? Load Balancers help prevent excessive network traffic and help prevent DOS attacks, increasing availability of that network. The advantage of a jump box is to help distribute code to VMs on a network and get rid of/reduce downtime of those VMs.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system resources.
-What does Filebeat watch for? For new logs from the webservers.
-What does Metricbeat record? OS resource data and services running on webservers.

The configuration details of each machine may be found below.

| Name     | Function   | IP Address | Operating System |
|----------|------------|------------|------------------|
| Jump Box | Gateway    | 10.0.0.4   | Linux 18.04      |
| Server1  | Host DVWA  | 10.0.0.5   | Linux 18.04      |
| Server2  | Backup DVWA| 10.0.0.6   | Linux 18.04      |
| Server3  | Backup DVWA| 10.0.0.7   | Linux 18.04      |
| ELKvm    | ELK server | 10.1.0.4   | Linux 18.04      |

Access Policies:
- HTTP traffic to Servers
- SSH to Jumpbox and SSH from Jumpbox to servers and ELKvm
- SSH to ELKvm from Jumpbox within resource group
- Port 5601 from my public IP to ELKvm external IP

![image](https://user-images.githubusercontent.com/89103977/151673406-70e56a9d-747f-412d-bde0-0169e3665622.png)

CyberProjectDrawing.PNG


The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- My public IP address

Machines within the network can only be accessed by the Jumpbox VM.
- Which machine did you allow to access your ELK VM? What was its IP address? Allowed SSH from Jumpbox(10.0.0.4) and Port 5601 from my external IP address.

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Main advantage is being able to deploy .yml config files with little to no downtime.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Docker and images for ELK stack
- Configure playbooks for the ELK stack and filebeat/metricbeat
- Install filebeat/metricbeat on the webservers and install ELK on the dedicated VM outside of the webserver network
- Run Kibana VM to ensure connections are good and recieving data

Images/docker_ps.png
 

SSH into the control node and follow the steps below:
- Copy the roles file to /etc/ansible/roles.
- Update the hosts file to include webserver IPs and ELKServer IP
- Run the playbook, and navigate to HTTP://<ELKServer_Public_IP>:5601 to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? /etc/ansible/install-elk.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?  /etc/ansible/hosts Specify the IP addresses for the dedicated VM for the ELK and the IP addresses for the webservers.
- _Which URL do you navigate to in order to check that the ELK server is running? HTTP://<ELKServer_Public_IP>:5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

