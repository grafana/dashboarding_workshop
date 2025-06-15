# Transformations
[Transformations](https://grafana.com/docs/grafana/latest/panels-visualizations/query-transform-data/transform-data/) are a powerful way to manipulate data returned by a query before the system applies a visualization. Using transformations, you can:
- Rename fields
- Join time series/SQL-like data
- Perform mathematical operations across queries
- Use the output of one transformation as the input to another transformation
<br/><br/>

Edit the panel again, and this time click on `Transformations`:<br/>
![image](https://github.com/user-attachments/assets/a186b048-1e91-4ce8-ad4d-20e52696f775)
<br/>

![image](https://github.com/user-attachments/assets/d98b5d06-8c77-4384-a5a5-b67e3ae78bb0)

<br/><br/>
We want to sort the order of Parkruns by date, so let's select the `Sort by` transformation:<br/>
![image](https://github.com/user-attachments/assets/15cf0287-2680-4370-bc14-6e493931c3dc)
<br/><br/>
Set the field to `event_date`, and then also enable the `Reverse` toggle:<br/>
![image](https://github.com/user-attachments/assets/8e3e4f44-77f3-4a1f-a403-9a30cc2e935c)
<br/>
Notice how the result set displayed on screen dynamically updated and is showing the most recent Parkrun as the first row. 
<br/><br/>
We also want to limit the results to only show the last 5 Parkruns. Add another transformation:<br/>
![image](https://github.com/user-attachments/assets/976cc3c4-01d6-43e8-a4ff-e13b392c9232)
<br/>
And add the `Limit` transformation:<br/>
![image](https://github.com/user-attachments/assets/99cbf2e0-2de6-4984-afca-6adb1fbaf937)
<br/>
Then change the limit to 5, or any other number you want:<br/>
![image](https://github.com/user-attachments/assets/e98fa8b1-26a0-43ec-af69-72faea74ee4c)

<br/><br/>
One more transformation to go, and that is to change the titles of the column names, and also to remove one of the columns that are not needed.<br/>
Add another transformation:<br/>
![image](https://github.com/user-attachments/assets/976cc3c4-01d6-43e8-a4ff-e13b392c9232)
<br/>
Search for `Organize fields by name`, and add it:<br/>
![image](https://github.com/user-attachments/assets/ef97822e-2849-4180-95ad-a4d47adbd4d5)
<br/><br/>

Let's rename all the fields to be Capitalized and more readable:<br/>
![image](https://github.com/user-attachments/assets/badc40ae-99c3-4add-9aa0-17faef1a422c)
<br/>
Again, notice how as soon as you make the change, the titles in the actual panel updates in realtime. 
<br/>
One more change, and that is to "hide" the Precipitation column, as it is unneeded. Click the little "eye" icon:<br/>
![image](https://github.com/user-attachments/assets/e7473d09-ec0b-4a5a-a73d-533d5fd5f533)
<br/><br/>

Finally, your panel should now look like:<br/>
![image](https://github.com/user-attachments/assets/fe28efc4-0561-4c16-8fd9-8d4ac9176e6d)
<br/><br/>

Go back to the main dashboard, and remember to save as well:<br/>
![image](https://github.com/user-attachments/assets/c89a27c8-566f-41e9-a630-5d0cbccab1e3)

<br/><br/>
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
