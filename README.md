# task3_elevate_labs


Employee and Department Management System
This project is designed to manage employee and department information in a PostgreSQL database. It involves creating tables for employees and departments, inserting sample data, and running SQL queries to analyze and manage the information.

Table of Contents
Overview

File Structure

Database Setup

SQL Queries

How to Execute the SQL File

License

Overview
This project consists of two main tables:

employees: Stores information about employees such as their personal details, salary, hire date, job, manager, and associated department.

departments: Stores department details, including the department name and its manager.

The project also includes SQL queries for managing and querying this data. These queries demonstrate the use of basic SQL operations such as SELECT, WHERE, ORDER BY, GROUP BY, as well as advanced topics like JOINs, subqueries, and aggregate functions.

File Structure
The project includes the following files:

queries.sql: Contains SQL queries for creating tables, inserting data, and running analysis queries.

employees.csv: A CSV file containing employee data (if you prefer to import data directly).

departments.csv: A CSV file containing department data.

Database Setup
To set up the PostgreSQL database for this project, follow the steps below:

Install PostgreSQL: Ensure that PostgreSQL is installed on your system. If you haven't done so already, you can download it from the official PostgreSQL website.

Create a Database: After installing PostgreSQL, open your terminal or psql client and create a new database:

bash
Copy
Edit
CREATE DATABASE employee_management;
Connect to the Database: Connect to the database you just created:

bash
Copy
Edit
psql -U your_username -d employee_management
Execute the SQL File: Use the following command to execute the queries.sql file, which will create the tables and insert sample data into your database:

sql
Copy
Edit
\i '/path/to/queries.sql'
SQL Queries
The queries.sql file includes the following SQL operations:

1. Table Creation
Create departments Table: Creates a table for department details.

Create employees Table: Creates a table for employee details, including references to the departments table.

2. Insert Data
Sample data is inserted into both the departments and employees tables.

3. Basic Queries
SELECT with WHERE and ORDER BY: Retrieve employees with a salary greater than 60,000, ordered by hire date.

GROUP BY with Aggregate Functions: Calculate the total salary by department.

JOINS: Perform inner joins between employees and departments to retrieve employee details along with their respective departments.

Subqueries: Retrieve employees whose salary is higher than the average salary of all employees.

Example queries:

sql
Copy
Edit
SELECT first_name, last_name, salary
FROM employees
WHERE salary > 60000
ORDER BY hire_date;

SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id
ORDER BY total_salary DESC;
How to Execute the SQL File
To execute the SQL file and run the queries:

Open your terminal or command prompt.

Connect to the PostgreSQL database:

bash
Copy
Edit
psql -U your_username -d employee_management
Run the SQL file using the following command:

sql
Copy
Edit
\i '/path/to/queries.sql'
Replace '/path/to/queries.sql' with the actual path to your SQL file.

Once executed, you can run additional queries or modify the schema and data as needed.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Explanation of Key Concepts
In this project, several fundamental and advanced SQL concepts are demonstrated:

Data Integrity: The FOREIGN KEY constraints ensure that the relationships between employees and departments are consistent. The manager_id column in the employees table is a self-referencing foreign key, ensuring that employees can have managers who are also employees.

Normalization: The structure of the database follows basic normalization principles. This reduces redundancy by separating employee and department details into separate tables, minimizing data duplication.

Aggregate Functions: The project demonstrates the use of aggregate functions such as SUM and AVG to perform analytical operations on the dataset, which are commonly used in data processing and reporting.

Subqueries: The subquery in the WHERE clause demonstrates how you can use nested queries to filter data based on the results of another query.
