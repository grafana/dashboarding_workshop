# SQL Expressions
SQL Expressions are server-side expressions that manipulate and transform the results of data source queries using MySQL-like syntax. They allow you to easily query and transform your data after it has been queried, using SQL, which provides a familiar and powerful syntax that can handle everything from simple filters to highly complex, multi-step transformations.
<br/><br/>
In Grafana, a server-side expression is a way to transform or calculate data after it has been retrieved from the data source, but before it is sent to the frontend for visualization. Grafana evaluates these expressions on the server, not in the browser or at the data source.
<br/>
![image](https://github.com/user-attachments/assets/b164276f-b0a1-4471-88a7-22a948e309c1)
<br/><br/>
## Lab steps
<br/>
In this lab we will add an additional panel that will show us the top participating clubs for that Parkrun:<br/>

![image](https://github.com/user-attachments/assets/eabb2a02-b454-48a9-8d77-b767574a3979)
<br/><br/>
The main problem we have is that we will need to combine two datasets together to solve this problem. The name of the Parkrun (eg, `bushy` comes from our JSON API, which we can then map to our MySQL `results` table with a shared field where we can count, aggregate our data. However, as these two datasets comes from different types of datasources, we will need to do something special in Grafana. <br/>
![image](https://github.com/user-attachments/assets/428ba70a-67cb-4da6-bb45-124feb8ec1b6)
<br/><br/>

Click to add a new Panel, then select the `Visualization` option:<br/>
![image](https://github.com/user-attachments/assets/301fd9ec-87f8-48ce-86b7-5370a8e3ba62)
<br/><br/>
Select the `Pie Chart` visualisation:<br/>
![image](https://github.com/user-attachments/assets/a8199fa0-6adc-4a60-8967-2c02e168d4ae)

<br/><br/>In your query builder, change the datasource to --Mixed--, so from this:<br/>
![image](https://github.com/user-attachments/assets/705ee387-949c-49b2-bebe-93c7eedd2f3e)
<br/>To this:<br/>
![image](https://github.com/user-attachments/assets/955cd568-4313-4eab-af80-aa23d0dc32bb)
<br/>Using this mode will allow us to mix results from different types of datasources. For imagine, mixing Cloudwatch with Prometheus, or in our case, the JSON output from our API with MySQL. 
<br/><br/>
Now for query 'A', select the MySQL datasource, like so:<br/>
![image](https://github.com/user-attachments/assets/e0df749b-8186-4a5c-ab06-09228fc66a11)
<br/><br/>
And select the `code` mode:<br/>
![image](https://github.com/user-attachments/assets/ceaea893-ad2b-4321-a888-78d2171c4122)
<br><br/>
Copy the follwing SQL code:<br/>
```
SELECT 
  park_id, club, count(*) as club_count 
FROM 
  results 
WHERE 
  club != "NULL" 
GROUP BY 
  club, park_id 
ORDER BY 
  club_count DESC
```
and paste:<br/>
![image](https://github.com/user-attachments/assets/18b5d5c7-f2ba-4cc9-bcc2-bd611543e88d)
<br/>
Explanation: We are counting the number of park runners who belong to a club, per Parkrun. 
<br/><br/>
Your visualisation should update with what appears to be a pie-chart, but our data is not correct yet. Toggle the `table` view: <br/>
![image](https://github.com/user-attachments/assets/d7a9c380-e264-4645-9513-f0a0133ab96a)
<br/><br/>
You should see a table with the raw data. What we want to do now is to filter our results so that when you select `bushy` from the dropdown, then it automatically filters the results to only show for event_id 1 (the id that maps to bushy). And so on:<br/>
![image](https://github.com/user-attachments/assets/b706e8e4-97e7-4f4e-82c8-2da988856fed)
<br/><br/>
We can use our JSON API to get the park run name, as well as the event_id, then map that to our SQL output. 
<br/><br/>
Add another query:<br/>
![image](https://github.com/user-attachments/assets/0b6f5acc-4fb3-438e-bb6b-cdcf53cd2b65)
<br/><br/>
This will bring up query `B` as you can see. Use the url:`http://localhost:8080/parks`<br/>
![image](https://github.com/user-attachments/assets/e2f90c29-eefc-4e11-af5d-e13695392c00)
<br/><br/>
The table will still have the same results, but you might have noticed that a dropdown has now appeared:<br/>
![image](https://github.com/user-attachments/assets/d1f4c451-87c4-4111-8bb7-c77cacc847e3)
<br/>
What you are seeing here is that each query in Grafana (query `A` and query `B` in our case) maps to an internal "table" inside Grafana. We can access each table by selecting from the dropdown:<br/>
![image](https://github.com/user-attachments/assets/767887e5-ef81-4ffc-801b-4469284a5ddc)
<br/>Here you can see `B` which is the internal reference that maps to the output of query B. 
<br/><br/>
If you select `B`, then the table output will update to something like:<br/>
![image](https://github.com/user-attachments/assets/e9965784-350d-4c69-afc8-b317df23dec9)
<br/><br/>
Switch back and forth between these two result sets. Notice something interesting. Something that is common between the two?<br/>
There is a common shared field called `park_id` between these two result sets. We can use SQL expressions to "join" these two tables together inside Grafana, like as if they were real SQL tables!
<br/><br/>
This time, add a new `Expression`:<br/>
![image](https://github.com/user-attachments/assets/8bed01d3-509b-4910-af83-ebeb1a9dfbae)
<br/><br/>
And scroll down to SQL Expressions:<br/>
![image](https://github.com/user-attachments/assets/916ffd4f-f93d-46b2-8a8f-cf774db6d42e)
<br/><br/>
This brings up query `C`. With this, you can now manipluate the output of query `A` and `B` as if they were tables to begin with, using SQL dialect. You can join tables, rename fields, change the order, count, group by and all the things you can do in SQL:<br/>
![image](https://github.com/user-attachments/assets/63b830e2-6ab0-489b-8059-8edbcee115ed)
<br/><br/>
Paste the following SQL in the box:<br/>
```
SELECT 
  A.*
FROM 
  A, B
WHERE 
  A.park_id = B.park_id
  AND B.name = "$Parkrun"
LIMIT 10
```
What we are doing here is to combine the two tables where we take the option that was selected in the dropdown in our panel (eg: `bushy`), then joining that table with the results table using the common park_id field. Notice how we use `A` and `B` as our table names. Those are the names of the queries in Grafana earlier.<br/>
For example:<br/>
![image](https://github.com/user-attachments/assets/94c71387-22de-4132-9baf-0687198dff0d)
<br/><br/>



<br/><br/>
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
