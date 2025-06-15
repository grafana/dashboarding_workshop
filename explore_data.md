# Let's explore your data 
### MySQL Datasource
Browse to Explore mode, select the mysql-parkrun datasource.<br/>
Play around a bit, select different tables, try to order by and so on:<br/>
![image](https://github.com/user-attachments/assets/6614fcd5-8a58-40e7-8633-83eb4dcb342c)
Example output of the results table:<br/>
![image](https://github.com/user-attachments/assets/b0b3e6b4-8d45-42d5-8642-6d7c9e90879a)

### Infinity Datasource
We will also make use of the [Infinity Plugin](https://grafana.com/docs/plugins/yesoreyeram-infinity-datasource/latest/) available in Grafana. <br/>
The Infinity data source plugin allows you to query and visualize data from JSON, CSV, GraphQL, XML, and HTML endpoints. You can extract various fields/data elements from the response and then visualise as a table or graphs inside Grafana. <br/><br/>
Browse to Explore mode, and select the Inifinity datasource:<br/>
![image](https://github.com/user-attachments/assets/f45e3059-7a83-4261-b653-2ae1622fb835)
<br/><br/>
Supply the following url:
```
http://localhost:8080/weather/bushy
```
And you should see: <br/>
![image](https://github.com/user-attachments/assets/d90e2a07-2a53-4d7c-aceb-7abafa834fe8)
<br/><br/>
Almost there, we need to extract the `saturday_data` array and look at the data inside it. Expand the `Parsing options & Result fields` tab:<br/>
![image](https://github.com/user-attachments/assets/61e84fcb-7f44-44de-98a6-7b388e932a95)
Supply the value: `saturday_data`
<br/><br/>
And now we should see the proper tabular data:<br/>
![image](https://github.com/user-attachments/assets/63e517e6-ef7f-4975-8f56-bbff00b73b4f)

Alright, we're making progress!

<br/><br/>
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
