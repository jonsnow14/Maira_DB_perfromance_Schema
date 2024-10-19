Monitoring MariaDB for Competitive Programming Online Judge
Table of Contents
Introduction
Requirements
Monitoring Methods
Performance Schema
Information Schema
Query Logs
Monitoring Tools
Server Status Variables
Alerts and Notifications
System Resource Monitoring
Backup and Recovery Monitoring
Database Profiling
User Activity Monitoring
Transaction Monitoring
Replication Monitoring
Setup Instructions
Conclusion
License
Introduction
This document outlines the methods and best practices for monitoring a MariaDB database used as a backend for a competitive programming online judge. Effective monitoring is essential for ensuring the performance, reliability, and integrity of the database.

Requirements
MariaDB server installed and running
Access to the command line interface
Appropriate permissions to access monitoring features and tools
Knowledge of SQL and basic database management

Monitoring Methods

Performance Schema
Description: Provides insights into the performance of MariaDB by collecting data on query execution, wait events, and resource usage.
Usage: Enable and configure the Performance Schema in the MariaDB configuration file.

Information Schema
Description: Contains metadata about the database, such as tables, columns, and user privileges.
Usage: Query the Information Schema to retrieve information about table sizes, row counts, and user connections.

Query Logs
Description: Capture queries that exceed a specified execution time.
Usage: Enable slow query logging to identify slow-running queries impacting performance.

Monitoring Tools
Description: Utilize third-party tools for real-time monitoring.

Popular Tools:
Prometheus
Grafana
Zabbix
Datadog
Percona Monitoring and Management (PMM)

Server Status Variables
Description: Monitor key status variables to gain insights into server performance.
Key Metrics: Connections, Threads, Queries, Table Locks.

Alerts and Notifications
Description: Set up alerts to notify administrators of performance issues.
Implementation: Use monitoring tools to define alert rules based on thresholds.

System Resource Monitoring
Description: Monitor system-level metrics that impact MariaDB performance.

Tools: top/htop, iostat, vmstat, netstat.

Backup and Recovery Monitoring
Description: Monitor backup processes for data integrity.
Key Features: Track backup job statuses and time taken for backups.

Database Profiling
Description: Analyze query execution to identify performance bottlenecks.
Implementation: Enable profiling for specific queries.

User Activity Monitoring
Description: Track user activity within the database.

Key Features: Monitor user connections and query activity.
Transaction Monitoring
Description: Monitor transactions to identify locking issues.
Key Features: Track active transactions and wait times.
Replication Monitoring
Description: Monitor the replication status if using replication.
Key Features: Check replication lag and status of replication threads.
