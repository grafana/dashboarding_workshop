# Value Mappings & Overrides
[Value Mapping](https://grafana.com/docs/grafana/latest/panels-visualizations/configure-value-mappings/) is a technique you can use to change how data appears in a visualization. 
<br/><br/>
For example, the mapping applied in the following image causes the visualization to display the text Cold, Good, and Hot in blue, green, and red for ranges of temperatures rather than actual temperature values. Using value mappings this way can make data faster and easier to understand and interpret.<br/>
![image](https://github.com/user-attachments/assets/c279b5d9-803b-465d-a9cb-9d6f2193e518)
<br/><br/>
### Overrides
[Overrides](https://grafana.com/docs/grafana/latest/panels-visualizations/configure-overrides/) allow you to customize visualization settings for specific fields or series. When you add an override rule, it targets a particular set of fields and lets you define multiple options for how that field is displayed.
<br/><br/>
### Lab steps, field override 1
Edit your panel again, and switch to the Overrides tab:<br/>
![image](https://github.com/user-attachments/assets/d6d06870-aad2-406a-8b90-2be3451f4adc)
<br/><br/>
We will be adding many overrides, so start with the first one:<br/>
![image](https://github.com/user-attachments/assets/28443841-b20c-436d-9596-994178a4b3eb)
<br/><br/>
In almost most cases, we will want to override a specific field, but there are other ways to target what you want to change.<br/>Select `Fields with name`:<br/>
![image](https://github.com/user-attachments/assets/bf77fd29-f46d-41ad-a905-21e58ddaebe0)
<br/><br/>
Select the `Temperature` field, and then on `Add override property`:<br/>
![image](https://github.com/user-attachments/assets/fe47103f-2a56-48ef-891d-364ffb0d0535)
<br/><br/>
You want to pick the `Value mappings` property to override:<br/>
![image](https://github.com/user-attachments/assets/f4366e3b-4d46-4a4e-a8dd-15b66cb8cfd9)
<br/><br/>
Expand the Value mappings by pressing the arrow to the right of "Value mappings X ↓" 
<br/><br/>
Add the following "Range" mapping (and remember to remove the default mapping that exists initially):<br/>
![image](https://github.com/user-attachments/assets/1844e291-04eb-4db4-a9ce-b398bfcd66ac)
<br/><br/>
Slowly your panel will start changing. Here we can see that instead of the temperature values, we are seeing the words Cold, Mild or Hot displayed instead:<br/>
![image](https://github.com/user-attachments/assets/d2e81532-a994-4ec4-af38-a4f7d10c15ea)
<br/><br/>
Add another property, `Add override property`. Don't add a field override, just the property!<br/>
![image](https://github.com/user-attachments/assets/c0d775a3-1caf-4d52-ae32-68b3b80d2a62)
<br/><br/>
Search for `Cell type`:<br/>
![image](https://github.com/user-attachments/assets/4c005039-c66a-4120-abeb-7f5042eeb6dd)
<br/><br/>
And then search for `Gauge`:<br/>
![image](https://github.com/user-attachments/assets/5a660afa-40de-4e52-a4d4-aabb8d3007cb)
<br/><br/>
Select `Retro LCD` and `Value Color`:<br/>
![image](https://github.com/user-attachments/assets/54c79e49-7d04-4161-8351-05df5a66ae31)
<br/><br/>
Add one more override property, and search for `Column alignment` and make it `Left`:<br/>
![image](https://github.com/user-attachments/assets/6f2276d2-b341-4d2e-ab37-4a8b8570264f)
<br/>
![image](https://github.com/user-attachments/assets/848d0b1a-55b0-4717-806f-b1294eaab6b8)
<br/><br/>
Once again, look at the panel updating in real time with the new visualisation options:<br/>
![image](https://github.com/user-attachments/assets/cad70f3f-8c08-4c61-9f43-73809d464694)
<br/><br/>

### Field override 2
Now, add a new `Field override` (not override property):<br/>
![image](https://github.com/user-attachments/assets/7c8e8605-c78a-43a5-b819-a40108767bf4)
<br/><br/>
Select "Fields with name"
<br/><br/>
Pick `Wind Speed`:<br/>
![image](https://github.com/user-attachments/assets/7b23a26e-29ef-40ff-9375-49c9b4863e53)
<br/><br/>
Search for the property `Unit` and search for `km/h`:<br/>
![image](https://github.com/user-attachments/assets/c408766f-aef1-41ee-b3d8-eaaeb7cbdb81)
<br></br>

### Field override 3
Again, add another field override:<br/>
![image](https://github.com/user-attachments/assets/7c8e8605-c78a-43a5-b819-a40108767bf4)
<br/>
This time, search for Rain and set the following overrides, again remember to remove the Value condition and add ranges :<br/>
![image](https://github.com/user-attachments/assets/a50011c0-8e22-4fb7-bd0c-9c49322e1473)
<br/>
Specifically, you want to set:
- Value mappings
- Cell type -> Colored Background
- Background display mode -> Gradient
<br/>
As a hint, use the following value mappings:<br/>

![image](https://github.com/user-attachments/assets/3b476a5c-fb42-4897-ac84-26ccdd10e593)
<br/><br/>
And finally, your panel should look like this:<br/>
![image](https://github.com/user-attachments/assets/8492a261-7bee-453b-8371-32dee787fd7f)
<br/><br/>
Remember to save as well!<br/>
![image](https://github.com/user-attachments/assets/50239759-1136-455f-aca0-3110ee73c452)
<br/><br/>
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
