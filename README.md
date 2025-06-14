# Creating account and logging in
Click on Sign up:

![image](https://github.com/user-attachments/assets/d2a6d7dd-d7ca-44ea-bf30-75ea0d01e0dd)

<br/><br/>
Provide some account details: <br/>
You don't need to supply your real name or email, but you will need to remember what it was if you want to log in again!

![image](https://github.com/user-attachments/assets/623f952c-6f75-4fc0-b6d3-c325d8ca00ca)

<br/><br/>
Click on Dashboards:
  
![image](https://github.com/user-attachments/assets/36daa846-de69-4476-94d0-adffe8730b3b)

<br/><br/>
Create a new folder:

  ![image](https://github.com/user-attachments/assets/12bd1c07-fc48-4e65-a88e-6b37eb74b416)

<br/><br/>
Give it a name (your name ? or a descriptive name you will remember):
  
![image](https://github.com/user-attachments/assets/e3be53a6-f137-45a0-b840-f680eeff70a4)

<br/><br/>
Click on Manage Permissions:
  
  ![image](https://github.com/user-attachments/assets/ee36119a-5590-421b-86b4-1a2d575137fd)

<br/><br/>
Remove both "Editor" and "Viewer" permission. The "Admin" permission will remain, you can't delete it:
  
![image](https://github.com/user-attachments/assets/4ee79f64-046a-4ae1-924b-1d96db75f8f3)

So that it looks like:

![image](https://github.com/user-attachments/assets/32fe9fc1-1d7e-420f-8a3a-1ac696fb7595)

Now only you have access to your own folder and others won't be able to see your work/dashboards today and accidentally make changes 

<br/><hr/>
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

# Creating our first dashboard
We will use the current data in Explore mode, and convert that into a dashboard that we can further iterate and build on. 
<br/><br/>
On the top of the page, click on `Add` and then `Add to dashboard`:<br/>
![image](https://github.com/user-attachments/assets/a9001df4-ac0e-4735-bcd2-b55270171e09)
<br/><br/>
Ensure `New dashboard` is selected, then click on `Open in new tab`:<br/>
![image](https://github.com/user-attachments/assets/82401b0c-26bd-483e-8886-99d80a8889a5)
<br/><br/>
You should now see a fairly average looking dashboard with a single panel on it:<br/>
![image](https://github.com/user-attachments/assets/a45588a3-d7f0-4638-afd0-3d949b7ff566)
<br/><br/>
Let's save it, and then we can get to building: <br/>
![image](https://github.com/user-attachments/assets/2bf9c6e9-1d42-4cde-a717-35c5aca4c2ca)
<br/><br/>
Give it a title you will remember, and then remember to save it in the folder you created earlier!
![image](https://github.com/user-attachments/assets/558ed514-fe79-422e-b8b4-f4f831ad7e11)
<br/><br/>

<hr/>

# Template Variables
A [variable](https://grafana.com/docs/grafana/latest/dashboards/variables/) is a placeholder for a value. You can use variables in metric queries and in panel titles. So when you change the value, using the dropdown at the top of the dashboard, your panel’s metric queries will change to reflect the new value.
<br/><br/>
Variables allow you to create more interactive and dynamic dashboards. Instead of hard-coding things like server, application, and sensor names in your metric queries, you can use variables in their place. Variables are displayed as dropdown lists at the top of the dashboard. These dropdowns make it easy to change the data being displayed in your dashboard.
<br/>
![image](https://github.com/user-attachments/assets/56d48a44-d059-4ea7-9138-c9856aa46162)
<br/>
### Creating your template variable
On your dashboard, hit the `Edit` button:<br/>
![image](https://github.com/user-attachments/assets/9d6ab857-9656-4d0e-8909-421fe50a57ad)
<br/><br/>
Then `Settings`:<br/>
![image](https://github.com/user-attachments/assets/62f48bb8-5b6f-43fe-bd20-e5c8815a3d62)
<br/><br/>
Select the `Variables` tab:<br/>
![image](https://github.com/user-attachments/assets/4b3303a8-d882-4b2b-8106-3c781c8198dc)
<br/><br/>
And finally, `Add variable` to add your first:<br/>
![image](https://github.com/user-attachments/assets/25ca6670-dd8b-4ce8-9183-8bd3d3bac8dd)
<br/><br/>

Notice how you can add different types of variables, like `Query`, `Textbox`, `Constant` and so on. Use `Query` for this configuration:<br/>
![image](https://github.com/user-attachments/assets/a58cc2f8-a0e5-4937-87cc-11a22946dadd)
<br/><br/>
And set the Name to `Parkrun`:<br/>
![image](https://github.com/user-attachments/assets/68b702d3-a4fb-4089-af11-c5e6f3cea45a)
<br/><br/>
For the next bit, you need to set 3 things:<br/>
* Select the `Infinity` datasource
* Supply the url `http://localhost:8080/parks`
* use the `name` field to extract
<br/>
Like so:
![image](https://github.com/user-attachments/assets/cc4b25ab-e859-4bb2-b4b2-958246f007ec)
  






