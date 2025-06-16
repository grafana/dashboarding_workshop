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
