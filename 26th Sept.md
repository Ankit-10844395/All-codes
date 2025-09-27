# New Jenkins Setup Due To Update in Genkins



useast 1a

Custom tcp Port 8080

12 gib gp2



##### Jenkins Terminal

\# hostnamectl set-hostname jenkins.example.com

\# bash

\# rpmquery Jenkins

\# yum update

\# yum repolist all



yum update -y

dnf install java-17-amazon-corretto -y

 

  sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

 

rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

 

sudo yum install jenkins -y \*

sudo yum install jenkins

 

sudo systemctl start jenkins

sudo systemctl enable jenkins

