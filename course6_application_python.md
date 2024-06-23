# Install python3.6 in host01 server

Run sudo yum install -y python36

# We have created /home/thor/main.py. What will be output when you run it with python2?

Run: python2 /home/thor/main.py

# What will be output when you run /home/thor/main.py with python3?

Run python3 /home/thor/main.py

# Which python version is used by pip on host01 server?

pip -V

# Install flask app with pip in host01 server

sudo pip install flask

# Where will be flask app directory created with previous sudo pip install flask command?

Run: pip show flask 

check the Location

# Which of the following package is not installed on host01 server?

 Run: pip show gunicorn Jinja2 Werkzeug markupsafe 
 
 check which package is not found

 # We have created requirements file /home/thor/requirements.txt.Install python packages with versions specified in /home/thor/requirements.txt?

Run: pip install -r /home/thor/requirements.txt

---------------
Flask==0.10.1
Jinja2==2.7.3
MarkupSafe==0.23
Werkzeug==0.9.6
requests==2.3.0
gunicorn==18.0
--------------
the above is the requirement.txt file

#  Upgrade version of gunicorn package installed in previous step

Run: pip install gunicorn --upgrade

# Uninstall gunicorn package

Run: pip uninstall gunicorn -y












