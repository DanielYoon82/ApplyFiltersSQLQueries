<h1>Apple Filters to SQL Queries</h1>

<h2>Description</h2>
In this scenario, it was my duty as a security analyst to investigate potential security issues and to ensure the system was safe. The following displays tasks that were performed to identify security issues.
<br />


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>


<b>Open the file that contains the allow list</b><br />
There was a potential security incident that took place after business hours. Any failed log in attempts after hours needed to be investigated. <br/>
The following code displays how I created a SQL query to filter for failed login attempts that occurred after business hours. <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/ApplyFiltersSQLQueries/blob/main/images/SQLfla.jpg" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
The query displayed an output of all log in attempts after 18:00. I  then examined the data from the log_in_attempts table. From there, I inputted a WHERE with an AND operator to only display log in attempts that were unsuccessful after 18:00. The first condition is login_time > '18:00', the second condition is success = FALSE <br />
<br />                                                                                                                                                    
<br />
<b>Retrieve login attempts on specific dates</b> <br/>
A suspicious activity occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or 2022-05-08 needed to be inspected. <br />
The following code displays how I created a SQL query to filter for login activity on the specified dates. <br />
 This code allows me to access the "allow_list.txt" file into a string format which enables me to later use the string to organize and extract data from the Python program: <br />
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/UpdateFileWithPython/blob/main/images/GHFileContents.jpg" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
CONVERT THE STRING INTO A LIST <br />
To remove individual IP addresses from the allow list, It needs to be in the list format. I used the .split() method to convert the ip_addresses string into a list. The .split() function is called by appending it to a string variable. It does this by converting the data of a string to a list. The purpose of splitting ip_addresses into a list is to make it easier to remove IP addresses from the allow list. In this algorithm, the .split() function retrieves the data stored in the variable ip_addresses and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable ip_addresses:  <br/>
<br />
<img src="https://github.com/DanielYoon82/UpdateFileWithPython/blob/main/images/GHConvertString.jpg" height="55%" width="55%" alt="Disk Sanitization Steps"/>
<br />
<br />
ITERATE THROUGH THE REMOVE LIST <br />
A vital part of my algorithm is to iterate through the IP addresses that are elements in the remove_list. To do this, I created a for loop. The purpose of the for loop in this algorithm is to apply specific code statements to all elements in a sequence. The for keyword starts the loop. It is followed by the loop variable element and the keyword in. The keyword in initiates the iteration through the sequence ip_addresses and assigns each value to the loop variable element:  <br/>
<br />
<img src="https://github.com/DanielYoon82/UpdateFileWithPython/blob/main/images/GHIterateList.jpg" height="38%" width="38%" alt="Disk Sanitization Steps"/>
<br />
<br />
REMOVE IP ADDRESSES THAT ARE ON THE REMOVE LIST <br />
This algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list. First, within my for loop, I created a conditional that evaluated whether or not the loop variable element was found in the ip_addresses list. I did this because applying .remove() to elements that were not found in ip_addresses would result in an error. <br />
<br />
I applied .remove() to ip_addresses. I passed in the loop variable element as the argument so that each IP address that was in the remove_list would be removed from ip_addresses: <br /> 
<br />
<img src="https://github.com/DanielYoon82/UpdateFileWithPython/blob/main/images/GHRemoveIP.jpg" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
<br />
UPDATE THE FILE WITH THE REVISED LIST OF IP ADDRESSES <br/>
Lastly, in this algorithm, I needed to update the allow list file with the revised list of IP addresses. To do this, I needed to convert the list back into a string. I used the .join() method for this. The .join() method combines all items into a string. I used the .join() method to create a string from the list ip_addresses so that I could be changed to an argument in the .write() method when writing to the file "allow_list.txt": <br />
<br />
<img src="https://github.com/DanielYoon82/UpdateFileWithPython/blob/main/images/Updatefile.jpg" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Then, I used another with statement and the .write() method to update the file. <br /> 
<br />
For this, I used a second argument of "w" with the open() function in my with statement. When using this argument "w", I can call the .write() function . The .write() function writes string data to a file and replaces any existing data.
<br />
<br />
In this scenario I wanted to write the updated allow list as a string to the file "allow_list.txt". The restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the .write() function to the file object file that I identified in the with statement. I passed in the ip_addresses variable as the argument to specify that the contents of the file specified in the with statement should be replaced with the data in this variable. <br />
<br />
<img src="https://github.com/DanielYoon82/UpdateFileWithPython/blob/main/images/write.1.jpg" height="52%" width="52%" alt="Disk Sanitization Steps"/> <br />
