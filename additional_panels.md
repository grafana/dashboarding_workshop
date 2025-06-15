# Let's add a few more panels

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
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
