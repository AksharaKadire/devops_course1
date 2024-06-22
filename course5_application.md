Steps to install java in linux - thi is 20 version:

1)sudo curl https://download.java.net/java/GA/jdk20/bdc68b4b9cbc4ebcb30745c85038d91d/36/GPL/openjdk-20_linux-x64_bin.tar.gz --output /opt/openjdk-20_linux-x64_bin.tar.gz

2)To uncompress run sudo tar -xf /opt/openjdk-20_linux-x64_bin.tar.gz -C /opt/

3)To verify run /opt/jdk-20/bin/java -version on app01 and confirm correct version is installed
