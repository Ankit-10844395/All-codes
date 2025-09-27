

## After Lunch

///////////////////////



After restarting instances

->in the dev-server terminal create new ssh key and then copy it and paste in GitHub ssh key

-> in Jenkins terminal change the ip and restart Jenkins:
# cd /var/lib/jenkins
# ll
# vim jenkins.model.JenkinsLocationConfiguration.xml
replace the older ip with new one
# systemctl restart jenkins



Jenkins Server
________________

\# yum install maven -y

-> then go to Jenkins site and install plugin

 -GitHub integration

 - maven

 - deploy to container

->go to Jenkins site settings tool add Java and Mvn path

-> Create a new job

- Maven Project

- paste Github link

- branch main

- Trigger - Build whenever a SNAPSHOT dependency is built :uncheck

          - GitHub hook trigger for GITScm polling :Check

-> Stop ec2 instance

-> Change the ec2 instance's Size from t3micro to t3small

-> started the instance\\

-> copy the public ip



\# cd /var/lib/Jenkins

\# ll

\# vim jenkins.model.JenkinsLocationConfiguration.xml

-> Change the ip

# systemctl restart Jenkins
-> goto Jenkins site and login then Pray to God and hit Build Now



TOMCAT SERVER
_____________

us east 1a

13gib t3

New security group 8080



\# hostnamectl set-hostname tomcat.example.com

\# bash

\# yum install java\* -y

\# yum install wget -y

\# yum install wget

\# wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.109/bin/apache-tomcat-9.0.109.tar.gz

\# tar -xvzf apache-tomcat-9.0.109.tar.gz

\# ll

\# cd apache-tomcat-9.0.109

\# cd bin/

\# ll

\# chmod +x startup.sh

\# chmod +x shutdown.sh

\# ./startup.sh

\# ./shutdown.sh

\# cd ..

\# cd conf

\# vim tomcat-users.xml

goto -> https://medium.com/@raguyazhin/step-by-step-guide-to-install-apache-tomcat-on-amazon-linux-120748a151a9



-> Copy

Update user information in tomcat-users.xml



\#Add below lines between <tomcat-users> tag



<role rolename="manager-gui"/>

<role rolename="manager-script"/>

<role rolename="manager-jmx"/>

<role rolename="manager-status"/>   

<user username="admin" password="admin" roles="manager-gui,manager-script,manager-jmx,manager-status"/>

<user username="deployer" password="deployer" roles="manager-script"/>

<user username="tomcat" password="s3cret" roles="manager-gui"/>



\# cd ..

\# find -name context.xml

output:

./conf/context.xml

./webapps/docs/META-INF/context.xml

./webapps/examples/META-INF/context.xml

./webapps/host-manager/META-INF/context.xml

./webapps/manager/META-INF/context.xml



now We have to comment out valve statement of last 3 files



\# vim webapps/examples/META-INF/context.xml

\# vim webapps/host-manager/META-INF/context.xml

\# vim webapps/manager/META-INF/context.xml



\# cd bin/

\# ./shutdown.sh

\# ./startup.sh



goto jenkins site

->settings ->Security ->credentials -> Global credentials -> Add credentials -> userid and pass - deployer



-> copy Tomcat server ip and open in a new tab then

Manager Tab









