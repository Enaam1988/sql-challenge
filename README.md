# sql-challenge
# Database Tables and Data Analysis
- [Overview](#overview)
- [Database Tables](#database-tables)
  - [Table 1: Titles](#table-1-titles)
  - [Table 2: Employees](#table-2-employees)
  - [Table 3: Departments](#table-3-departments)
  - [Table 4: Dept_Manager](#table-4-dept_manager)
  - [Table 5: Dept_Emp](#table-5-dept_emp)
  - [Table 6: Salaries](#table-6-salaries)
- [Data Analysis](#data-analysis)
- [Getting Started](#getting-started)
## Overview
Welcome to the Pewlett Hackard Employee Database Project! As a newly hired data engineer at Pewlett Hackard, you're embarking on a research project focused on the employees who worked at the company during the 1980s and 1990s. The project aims to design and create a SQL database to store and analyze data extracted from six CSV files, the only remnants of the company's employee database from that era.

### Project Objectives

This project involves three main components:

1. **Data Modeling:** The first phase of the project focuses on understanding the structure of the available data and designing appropriate SQL tables to hold this data. This includes defining data types, primary keys, and relationships between tables.

2. **Data Engineering:** Once the table schemas are defined, the next step is to create these tables in a SQL database and import the data from the provided CSV files into these tables.

3. **Data Analysis:** With the data successfully imported, the project concludes with a series of data analysis tasks. SQL queries will be used to extract insights, answer questions, and perform various analyses on the employee data.
## Database Tables

In this section, we provide detailed information about the database tables used in this project, including their columns and relationships.

### Table 1: Titles

- **Table Name**: Titles
- **Columns**:
  - title_id (Primary Key, VARCHAR, 10): A unique identifier for each title.
  - title (VARCHAR, 50): The title name.
- **Relationships**: 
  - None

### Table 2: Employees

- **Table Name**: Employees
- **Columns**:
  - emp_no (Primary Key, INT): A unique identifier for each employee.
  - emp_title_id (VARCHAR, 10, Foreign Key to Titles.title_id): The title associated with the employee.
  - birth_date (DATE): The employee's date of birth.
  - first_name (VARCHAR, 50): The employee's first name.
  - last_name (VARCHAR, 50): The employee's last name.
  - sex (CHAR, 1): The employee's gender.
  - hire_date (DATE): The date the employee was hired.
- **Relationships**:
  - Foreign Key: emp_title_id references Titles.title_id.

### Table 3: Departments

- **Table Name**: Departments
- **Columns**:
  - dept_no (Primary Key, VARCHAR, 10): A unique identifier for each department.
  - dept_name (VARCHAR, 50): The name of the department.
- **Relationships**:
  - None

### Table 4: Dept_Manager

- **Table Name**: Dept_Manager
- **Columns**:
  - emp_no (Primary Key, INT, Foreign Key to Employees.emp_no): The unique identifier for an employee who manages a department.
  - dept_no (Primary Key, VARCHAR, 10, Foreign Key to Departments.dept_no): The unique identifier for the department managed by the employee.
- **Relationships**:
  - Foreign Key: emp_no references Employees.emp_no.
  - Foreign Key: dept_no references Departments.dept_no.

### Table 5: Dept_Emp

- **Table Name**: Dept_Emp
- **Columns**:
  - emp_no (Primary Key, INT, Foreign Key to Employees.emp_no): The unique identifier for an employee working in a department.
  - dept_no (Primary Key, VARCHAR, 10, Foreign Key to Departments.dept_no): The unique identifier for the department where the employee works.
- **Relationships**:
  - Foreign Key: emp_no references Employees.emp_no.
  - Foreign Key: dept_no references Departments.dept_no.

### Table 6: Salaries

- **Table Name**: Salaries
- **Columns**:
  - emp_no (Primary Key, INT, Foreign Key to Employees.emp_no): The unique identifier for an employee's salary record.
  - salary (INT): The salary amount associated with the employee.
- **Relationships**:
  - Foreign Key: emp_no references Employees.emp_no.

