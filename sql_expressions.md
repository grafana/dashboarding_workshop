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


[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
