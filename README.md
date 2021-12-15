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


The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- My public IP address

Machines within the network can only be accessed by the Jumpbox VM.
- Which machine did you allow to access your ELK VM? What was its IP address? Allowed SSH from Jumpbox(10.0.0.4) and Port 5601 from my external IP address.

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Main advantage is being able to deploy .yml condfig files with little to no downtime.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._



1. Add the sample web log data to Kibana.

2. Answer the following questions:

    - In the last 7 days, how many unique visitors were located in India? 249

    - In the last 24 hours, of the visitors from China, how many were using Mac OSX? 8

    - In the last 2 days, what percentage of visitors received 404 errors? How about 503 errors? 0%
    - In the last 7 days, what country produced the majority of the traffic on the website? China
    - Of the traffic that's coming from that country, what time of day had the highest amount of activity? 13:00
    - List all the types of downloaded files that have been identified for the last 7 days, along with a short description of each file. CSS, describes how HTML elements are displayed on the screen. GZ, archive compressed file using gzip compresson.

3. Now that you have a feel for the data, Let's dive a bit deeper. Look at the chart that shows Unique Visitors Vs. Average Bytes.
     - Locate the time frame in the last 7 days with the most amount of bytes (activity).
     - In your own words, is there anything that seems potentially strange about this activity?

4. Filter the data by this event.
     - What is the timestamp for this event?
     - What kind of file was downloaded?
     - From what country did this activity originate?
     - What HTTP response codes were encountered by this visitor?

5. Switch to the Kibana Discover page to see more details about this activity.
     - What is the source IP address of this activity?
     - What are the geo coordinates of this activity?
     - What OS was the source machine running?
     - What is the full URL that was accessed?
     - From what website did the visitor's traffic originate?

6. Finish your investigation with a short overview of your insights. 

     - What do you think the user was doing?
     - Was the file they downloaded malicious? If not, what is the file used for?
     - Is there anything that seems suspicious about this activity?
     - Is any of the traffic you inspected potentially outside of compliance guidlines?

---
