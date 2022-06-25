<h1 style="color:#ff0000;">ci-cdWithJenkins on AWS</h1>

---

<p> Create a new instance (Linux for example) && connact to him. 
<br> We want to install Jenkins on this instance right ?!
<br> Follow these commands .. 
</p>

- sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
- sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
- yum install java-1.8.0-openjdk -y  *after it's complete, check with the jave -version commads if it's install.
- yum install jenkins
- systemctl start jenkins *let's see if jenkins is running - systemctl status jenkins
- systemctl enable jenkins

<p> On your browse hit <Public IPv4 address>:8080  --> You can see that address is not reachable.
<br>Let’s add the inbound rule to the security group.
<br>Follow these steps:
<br>Go to the security tab in your instance --> click on the security group link --> go down to the 'edit inbound rules' & click --> add rule --> for the type option: select 'all traffic' & for the source: select anywhere 0.0.0.0/0 
<br>*Once you click on the Save rules and you can see the newly added rule under the security tab.
  </p>
---
Setup Jenkins
  <p> While we done with the rule and jenkins is working from the internet, we see that jenkins need a password. 
    <br< we need to go back to the instance and write this command --> cat /var/lib/jenkins/secrets/initialAdminPassword then we get a sequence, copy that
