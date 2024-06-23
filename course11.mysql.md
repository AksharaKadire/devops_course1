What is the default data directory MySQL uses on most of Linux based systems ?

/var/lib/mysql
# Install MySQL server package. You can either install Mysql or MariaDB both should work.


To install MariaDB Server:

i. sudo yum install mariadb-server

To install MySQL Server:

i. sudo yum install https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm

ii. sudo yum install mysql-community-server

# start MySQL/MariaDB service on default port.

To start MariaDB Service: sudo service mariadb start

To start MySQL Service: sudo service mysqld start

# If you have installed MySQL Server then you can find out MySQL root user password using command sudo grep 'temporary password' /var/log/mysqld.log But if you have installed MariaDB server you might have noticed that there is no password set for MySQL root user.


a. If you have installed MariaDB server then set password P@ssw0rd12t user.

b. If you have installed MySQL server then change root user password to P@ssw0rd123.

ans:

In case of MariaDB use below mentioned queries:

i. Login to mysql database server: - mysql -u root

and then run the following queries in it.

ii. USE mysql;

iii. UPDATE user SET password=PASSWORD('P@ssw0rd123') WHERE User='root' AND Host = 'localhost';

iv. FLUSH PRIVILEGES;



In case of MySQL use below mentioned queries:

i. Login to mysql database server: - mysql -u root -p

(enter password what you got from sudo grep 'temporary password' /var/log/mysqld.log command earlier)

and then run the following queries in it.

ii. SET PASSWORD = PASSWORD('P@ssw0rd123');

iii. FLUSH PRIVILEGES;

# Create a MySQL user kk_user and set its password to S3cure#3214

Login to MySQL: mysql -u root -p

Password is - P@ssw0rd123

Use query: CREATE USER 'kk_user'@'localhost' IDENTIFIED BY 'S3cure#3214';

# Grant full access on kk_db database to kk_user user.

Login to MySQL: mysql -u root -p

Password is - P@ssw0rd123

Use query: GRANT ALL PRIVILEGES ON kk_db.* TO 'kk_user'@'localhost';

