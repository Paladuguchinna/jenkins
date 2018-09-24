# jenkins
Jenkins installation using yum repo
Step:1 Add Jenkins Repository
Jenkins package is not available in the default CentOS and RHEL repositories. So we need to add jenkins repository using the beneath commands.

[root@jenkins ~]# wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins.io/redhat-stable/jenkins.repo
[root@jenkins ~]# rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key
Step:2 Install Jenkins and Java
Run the below  yum command to install Jenkins and java.

[root@jenkins ~]# yum install jenkins java-1.7.0-openjdk –y
Step:3 Start and Enable Jenkins Service
Run the following systemctl commands to start and enable the jenkins service

[root@jenkins ~]# systemctl start jenkins
[root@jenkins ~]# systemctl enable jenkins
Step:4 Open the ports (80 and 8080) in OS firewall.
In case firewall is enabled on your Linux server then run the following commands to open jenkins related ports like 80 and 8080.

[root@jenkins ~]# firewall-cmd --zone=public --add-port=8080/tcp --permanent
success
[root@jenkins ~]# firewall-cmd --zone=public --add-service=http --permanent
success
[root@jenkins ~]# firewall-cmd --reload
success
[root@jenkins ~]#
Step:5 Access the Jenkins Web portal
Access the URL : http://<Ip-Address-of-your-Server>:8080
