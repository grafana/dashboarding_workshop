# Annotations

[Annotations](https://grafana.com/docs/grafana/latest/dashboards/build-dashboards/annotate-visualizations/) provide a way to mark points on a visualization with rich events. They are visualized as vertical lines and icons on all graph panels. When you hover over an annotation, you can get event description and event tags. The text field can include links to other systems with more detail.<br/>
![image](https://github.com/user-attachments/assets/a5e0a757-c4e8-4402-97c5-56067cf7ec1e)

<br/><br/>
### Annotation 1 & 2
We will now set the first of three types of annotations. <br/>
For the first annotation, hold Ctrl/Cmd and click+drag over an area of the Timeseries panel:<br/>
![image](https://github.com/user-attachments/assets/12c33aa4-2884-412b-a620-c2625ee1d5ca)
<br/>
So that it looks something like this:<br/>
![image](https://github.com/user-attachments/assets/01ef4565-1798-4738-94b0-0dca88b52c82)
<br/><br/>
Then, pick a single time point, and click on it to set another annotation, eg:<br/>
![image](https://github.com/user-attachments/assets/997c1625-dc6d-4159-8577-e5657bc629b7)
<br/>
Give it a description:<br/>
![image](https://github.com/user-attachments/assets/ccc439af-6d88-43f4-ad0e-0a9e063c463a)
<br/><br/>
Notice how how you can hover your mouse over an annotation to get more detail about that region:<br/>
![image](https://github.com/user-attachments/assets/3ccfdfcb-0d52-4ed9-ade2-ba0c85251b5f)
<br/><br/>

### Annotation 3
So far we have added annotations manually to our panel, but we can also add them dynamically from another source, like a database. So this means that whenever you update your external annotation source, then it will automatically reflect on your panel.<br/>
<br/>
Top right, click on Settings:<br/>
![image](https://github.com/user-attachments/assets/6d13fcb3-0a2d-4952-8d32-a06becc6ca7e)
Select `Annotations`:<br/>
![image](https://github.com/user-attachments/assets/4cdc4013-4268-4a03-9173-402fd725b5ef)
<br/><br/>
Click on `Add annotation query`:<br/>
![image](https://github.com/user-attachments/assets/7461c5be-04a1-4b4d-82e7-24bff7294de9)
<br/><br/>
On the next page, provide a Name, ensure you have selected the `mysql-parkrun` datasource and change the colour to green or something else:<br/>
![image](https://github.com/user-attachments/assets/549b5da3-ce0e-4b0b-95cc-fa5c8ab0b7b5)
<br/><br/>
In the query section, make sure you have selected the `grafana_annotations` table:<br/>
![image](https://github.com/user-attachments/assets/30b7373c-ef13-4ddb-905c-691bdc193d51)
<br/><br/>
And also pick 4 columns that are needed to display the annotations:<br/>
- time_epoch_ms -> time
- time_end_epoch_ms -> timeEnd
- text
- tags
<br/>

![image](https://github.com/user-attachments/assets/e1a429ef-e3a8-4980-bb73-265a954a9f83)
<br/><br/>

And if you did it correctly, it should automatically show in green successful:<br/>
![image](https://github.com/user-attachments/assets/53d0ee22-72ef-454d-8d1b-56905bd6b602)

<br/><br/>
Go back to your dashboard, and remember to save!<br/>
![image](https://github.com/user-attachments/assets/9334a932-bf0b-4d4d-a663-c77478614571)

<br/><br/>
And now you will automatically pull in three annotations from the database into your panel:<br/>
![image](https://github.com/user-attachments/assets/dbd601df-aded-4df0-bc33-dbcb463bb37f)
<br/><br/>
[Back to Table of Contents](https://github.com/grafana/dashboarding_workshop/blob/main/README.md)
