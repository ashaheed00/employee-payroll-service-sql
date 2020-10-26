# employee-payroll-service-sql
## UC1_CreateEmpPayrollServiceDB
```
CREATE DATABASE payroll_service;
SHOW DATABASE;
USE payroll_service;
```
## UC2_CreateEmployeePayrollTable
```
CREATE TABLE employee_payroll (
id          INT unsigned NOT NULL AUTO_INCREMENT,
name        VARCHAR(150) NOT NULL,
salary      DOUBLE NOT NULL,
start_date  DATE NOT NULL
PRIMARY KEY (id)
);
```
## UC3_AddEmpPayrollData
```
INSERT INTO employee_payroll (name, salary, start_date) VALUES
   ('Vishal', 1500000.00, '2018-02-06'),
   ('John', 2500000.00, '2016-10-12'),
   ('Asifa', 1800000.00, '2019-10-10');
```
## UC4_RetrieveAllData
```SELECT * FROM employee_payroll;```
## UC5_RetrieveSpecificData
#### Retrieve salary using name
```
SELECT salary FROM employee_payroll 
   WHERE name = 'John';
```
#### Retrieve employee name using start date
```
SELECT name FROM employee_payroll
   WHERE start_date BETWEEN
   CAST('2018-01-01' AS DATE) AND DATE(NOW());
```
## UC6_AbilityToAddGender
```
ALTER TABLE employee_payroll ADD gender CHAR(1) AFTER name;

UPDATE employee_payroll set gender ='M'
   where name = 'Vishal' or name = 'John';
UPDATE employee_payroll set gender ='F'
   where name = 'Asifa';
```
## UC7_Find_Sum_Avg_Count
#### Total salary of all the female employees
```
SELECT SUM(salary) FROM employee_payroll
WHERE gender = 'F' GROUP BY gender;
```
#### Average salary of male employees
```
SELECT AVG(salary) FROM employee_payroll
WHERE gender = 'M' GROUP BY gender;
```
#### Max and Min salary
```
SELECT MIN(salary) FROM employee_payroll;
```
```
SELECT MAX(salary) FROM employee_payroll;
```
#### Count of employee numbers and based on their genders
```
SELECT COUNT(id) FROM employee_payroll;
```
```
SELECT COUNT(id) FROM employee_payroll WHERE gender = 'M';
```