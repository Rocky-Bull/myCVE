#  Simple Admin Panel in PHP has Stored Cross Site Scripting vulnerability in editItemForm.php

## supplier 
https://code-projects.org/farmacia-in-php-css-javascript-and-mysql-free-download/
## Vulnerability file
editItemForm.php

## describe
In editItemForm.php. There are unrestricted stored cross site scripting attacks and injection attacks in the Simple Admin Panel. The controllable parameters are as follows: product_name and product_desc parameter. This function will execute the user parameter without restriction into the echo statement. Malicious attackers can exploit this vulnerability to obtain sensitive information from clients

**Code analysis**    

Updating and Querying data from the database and storing it in the <?=$row1['product_name']?>, and the echo product_name is not filtered, resulting in the execution of XSS statements.

![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-25%20142316.png)

## POC

```
<script>alert(1)</script>
```

![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-25%20141045.png)
![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-25%20141051.png)
![image](https://github.com/Rocky-Bull/myCVE/blob/main/images/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-25%20141407.png)
Click this Products button to trigger the cross-site scripting vulnerability.

```
http://localhost/admin_panel/#products
```

**Result**

![image]([https://github.com/user-attachments/assets/4ac05f98-aa5b-4e97-a50c-3c8ed574c663](https://github.com/Rocky-Bull/myCVE/blob/main/images/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-12-25%20141108.png))
