<h1>Apple Filters to SQL Queries</h1>

<h2>Description</h2>
In this scenario, it was my duty as a security analyst to investigate potential security issues and to ensure the system was safe. The following displays tasks that were performed to identify security issues.
<br />


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>


- <b>Retrieve after hours failed login attempts</b> <br />
There was a potential security incident that took place after business hours. Any failed log in attempts after hours needed to be investigated.
The following code displays how I created a SQL query to filter for failed login attempts that occurred after business hours. <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLfla.jpg" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<br />
The query displayed an output of all log in attempts after 18:00. I  then examined the data from the log_in_attempts table. From there, I inputted a WHERE with an AND operator to only display log in attempts that were unsuccessful after 18:00. The first condition is login_time > '18:00', the second condition is success = FALSE <br />
<br />                                                                                                                                                    
<br />

- <b>Retrieve login attempts on specific dates</b> <br/>
A suspicious activity occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or 2022-05-08 needed to be inspected. <br />
The following code displays how I created a SQL query to filter for login activity on the specified dates. <br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLLogInAttempts.jpg" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
First, I initiated the task by selecting all data from the log_in_attempts table. Secondly, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09'. The second condition is login_date = '2022-05-08';, which filters for logins on 2022-05-08.
<br />
<br />

- <b>Retrieve login attempts outside of Mexico</b> <br />
From investigated login attempts, there appeared to be an issue everywhere other than the country of Mexico. The following query was then created to further investigate the issue with logins. <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLMX.jpg" height="63%" width="63%" alt="Disk Sanitization Steps"/>
</p>
First, I inputted the query to retrieve all data from the log_in_attempts table. I then used a WHERE clause with NOT to filter. I utilized  LIKE with MEX% syntax to match due to the dataset correlating to Mexico as MEX and MEXICO. 
<br />
<br />

- <b>Retrieve employees in Marketing</b> <br />
An update was to be performed for certain employees in the Marketing Department. To do that, data from that department needed to be retrieved. The following code shows how I created a SQL query to filter specifically for employees from the Marketing department in the East building.  <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLeM.jpg" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
I started by selecting all data from the employees table. I then used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I inputted LIKE with East% as the pattern due to ‘East’ having a suffix.
<br />
<br />

- <b>Retrieve employees in Finance or Sales</b> <br />
A unique security update needed to be implemented only to the Finance and Sales departments. The code displays how I created a SQL query to filter from employees in the Finance or Sales departments. <br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLFS.jpg" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
First, I selected data from the employees table. Secondly, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. The OR operator instead of AND was used due to data needed for either department. The first condition is department = 'Marketing' and the second condition is the office LIKE 'East%'.
<br />
<br />

- <b>Retrieve all employees not in IT</b> <br/>
A security update was necessary for all departments except for Information Technology. The following displays how I created a SQL query to filter for employees not in the  Information Technology department. <br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLnoIT.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
I started by gathering all data from the employees table. Secondly, I used a WHERE clause with NOT to filter for employees not in the Information Technology department.
<br />
<br />

- <b>Summary</b> <br />
I demonstrated SQL queries to gather relevant information on login attempts and employee machines. I utilized two different tables, log_in_attempts and employees. I employed the AND, OR, and NOT operators to filter for the particular information needed for each task. In addition, the LIKE and the percentage sign (%) wildcard was used to filter patterns.
<br />
<br />
