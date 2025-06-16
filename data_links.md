# Data Links
[Data links](https://grafana.com/docs/grafana/latest/panels-visualizations/configure-data-links/) allow you to link to other panels, dashboards, and external resources and actions let you trigger basic, unauthenticated, API calls. In both cases, you can carry out these tasks while maintaining the context of the source panel.
<br/><br/>
However there is also [Dashboard Links](https://grafana.com/docs/grafana/latest/dashboards/build-dashboards/manage-dashboard-links/) and Panel Links. 

### Configuring Dashboard Link
In your dashboard, click on Settings:<br/>
![image](https://github.com/user-attachments/assets/465facdd-6f1b-47a5-901e-cf02b37dc306)
<br/><br/>
Then click on `Links`:<br/>
![image](https://github.com/user-attachments/assets/cb38bb0c-88a5-4665-a3fa-32b922257732)
<br/><br/>
- Give your link a name, eg: `More details`<br/>
- Change the type to "Link"<br/>
- And set the URL to: `https://grafanaday.taila86a5.ts.net/d/100fddb0-c315-4434-b176-147435dd6134/parkun-analytics?orgId=1&from=now-6h&to=now&timezone=browser`<br/>
- Also tick the options for `Include current template variable values` and `Open in new tab`<br/>

![image](https://github.com/user-attachments/assets/b446ab46-db86-404a-b30c-1941f519fe0c)
<br/><br/>
Now when you go back to your dashboard:<br/>
![image](https://github.com/user-attachments/assets/d7b1f9b8-f67f-4fbe-a241-d4016b71c40b)
<br/><br/>
You will see a new sort of button/menu option appear:<br/>
![image](https://github.com/user-attachments/assets/6825af40-faa1-4e4f-9c54-2181e2a841f1)

<br/><br/>
Click it and see what happens!
<br/><br/>

### Configuring a Data Link
Above you configured a link for the whole dashboard that will take you to another location. But it is also possible to make individual things on a panel into the own clickable links. For example, each of these links can go to their own URL:<br/>
![image](https://github.com/user-attachments/assets/55656e89-903c-4050-98b2-8d02464b04ac)
<br/>These are called `Data Links`
<br/><br/>
Edit the panel:<br/>
![image](https://github.com/user-attachments/assets/9263eef0-7dc5-437f-ab7e-39ff45effb69)
<br/><br/>
Click to add an override:<br/>
![image](https://github.com/user-attachments/assets/b262531b-34f1-46e2-b0fb-be0db1fce8d4)
<br/><br/>
Scroll to the bottom and add a new override:<br/>
![image](https://github.com/user-attachments/assets/c287e67d-8f19-47d2-a00d-41b45042c47a)
<br/><br/>
And then `Fields with name`:<br/>
![image](https://github.com/user-attachments/assets/47ecf1f9-aa46-4faf-82ff-f896856329d7)
<br/><br/>
Select the `Date` field:<br/>
![image](https://github.com/user-attachments/assets/17f23752-9656-463f-8591-9daf634ab6b7)
<br/><br/>
Search for `link`, then select `Data links`:<br/>
![image](https://github.com/user-attachments/assets/90eee519-ae2a-4038-b085-94c17ef487e4)
<br/><br/>
Finally, `Add link`:<br/>
![image](https://github.com/user-attachments/assets/40348ced-adfe-4aaf-8cb7-cba3948b8cc6)
<br/><br/>
Finally, a popup will appear. 
- Provide a title
- Use the URL: `https://grafanaday.taila86a5.ts.net/d/100fddb0-c315-4434-b176-147435dd6134/parkun-analytics?orgId=1&from=now-6M&to=now&timezone=browser&${Parkrun:queryparam}&var-ParkrunDate=${__value.text}`
- Enable the toggle to `Open in a new tab`</br>

![image](https://github.com/user-attachments/assets/c6020555-d1d6-45a7-9533-fb9b4e081444)
<br/>
I will explain during the workshop how this URL was constructed. 
<br/><br/>
Hit `Save` and then back to dashboard:<br/>
![image](https://github.com/user-attachments/assets/5872bc65-5598-4e89-b3a7-a891cc72e2c5)
<br/><br/>

Pick different park runs and different dates. It should open on the `Parkrun Analytics` Dashboard in a new tab, with your selected variables passed through!<br/>
![image](https://github.com/user-attachments/assets/b79f6205-3e38-48a9-879e-871ed6d77d75)
<br/><br/>

## Congratulations, you've made it to the end of the workshop!


