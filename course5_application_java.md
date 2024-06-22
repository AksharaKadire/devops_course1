Steps to install java in linux - thi is 20 version:

1)sudo curl https://download.java.net/java/GA/jdk20/bdc68b4b9cbc4ebcb30745c85038d91d/36/GPL/openjdk-20_linux-x64_bin.tar.gz --output /opt/openjdk-20_linux-x64_bin.tar.gz

2)To uncompress run sudo tar -xf /opt/openjdk-20_linux-x64_bin.tar.gz -C /opt/

3)To verify run /opt/jdk-20/bin/java -version 

step 4 - not reqired - only understand 

4) We need to set java binary path in environment PATH variable to use java binaries. So that you can simply run java instead of the full path.

Set path variable with the command as: export PATH=$PATH:/opt/jdk-20/bin
