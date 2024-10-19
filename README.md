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

# Enabling Performance Schema in MariaDB
> # Table of Contents
>> Introduction.  
>>Requirements.  
>>Enabling Performance Schema.  
>> Note : The performance schema cannot be activated at runtime - it must be set when the server starts by editing my.cnf configuration file.  
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

# Enabling Performance Schema
# Step 1: Accessing the MariaDB Configuration File.  
Open a Terminal: Access your terminal or command prompt.  

Locate the Configuration File:
>>The main configuration file for MariaDB is typically named my.cnf or my.ini.  
>>Common locations for the file include:
>>Linux
`/etc/my.cnf`.    
>>ubuntu.  
`/etc/mysql/my.cnf`    
>>Windows  
`C:\Program Files\MariaDB\MariaDB <version>\my.ini`.     
>Open the Configuration File:  
>Use a text editor to open the configuration file. For example, on a Linux system:    
`sudo nano /etc/my.cnf`. 
>> for Ubuntu:  
`sudo nano /etc/mysql/my.cnf`  
# Step 2: Editing the Configuration File
Find the [mysqld] Section:

>>Scroll through the file to locate the [mysqld] section. If it does not exist, you can create it. <br>
>>Add or Modify Performance Schema Settings:

>>Add the following line under the [mysqld] section to enable the Performance Schema:  
>>>>``` sql
>>>> performance_schema=ON
>>>>``` 
>>If you want to adjust the memory allocation for the Performance Schema, you can also add:    
>>>>``` sql
>>>>performance_schema_instrument = '%=on
>>>>```  
>>enables all instrumentation of all stages (computation units) in MariaDB:  
```  sql
>>>>performance_schema=ON  
>>>>performance-schema-instrument='stage/%=ON'  
>>>>performance-schema-consumer-events-stages-current=ON  
>>>>performance-schema-consumer-events-stages-history=ON  
>>>>performance-schema-consumer-events-stages-history-long=ON
```   
>>Make sure to check if there are existing entries for performance_schema, and modify them if necessary.    
>>Save the Changes:  
>>If you are using nano, press CTRL + O to save, then CTRL + X to exit.  
>>If using vim, type :wq and press Enter to save and exit.  
# Step 3: Restarting the MariaDB Service
>>Restart the MariaDB Service:    
>>To apply the changes, you need to restart the MariaDB service. Use the following command based on your system:
>>For Ubuntu or Debian:  

>>>``` linux  
>>>sudo systemctl restart mariadb
>>>```


# Step 4: Verifying Performance Schema is Enabled
>>Log in to MariaDB:  
>>Access the MariaDB command-line interface:  

>>>`mysql -u root -p`

>>Enter your root password when prompted.  
>>Check Performance Schema Status:  
>>Run the following SQL command to verify that the Performance Schema is enabled:  
>>>``` sql
>>>SHOW VARIABLES LIKE 'performance_schema'
>>>```

>>If it is enabled, you should see:

>>>+-------------------+-------+  
>>>| Variable_name     | Value |    
>>>+-------------------+-------+  
>>>| performance_schema | ON    |    
>>>+-------------------+-------+  


