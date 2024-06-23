 flask and django is widely used

 # Clone python app repository from github in /opt/ directory. Repo URL: https://github.com/mmumshad/simple-webapp-flask

 Run: cd /opt/ ; sudo git clone https://github.com/mmumshad/simple-webapp-flask

 # Install the requirements for app in /opt/simple-webapp-flask. Requirements are in requirements.txt file.

 Run: cd /opt/simple-webapp-flask; sudo pip install -r requirements.txt and verify the downloaded items by running sudo pip list

 # Which python version was used in previous pip installation?

Run: pip -V command to check the python version.

python3 -V

python2 -V

# On which port app.py will run?

cd /opt/simple-webapp-flask

cat app.py | grep port

# Change port in app.py to 5000 and start the app.

Run: sudo sed -i 's/8080/5000/g' app.py

run: python app.py

# Now stop previously running app and run app.py with Gunicorn.

If gunicorn is not installed, 

run: sudo pip install gunicorn --upgrade 

and then, to run the app: gunicorn app:app

Important Note: The default location for the gunicorn binary is /usr/bin/gunicorn.

If the gunicorn binary is installed, in a different location, such as /usr/lib/python3.6/site-packages/bin/gunicorn, export this path to the $PATH environment variable for the user thor.
This way you can make use of the gunicorn command without having to provide the absolute path.

# Run Gunicorn with 3 workers in background and confirm with curl command.

Stop previously started process by pressing Ctrl + C. Then run nohup gunicorn app:app -w 3 & and verify with curl localhost:8000























