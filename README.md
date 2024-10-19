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
>>Appropriate permissions to access monitoring features and tools  





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


