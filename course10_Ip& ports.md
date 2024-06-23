# Run apache tomcat on all IP interfaces and port 9090 on host01 server. We already downloaded apache tomcat under /opt/apache-tomcat-8.5.53 directory. Modify necessary files and start tomcat.

Move to the /opt/ directory by using the cd command: -

thor@host01 ~$ cd /opt/

Then use the sudo at the beginning of the command because it needs root permission to execute this.

thor@host01 ~$ sudo sed -i 's/8080/9090/g' apache-tomcat-8.5.53/conf/server.xml 

Run the startup.sh script as follows: -

thor@host01 ~$ sudo ./apache-tomcat-8.5.53/bin/startup.sh 

Note: - Tomcat by default listen to all IP interfaces.

# We have cloned python app repo from GitHub in /opt/ directory in app01 server. When you start it which IP and port combination it will listen on?

Python app file : /opt/simple-webapp-flask/app.py

Note: - Make use of the SSH command to login in app01 server from the thor user of host01 server. It's a passwordless setup.

thor@host01 ~$ ssh app01

ans:

Run ssh app01 to login app01 server from the thor user of the host01 server as follows: -

thor@host01 ~$ ssh app01


After successful login, check app.run parameters in /opt/simple-webapp-flask/app.py file with cat command as follows: -

[thor@app01 ~]$ cat /opt/simple-webapp-flask/app.py 

# In app01 server ensure that our app in /opt/simple-webapp-flask/ run on port 5000 and listen to 127.0.0.1 IP.

Run python app in background with nohup.

Note:- Nohup stands for no hang up, which can be executed as shown below:-

nohup command-with-options &

Adding & at the end will move the process to run in background. When you execute a Unix job in the background (using &) and logout from the session, your process will get killed. You can avoid this with nohup.

ans:  

SSH to app01 server if you are in the host01 server from the thor user. It's a passwordless setup: -

thor@host01 ~$ ssh app01


Skip this step. if you are already in the app01 server.


Replace the given IP address and port with sed command as follows: -

[thor@app01 ~]$ sudo sed -i 's/0.0.0.0/127.0.0.1/g;s/8080/5000/g' /opt/simple-webapp-flask/app.py


And inspect the changes: -

[thor@app01 ~]$ cat /opt/simple-webapp-flask/app.py 


Now, move to the /opt/simple-webapp-flask/ directory: -

[thor@app01 ~]$ cd /opt/simple-webapp-flask/


Then run the python app in background with nohup as follows: -

[thor@app01 simple-webapp-flask]$ nohup python app.py &


To ensure it's working, make use of the curl command: -

[thor@app01 simple-webapp-flask]$ curl http://127.0.0.1:5000


You will get a Welcome! message.

# hint:

ssh to app01 server and run below commands :-

sudo sed -i 's/0.0.0.0/127.0.0.1/g;s/8080/5000/g' /opt/simple-webapp-flask/app.py;

cd /opt/simple-webapp-flask/; nohup python app.py &

# From host01 server is Python flask of app01 server accessible?

We started python app on only 127.0.0.1 interface. Open an additional terminal and try curl app01:5000 on host01 server.

# Enable Flask app to be reachable from host01 and confirm by browser tab.

To make app reachable from outside we have to bind app to global IP that will be used to access it or simply listen on all interfaces. In this case please make Flask app listen on all IP interfaces

Note: - Make use of the SSH command to login in app01 server from the thor user of host01 server. It's a passwordless setup.

thor@host01 ~$ ssh app01

ans: 

Make use of the SSH command to login in app01 server from the thor user of host01 server as follows: -

thor@host01 ~$ ssh app01

Skip this step if you are already in the app01 server. 


Replace the 127.0.0.1 IP address with 0.0.0.0 to make Flask app listen on all IP interfaces.

[thor@app01 ~]$ sudo sed -i 's/127.0.0.1/0.0.0.0/g' /opt/simple-webapp-flask/app.py


Inspect the changes:-

[thor@app01 ~]$ cat /opt/simple-webapp-flask/app.py 


Now, kill the running python app: -

[thor@app01 ~]$ pkill python


Move to the /opt/simple-webapp-flask/ directory: -

[thor@app01 ~]$ cd /opt/simple-webapp-flask/


And run the python app in the background with nohup command again: -

[thor@app01 simple-webapp-flask]$ nohup python app.py &


To ensure it's working, open an additional terminal and run the curl command from the host01 server as follows: -

thor@host01 ~$ curl app01:5000


You will get a Welcome! message.

# We added app01 IP address 172.16.239.30 to flask application but seems curl app01:5000 not working on host01 server. Please fix the issue so that curl app01:5000 works as well as curl 172.16.239.30:5000 works on host01 server.


Note: - Make use of the SSH command to login in app01 server from the thor user of host01 server. It's a passwordless setup.

thor@host01 ~$ ssh app01


ans:

Make use of the SSH command to login in app01 server from the thor user of host01 server as follows: -

thor@host01 ~$ ssh app01

Skip this step if you are already in the app01 server. 


Use the sed command to replace the IP address: -

[thor@app01 ~]$ sudo sed -i 's/172.16.239.30/0.0.0.0/g' /opt/simple-webapp-flask/app.py

Now, kill the python process to rerun the app again: -

[thor@app01 ~]$ sudo pkill python


Move to the flask directory: -

[thor@app01 ~]$ cd /opt/simple-webapp-flask/


Run the python app in the background with nohup command: -

[thor@app01 ~]$ nohup python app.py &

And make it work for all IPs.

Finally, open an additional terminal and test it with the curl command on the host01 server as follows: -

thor@host01 ~$ curl app01:5000 

thor@host01 ~$ curl 172.16.239.30:5000


In both tests, you will get a Welcome! message.










