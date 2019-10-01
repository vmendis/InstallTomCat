README


0.  copy the public key used by Ansible to communicate with nodes

ssh_key.yml is used for this purpose

a. Make sure corret key is specified in 'key'
b. run 
    ansible-playbook --private-key=/home/ec2-user/Keys/validation-services-dev-tomcat.priv  /home/ec2-user/Work/MyAnsible/ssh_key.yml -i <ip-number-of-new-tomcat-server>,




# InstallTomCat

Always do this unless you already have the software downloaded !!

NOTE: skip to Step 4 if you have already downloaded the necessary software

1) Download JDK

Example ORacle JDK from    
          https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html?ssSourceSiteId=otnes

Extract

You will see a directory like this

  jdk1.8.0_211

Modify

./Tomcat-Ansible-Role/defaults/main.yml



Example:

   tomcat_java_version:  8u211    / This is from the web site
   tomcat_jdk_version: 1.8.0      / From the directory name
   tomcat_jdk_minor_version: 211  / From the directory name


2) Download Tomcat in "tar.gz" format

Example, downloading TomCat 9    
       https://tomcat.apache.org/download-90.cgi#9.0.21



Modify

./Tomcat-Ansible-Role/defaults/main.yml

Example:

   tomcat_version: 9.0.21       / Version number from the tomcat download page
   tomcat_checksum:             /  Get this from the web page 'sha512' version


3) Modify ./Tomcat-Ansible-Role/tasks/download-software.yml

   Set the two paths where JDK and Tomcat bundles are stored.
   // Really this hould be a variable somewhere



4) Run deploy-tomcat.yml playbook
 
$ cd /home/ec2-user/Work/MyAnsible/InstallTomCat-Using-LocalFiles

$ ansible-playbook --private-key=~/Keys/ansible-key   ./deploy-tomcat.yml -i <ip-number-of-new-tomcat-server>,

*** NOTE:  
    Remember to modify /opt/tomcat/latest/bin/setenv.sh  to add correct values for the enviornment.
       Valid values are dev or st       As of 14.Aug.2019

5) Access TomCat to confirm deployment is successful

http://<ip-number-of-new-tomcat-server>:8080/docs/manager-howto.html
