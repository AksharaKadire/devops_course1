# We have added dummy html files and some dependent images to /opt/food directory.Make sure that this content is available on apache page

Move dummy content to DocumentRoot directory /var/www/html/.
  
Run sudo mv /opt/food/* /var/www/html/

# Install the latest version of tomcat 8 on host01 server under /opt/ directory. Please move extracted package to /opt/apache-tomcat-8 to keep just major version for simplicity.

# 1) https://downloads.apache.org/tomcat/tomcat-8/

After clicking on the tomcat version directory i.e. v8.5.98. You will see directory structure as follows:-

Note - The tomcat version used here as an example. It may be different in your time.

bin/                    2021-07-05 15:23     
src/                    2021-07-05 15:23  
KEYS                    2021-06-29 19:24
RELEASE-NOTES           2021-06-29 19:24

Move on to the bin directory and next, right-click on the apache-tomcat-8.5.98.tar.gz archive file and copy the link address. You can then download it using curl.

 # 2) Command: sudo curl -OL https://downloads.apache.org/tomcat/tomcat-8/v8.5.98/bin/apache-tomcat-8.5.98.tar.gz

(thor@host01 ~$ sudo curl -OL https://downloads.apache.org/tomcat/tomcat-8/v8.5.98/bin/apache-tomcat-8.5.98.tar.gz
thor@host01 ~$ ls
apache-tomcat-8.5.98.tar.gz)

After downloading it using the curl command, extract it with tar command :-
  
# 3)   sudo tar -xvf apache-tomcat-8.5.98.tar.gz  

  Next, rename the directory to the apache-tomcat-8 and move to the /opt/.

# 4)   sudo mv apache-tomcat-8.5.98 /opt/apache-tomcat-8 

q) Which scripts are used to start and stop tomcat on Linux respectively?

startup.sh and shutdown.sh

in windows: startip.bat and shutdown.bat

# Now run tomcat with default settings. Open the localhost tab to see the tomcat web page in web browser.

Run: sudo /opt/apache-tomcat-8/bin/startup.sh 

run: curl localhost:8081; ps -ef | grep tomcat 

to see tomcat page content and process. Whereas ps command does check active processes running on the system and the resources they are using.

# Now change tomcat port from 8081 to 9090. Open the localhost tab to see the tomcat web page in web browser.

To change the port :-

sudo sed -i 's/8081/9090/g'  /opt/apache-tomcat-8/conf/server.xml;

To shutdown the tomcat server :-

sudo /opt/apache-tomcat-8/bin/shutdown.sh

To start the tomcat server :-

sudo /opt/apache-tomcat-8/bin/startup.sh

and then run

curl localhost:9090; ps -ef | grep tomcat 

to see tomcat page content and process.

# Where will the tomcat logs be stored in our tomcat installation?

Logs will be under extracted tomcat package logs directory.

# Where should you place your application that you want apache tomcat to serve?

Application goes to under extracted tomcat package webapps directory.
 command: /opt/apache-tomcat-<version_number>/webapps

# Where should you place your application that you want apache tomcat to serve?

Run: cd /opt/ ; sudo mv /opt/sample.war /opt/apache-tomcat-8/webapps/

To confirm Hello world content, run curl http://localhost:9090/sample/index.html

# Which log file will show the logs for extracting war content into tomcat webapps directory?

Logs will be under extracted tomcat package logs directory. You can check content of each log or run grep command as sudo sh -c 'grep sample.war /opt/apache-tomcat-8/logs/*'

catalina.out 











  
