
# Hospital Management System has sql injection in admin login portal
CVE-2024-12969
## supplier

https://code-projects.org/hospital-management-system-using-php-source-code/

## Vulnerability file

hostpital/hms/admin/index.php

## describe

**Code analysis**

In the hostpital/hms/admin/index.php file of Hospital Management System, the username and password parameter is obtained, and the SQL statement is concatenated to the SQL statement without filtering the execution, resulting in SQL injection vulnerabilities and login as administrator
![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/hmss/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-26%20133407.png)
![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/hmss/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-26%20133105.png)
## POC

input

```
1' or 1=1-- -
```
in the username field and random string in the password field(over 6 characters)
![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/hmss/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-26%20133245.png)

**Result**

login as administrator:
![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/hmss/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-26%20133251.png)
