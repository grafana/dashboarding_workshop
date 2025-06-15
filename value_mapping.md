# Value Mappings & Overrides
[Value Mapping](https://grafana.com/docs/grafana/latest/panels-visualizations/configure-value-mappings/) is a technique you can use to change how data appears in a visualization. 
<br/><br/>
For example, the mapping applied in the following image causes the visualization to display the text Cold, Good, and Hot in blue, green, and red for ranges of temperatures rather than actual temperature values. Using value mappings this way can make data faster and easier to understand and interpret.<br/>
![image](https://github.com/user-attachments/assets/c279b5d9-803b-465d-a9cb-9d6f2193e518)
<br/><br/>
### Overrides
[Overrides](https://grafana.com/docs/grafana/latest/panels-visualizations/configure-overrides/) allow you to customize visualization settings for specific fields or series. When you add an override rule, it targets a particular set of fields and lets you define multiple options for how that field is displayed.
<br/><br/>
### Lab steps
Edit your panel again, and switch to the Overrides tab:<br/>
![image](https://github.com/user-attachments/assets/d6d06870-aad2-406a-8b90-2be3451f4adc)

<br/><br/>
We will be adding many overrides, so start with the first one:<br/>
![image](https://github.com/user-attachments/assets/28443841-b20c-436d-9596-994178a4b3eb)

<br/><br/>
In almost most cases, we will want to override a specific field, but there are other ways to target what you want to change.<br/>Select `Fields with name`:<br>/
![image](https://github.com/user-attachments/assets/bf77fd29-f46d-41ad-a905-21e58ddaebe0)

<br/><br/>
Select the `Temperature` field, and then on `Add override property`:<br/>
![image](https://github.com/user-attachments/assets/fe47103f-2a56-48ef-891d-364ffb0d0535)

<br/><br/>
You want to pick the `Value mappings` property to override:<br/>
![image](https://github.com/user-attachments/assets/f4366e3b-4d46-4a4e-a8dd-15b66cb8cfd9)

<br/><br/>
Add the following "Range" mapping (and remember to remove the default mapping that exists initially):<br/>
![image](https://github.com/user-attachments/assets/1844e291-04eb-4db4-a9ce-b398bfcd66ac)

<br/><br/>
Slowly your panel will start changing. Here we can see that instead of the temperature values, we are seeing the words Cold, Mild or Hot displayed instead:<br/>
![image](https://github.com/user-attachments/assets/d2e81532-a994-4ec4-af38-a4f7d10c15ea)


<br/><br/>
