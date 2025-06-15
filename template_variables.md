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
Like so:<br/>

![image](https://github.com/user-attachments/assets/9f8e6de2-ab4a-486e-9649-589b6b8ef50e)
<br/><br/>
Deselect `Allow custom values`. You should now see three parkrun names:<br/>

![image](https://github.com/user-attachments/assets/4a20725e-03a7-4f29-a859-eb94e1a7d82e)
<br/><br/>
If that looks good, then on the top right of your page, click on `Back to dashboard`:<br/>

![image](https://github.com/user-attachments/assets/c89a27c8-566f-41e9-a630-5d0cbccab1e3)
<br/><br/>
Fabulous, you have made your first dashboard variable!<br/>

![image](https://github.com/user-attachments/assets/2869417f-54e4-44d3-b48b-03dc68d705c8)
<br/><br/>

One final step, we need to edit the panel to actually use the variable so that it dynamically updates itself: <br/>
![image](https://github.com/user-attachments/assets/38c23761-0bfe-4ae5-9639-2b77518a0158)
<br/><br/>

Change the title of the panel to use the variable: `Parkrun data for $Parkrun`:<br/>
![image](https://github.com/user-attachments/assets/dcb82af6-051b-49f5-93a2-bf66b9bfb7a2)
<br/><br/>

And also update the URL you used earlier, to use the variable now: `http://localhost:8080/weather/$Parkrun`: <br/>
![image](https://github.com/user-attachments/assets/d96938ec-55f7-4cdd-90be-bf34abdb6e4f)
<br/><br/>
If that looks good, then on the top right of your page, click on `Back to dashboard`:<br/>
![image](https://github.com/user-attachments/assets/c89a27c8-566f-41e9-a630-5d0cbccab1e3)
<br/><br/>
Notice how when you change the selection of the variable, that the panel updates with new data for that location. It updates dynamically!
<br/><br/>
If you're happy, **Save your dashboard**, top right of the page.
<br/><br/>
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
