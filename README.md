# Hotel_Revenue_insights


```
Data Source ---> Power Query --> DAX -> Dashboarding
```
-----------------------------> `Data Loading and Power Query Documentation` -------------------------------------->


1. Create a folder in Desktop and store all the csv files related to hospitality challenge.

2. Open a Power BI file, and In "Get Data", select the option as folder and browse through the folder containing csv files.

3. Then go to Tranform data to expand each and every dataset.

4. Now, duplicate the data source 4 times and in each one, expand one dataset by clicking on "Binary" option. also, rename 
   the tables accordingly.


*****************  `Power Query steps for tables:`  *******************
1. dim_date:
	- remove the column 'day_type'
	- we are deleting this because, we got a feedback from the mock dashboard review that Friday and Saturday are           
	  considered as weekends in the industry and not sunday. But In our datasets, saturday and sunday are considered           
	  as weekends. So we delete this column and re-create day_type using calculated columns.


day_type= var wkd = WEEKDAY(dim_date[date])
 return if (wkd>5,"weekend","Weekday")


2. dim_rooms
	- The column names are not captured here. We need to select "Use First Row as Headers" option .
