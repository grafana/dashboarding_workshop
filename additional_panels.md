# Let's add a few more panels
### Geomap / Worldmap

Click to add a new Panel, then select the `Visualization` option:<br/>
![image](https://github.com/user-attachments/assets/301fd9ec-87f8-48ce-86b7-5370a8e3ba62)
<br/><br>
Scroll down in the visualisation until you find the `Geomap` option:<br/>
![image](https://github.com/user-attachments/assets/7b814dad-0b85-4fe1-a17e-1b6a9e00244e)
<br/><br/>
Use the Infinity Datasource, and set the URL to: `http://localhost:8080/parks`
![image](https://github.com/user-attachments/assets/04aef6fb-1d2c-4bac-8d50-bad49520ee30)
<br/><br/>
http://localhost:8080/parks returns a JSON:<br/>
```
[
    {
        "name": "bushy",
        "latitude": 51.4145248,
        "longitude": -0.3297215
    },
    {
        "name": "great notley",
        "latitude": 51.8633949,
        "longitude": 0.5172669
    },
    {
        "name": "chelmsford central",
        "latitude": 51.7327454,
        "longitude": 0.4659901
    }
]
```

Remember to set a title, eg: `Parkrun Locations`</br>
![image](https://github.com/user-attachments/assets/e07fdbd7-a361-4505-8ad6-b5a74767cecb)
<br/>

Finally, under styles, change the value from `5` to `15`:<br/>
![image](https://github.com/user-attachments/assets/d3dddc70-dff9-4faa-b07c-84482f8fe26a)

<br/>

If you zoom in the worldmap a bit, you should be able to see the three locations:<br/>
![image](https://github.com/user-attachments/assets/dc810c83-9e44-4b38-a6a7-d6dcde73b943)

<br/>
<hr/>

### Timeseries Panel
Again, click to add a new Panel, then select the `Visualization` option:<br/>
![image](https://github.com/user-attachments/assets/301fd9ec-87f8-48ce-86b7-5370a8e3ba62)
<br/><br/>
You may want to toggle the "Table view", so you can see the data we're working with.
<br/><br/>
Pick Infinity as the datasource again, using the url `http://localhost:8080/weather/$Parkrun` and set `saturday_data` under the Parsing options tab:<br/>
![image](https://github.com/user-attachments/assets/d928ccfc-1af4-4eae-b6a7-d91d838aa601)
<br/><br/>
However this time, add an "Expression" (we will discuss this a little later):<br/>
![image](https://github.com/user-attachments/assets/d0ec7c52-59cf-4908-8e57-debf4c0e7ccb)
<br/><br/>
Under Operation, scroll down and select the `SQL` expression:<br/>
![image](https://github.com/user-attachments/assets/fb15c7f6-64d3-41f3-a144-cde583995569)
<br/><br/>
We need to "hide" the output of query A so that we only look at the output of query B:<br/>
![image](https://github.com/user-attachments/assets/f299cb21-c3a0-4955-a30a-38e33a7d652d)
<br/><br/>
Then change the SQL query to:<br/><br/>
```
SELECT
 UNIX_TIMESTAMP(CONCAT(event_date, ' 09:00:00')) * 1000 AS time,
 temperature_2m
FROM A
```
For example:<br/>
![image](https://github.com/user-attachments/assets/97693489-d347-4fbf-9ca7-478f769960bb)
<br/><br/>
Add a transformation `Convert field type`, to convert the time column to a `Time` type field:<br/>
![image](https://github.com/user-attachments/assets/cb819ed7-b5d1-4439-bdd6-67a4cb10e399)
This should immediately change the panel, and draw a basic timeseries graph:<br/>
![image](https://github.com/user-attachments/assets/b9494c04-d1c5-436d-a7df-bcf1847c933a)
<br/><br/>
If this didn't work, make sure you have the `Time series` visualisation set:<br/>
![image](https://github.com/user-attachments/assets/1988d678-a758-4ee4-a0bd-56fe4167764a)
<br/><br/>
But we want this to look better, so let's look at some suggestions and pick the one with the colour gradient:<br/>
![image](https://github.com/user-attachments/assets/a6f72f19-145f-42b9-ac7e-d4d433951001)
<br/>
Scroll down, and pick:<br/>
![image](https://github.com/user-attachments/assets/729c97ba-a36c-49f5-a1de-1bbc8a4200c3)
<br/><br/>
Remember to set the title: `Historic Temperature for: $Parkrun`<br/>
And add an override:<br/>
Set the following options:
- Fields with name: `temperature_2m`
- Add an override property, pick `Threshold`
- Remove the red 80 threshold, add a new 0 threshold and set the colour to blue
- Add another override property, pick `Show thresholds`
- Change the value to `As lines (dashed)`
- Add another override property, pick `Unit` and set to Celsius

![image](https://github.com/user-attachments/assets/b8e1414e-39a0-43a5-97e0-6684ce4c0c69)
<br/><br/>
By now, your panel show resemble something like this:<br/>
![image](https://github.com/user-attachments/assets/b7095915-83ef-48ed-9995-eccb3426fed3)
<br/><br/>
Remember to save your dashboard, and then go back to the main dashboard:<br/>
![image](https://github.com/user-attachments/assets/10285e6d-d79b-48a6-bbc7-302fbe488139)
<br/><br/>
Feel free to rearrange the panels fit nicely on your screen. For example (but you can choose any layout you want for yours!):<br/>
![image](https://github.com/user-attachments/assets/5d7f837f-6578-49f2-8bb3-cd97560f81a3)
<br/><br/>

[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
