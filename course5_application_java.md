Steps to install java in linux - thi is 20 version:

1)sudo curl https://download.java.net/java/GA/jdk20/bdc68b4b9cbc4ebcb30745c85038d91d/36/GPL/openjdk-20_linux-x64_bin.tar.gz --output /opt/openjdk-20_linux-x64_bin.tar.gz

2)To uncompress run sudo tar -xf /opt/openjdk-20_linux-x64_bin.tar.gz -C /opt/

3)To verify run /opt/jdk-20/bin/java -version 

step 4 - not reqired - only understand 

4) We need to set java binary path in environment PATH variable to use java binaries. So that you can simply run java instead of the full path.

Set path variable with the command as: export PATH=$PATH:/opt/jdk-20/bin

# We have created MyClass.java file inside /opt/app directory. View it if you like using the command cat MyClass.java. Please compile it.

Run cd /opt/app/; javac MyClass.java to compile 

(or)

javac /opt/app/MyClass.java

# To print output 

run: java /opt/app/MyClass.java (or)

cd /opt/app

java MyClass.java

# Generate documentation for the MyClass.java source code into the /opt/app/doc directory.

Run: cd /opt/app/; javadoc -d doc MyClass.java to document and see an output

# Install the Apache Ant build tool on host01 server

sudo yum install ant -y

# Check the ANT build configuration file /opt/ant/build.xml on host01 server. If you run ant docs command, where will the generated html docs be stored?

cat /opt/ant/build.xml | grep destdir

# if ant jar command runs then where does the html gets stored?

cat /opt/ant/build.xml | grep destfile | grep jar

o/p: 

<jar basedir="/opt/ant/build" destfile="/opt/ant/dist/MyClass.jar" >

# Compile and generate jar package using ant.

Run: ant compile jar inside /opt/ant directory.

# Run ant to carry out all steps specified in the build configuration file /opt/ant/build.xml.

Run: ant inside /opt/ant directory

or

cd /opt/ant

ant

output:

Buildfile: /opt/ant/build.xml

compile:
    [javac] /opt/ant/build.xml:5: warning: 'includeantruntime' was not set, defaulting to build.sysclasspath=last; set to false for repeatable builds

jar:

docs:
  [javadoc] Generating Javadoc
  [javadoc] Javadoc execution
  [javadoc] Loading source file /opt/ant/src/MyClass.java...
  [javadoc] Constructing Javadoc information...
  [javadoc] Standard Doclet version 1.8.0_412
  [javadoc] Building tree for all the packages and classes...
  [javadoc] Building index for all the packages and classes...
  [javadoc] Building index for all classes...

run:
     [java] Hello Kodekloud

main:

BUILD SUCCESSFUL
Total time: 0 seconds

## Install the maven build automation tool on the host01 server.

Run: sudo yum install -y maven to install maven.

rpmquery maven

# Please compile and package the application inside /opt/maven/my-app/ with maven on host01 server.

do cd /opt/maven/my-app/; sudo mvn package to build with maven.

# What is output for main app when you run /opt/maven/my-app/target/my-app-1.0-SNAPSHOT.jar created with maven package?

Execute java -cp /opt/maven/my-app/target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App on host01 server to run jar.

# Help us install NodeJS 16 on host01 server!

sudo yum install nodejs

# To run/see output nodejs

node /home/add.js 

 # to check version
 
 node -v

 or
 
rpmquery nodejs

# What is the npm version preinstalled in host01 server?

npm -v

# Who is author of file package for npm?

Run: npm search file 

check AUTHOR column.

# Install NodeJS file package with npm inside /home/thor/ directory.

Run: cd /home/thor/; npm install file

to install NodeJS file package.

# What is the path for package.json for file package installed in previous step? 

thor@host01 ~$ ls
node_modules  package-lock.json
thor@host01 ~$ cd node_modules
thor@host01 ~/node_modules$ ls
file
thor@host01 ~/node_modules$ cd file
thor@host01 ~/node_modules/file$ ls
lib  LICENSE  package.json  README.md  tests
thor@host01 ~/node_modules/file$ 

# Install file module globally with npm.

Run: sudo npm install file -g 

# Where did we install file package in previous step with global option?

Built-in modules are stored in /usr/lib/node_modules/npm/node_modules/ 

while External modules are stored in /usr/lib/node_modules on linux systems.

# Download nodejs application from github in /home/thor/ on host01 server?

Git repo URL for nodejs : https://github.com/contentful/the-example-app.nodejs

Run: cd /home/thor/; git clone https://github.com/contentful/the-example-app.nodejs

# What is the dependency for helmet version in /home/thor/the-example-app.nodejs/package.json on host01 server?

Check dependencies field for helmet in /home/thor/the-example-app.nodejs/package.json.

or 

cat /home/thor/the-example-app.nodejs/package.json | grep helmet





