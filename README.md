# flask_4_databases_mysql_vm

## Overview

This repository focuses on setting up and running MySQL on a cloud Virtual Machine (VM). We have set up a VM using Microsoft Azure and connected Flask to the MySQL instance to display data from the database.


## Setting Up MySQL on Azure VM

### 1. VM Configuration

- Create a virtual machine on Microsoft Azure.
- Add a MySQL port (usually `3306`) in the networking configuration.

### 2. SSH into VM

- Access the VM using SSH: `ssh <username>@<IP address>`.

### 3. MySQL Installation

- Update the VM: `sudo apt-get update`.
- Install MySQL: `sudo apt install mysql-client mysql-server`.


- Log into MySQL: `sudo mysql`.
- Create a new user: `CREATE USER '<user>'@'%' IDENTIFIED BY '<password>'`.
- Confirm the user was created: `SELECT user FROM mysql.user;`.
- Grant privileges to the new user: `GRANT ALL PRIVILEGES ON *.* TO '<user>'@'%' WITH GRANT OPTION`.

## Connecting to MySQL Workbench

- Configure the MySQL instance to allow external connections.
- Modify the MySQL configuration file: `sudo nano /etc/mysql/mysql.conf.d/mysqld.conf`.
- Set `bind-address` and `mysqlx-bind-address` to `0.0.0.0`.
- Restart MySQL: `/etc/init.d/mysql restart`.
- Create a new connection in MySQL Workbench using VM IP as the hostname, the username, and the associated password.

## Database Schema

- In MySQL Workbench, create a database (e.g., `database`) and define tables (e.g., `patient` and `doctors`).
- Add columns as needed, set primary keys, and establish relationships between tables.
- Insert sample data into the tables.

I created two tables in the database. The first table, named "employee," stored information about employees, including their unique employee_id, employee_name, and role. The employee_id served as the primary key for this table. The second table, "hospital_department," managed data related to hospital departments, featuring attributes such as department_id, department_name, and department_head. The department_head attribute was linked as a foreign key to an employee's employee_id. The primary key for this table was department_id.

## Flask Deployment Issue 

I encountered a deployment issue while working on this project. Specifically, I faced difficulties deploying the Flask application to our target environment. Despite my efforts, the application did not deploy successfully, and I am actively working to resolve the issue. I'm attaching a screenshot of the error. 
<img width="1432" alt="Screenshot 2023-10-12 at 1 07 08 AM" src="https://github.com/Jannath19/flask_4_databases_mysql_vm/assets/124007534/35ec5eb6-35a3-4382-86b7-795fd78f6eff">


