# Hospital Management System in PHP has Stored Cross Site Scripting vulnerability in manage-doctors.php

## supplier

https://code-projects.org/hospital-management-system-using-php-source-code/

## Vulnerability file

/hospital/hms/admin/manage-doctors.php

## describe

In /hospital/hms/admin/manage-doctors.php. There are unrestricted stored cross site scripting attacks and injection attacks in the Hospital Management System. The controllable parameters are as follows: doctorName. This function will execute the user parameter without restriction into the echo statement. Malicious attackers can exploit this vulnerability to obtain sensitive information from clients

**Code analysis**

Updating and Querying data from the database and storing it in the <?php echo $row['doctorName'];?>, and the echo doctorName is not filtered, resulting in the execution of XSS statements.

## POC

```
<script>alert(1)</script>
```


**Result**
