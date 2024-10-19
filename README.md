# Monitoring MariaDB for Competitive Programming Online Judge
> # Table of Contents
  >>Introduction  
  >>Requirements  
  >>Monitoring Methods  
  >>Performance Schema  
  >>Information Schema  
  >>Query Logs  
  >>Monitoring Tools  
  >>Server Status Variables  
  >>Alerts and Notifications  
  >>System Resource Monitoring  
  >>Backup and Recovery Monitoring  
  >>Database Profiling  
  >>User Activity Monitoring  
  >>Transaction Monitoring  
  >>Replication Monitoring  
>Setup Instructions  
  >>Conclusion
  
># Introduction
>This document outlines the methods and best practices for monitoring a MariaDB database used as a backend for a competitive programming online judge.   Effective monitoring is essential for ensuring the >performance, reliability, and integrity of the database.

># Requirements
>>MariaDB server installed and running  
>>Access to the command line interface  
>>Appropriate permissions to access monitoring features and tools.

Enabling Performance Schema
Step 1: Accessing the MariaDB Configuration File
Open a Terminal: Access your terminal or command prompt. <br>
Locate the Configuration File:
The main configuration file for MariaDB is typically named my.cnf or my.ini. <br>
Common locations for the file include:
/etc/my.cnf (Linux) <br>
/etc/mysql/my.cnf (Linux) <br>
C:\Program Files\MariaDB\MariaDB <version>\my.ini (Windows) <br>
Open the Configuration File:
Use a text editor to open the configuration file. For example, on a Linux system:
bash
Copy code
sudo nano /etc/my.cnf
Or for Ubuntu:
bash
Copy code
sudo nano /etc/mysql/my.cnf
Step 2: Editing the Configuration File
Find the [mysqld] Section:
Scroll through the file to locate the [mysqld] section. If it does not exist, you can create it. <br>
Add or Modify Performance Schema Settings:
Add the following line under the [mysqld] section to enable the Performance Schema:
ini
Copy code
performance_schema=ON
If you want to adjust the memory allocation for the Performance Schema, you can also add:
ini
Copy code
performance_schema_instrument = '%=on'
Make sure to check if there are existing entries for performance_schema, and modify them if necessary. <br>
Save the Changes:
If you are using nano, press CTRL + O to save, then CTRL + X to exit. <br>
If using vim, type :wq and press Enter to save and exit. <br>
Step 3: Restarting the MariaDB Service
Restart the MariaDB Service:
To apply the changes, you need to restart the MariaDB service. Use the following command based on your system:
For Ubuntu or Debian:
bash
Copy code
sudo systemctl restart mariadb
For CentOS or RHEL:
bash
Copy code
sudo systemctl restart mysql
For older systems:
bash
Copy code
sudo service mysql restart
Step 4: Verifying Performance Schema is Enabled
Log in to MariaDB:
Access the MariaDB command-line interface:
bash
Copy code
mysql -u root -p
Enter your root password when prompted. <br>
Check Performance Schema Status:
Run the following SQL command to verify that the Performance Schema is enabled:
sql
Copy code
SHOW VARIABLES LIKE 'performance_schema';
If it is enabled, you should see:
diff
Copy code
+-------------------+-------+
| Variable_name     | Value |
+-------------------+-------+
| performance_schema | ON    |
+-------------------+-------+
Using Performance Schema
Once enabled, you can start using the Performance Schema to monitor various aspects of the database. You can query different tables within the performance_schema database to get insights into wait events, query performance, and more. <br>

For example:

sql
Copy code
SELECT * FROM performance_schema.events_waits_summary_global_by_event_name;
Conclusion
You have successfully enabled the Performance Schema in MariaDB. This powerful tool will help you monitor and diagnose performance issues, ensuring your database operates efficiently. <br>







# Enabling Performance Schema in MariaDB
> # Table of Contents
>> Introduction.  
>>Requirements.  
>>Enabling Performance Schema.  
>>>Step 1: Accessing the MariaDB Configuration File.  
>>>Step 2: Editing the Configuration File.  
>>>Step 3: Restarting the MariaDB Service.  
>>>Step 4: Verifying Performance Schema is Enabled.  
>>Using Performance Schema.
>>Conclusion.  
> # Introduction.  
>>The Performance Schema is a feature in MariaDB that provides insights into the performance of the database server.It collects data about query execution, wait events, and resource usage, allowing database administrators to diagnose performance issues effectively.
> # Requirements
>>MariaDB Server: Ensure you have MariaDB version 5.5 or later installed.  
>>Access: You need to have root or sufficient privileges to modify the MariaDB configuration and restart the service.  
>>Text Editor: A text editor installed on your system (e.g., nano, vim).  


