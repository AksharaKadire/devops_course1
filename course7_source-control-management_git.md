# https://res.cloudinary.com/kodekloud/image/upload/v1702543780/course-resource-new/Additional-Resources.pdf

# Install git package using yum on host01 server.

 sudo yum install git

 # On host01 create/initialize a git repository myrepo in thor user's home directory

 Use below mentioned commands:

cd /home/thor

git init myrepo

(Initialized empty Git repository in /home/thor/myrepo/.git/)

# In /home/thor/myrepo repository check the status and find out un-tracked changes. Which un-tracked file/files you see there ?

git status

# Add the index.html file to the git repo so it's changes are tracked. And then commit the changes. Use any message while committing.

Use below mentioned command:

cd /home/thor/myrepo

git add index.html

git commit -m 'your commit message'








