# ci-cdWithJenkins on AWS
---

Create a new instance (Linux for example) && connact to him. 
We want to install Jenkins on this instance right ?!
Follow these commands .. 
- sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
- sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
- yum install java-1.8.0-openjdk -y  *after it's complete, check with the jave -version commads if it's install.
- yum install jenkins
- systemctl start jenkins *let's see if jenkins is running - systemctl status jenkins
- systemctl enable jenkins

On your browse hit <Public IPv4 address>:8080  --> You can see that address is not reachable.
Let’s add the inbound rule to the security group.
Follow these steps:
Goto security tab --> click on the security group link --> go down to 'edit inbound rules' --> add rule --> for the type option: select 'all traffic' & for the source: select anywhere 0.0.0.0/0 
*Once you click on the Save rules and you can see the newly added rule under the security tab.
