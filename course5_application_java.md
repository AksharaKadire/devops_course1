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
