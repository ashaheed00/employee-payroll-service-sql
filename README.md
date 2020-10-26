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