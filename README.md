1 Create 3 AWS ubuntu instances and name then JenkinsServer,QAServer,ProdServer
2 Connect to Jenkinsserver using Gitbash
3 Update the apt repository
sudo apt-get update
4 Install jdk
sudo apt-get install -y openjdk-11-jdk
5 Install git and maven
sudo apt-get install -y git maven
6 Downlaoded jenkins.war
wget https://get.jenkins.io/war-stable/2.361.3/jenkins.war
7 To start jenkins
java -jar jenkins.war
8 To access jenkins open browser
public_ip_of_jenkinserver:8080
9 Unlock jenkins by entering the password
10 Click on Install suggested plugin
11 Create admin user
Then I Setup of tomcat on Qa and ProdServers
1 Connect to QAserver using Gitbash
2 Update the apt repository
sudo apt-get update
3 Install tomcat9
sudo apt-get install -y tomcat9
4 Install tomcat9-admin
sudo apt-get install -y tomcat9-admin
5 Edit the tomcat-users.xml file
cd /etc/tomcat9
sudo vim tomcat-users.xml
Delete all the content from the file and add the below content
<tomcat-users>
<user username="advik" password="advik1234" roles="manager-script"/>
</tomcat-users>
6 Restart tomcat
sudo service tomcat9 restart

Pipeline as code can be implemented in 2 ways
1 Scripted Pipeline
2 Declarative Pipeline
Syntax of Scripted Pipeline
================================
node('built-in')
{
stage('Stage name in ci-cd')
{
Groovy code to implement this stage
}
}
Syntax of Declarative Pipeline
===================================
pipeline
{
agent any
stages
{
stage('Stage name in CI-CD')
{
steps
{
Groovy code to implement this stage
}
}
}

I implemented Declarative Pipeline
