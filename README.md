# Surfs_up
For learning Advanced Data Storage and Retrieval from Module 9

## Project Overview
W. Avy likes the analysis, but he wants more information about temperature trends before opening the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

## Resources
- sqlite, Anaconda, Jupyter notebook, Visual Code
- data for tables from hawaii.sqlite

## Challenge Overview
Prerequisite:
1.  Download the SurfsUp_Challenge_starter_code.ipynb file 


## Deliverable 1:  Determine the Summary Statistics for June

Follow the instructions below to complete Deliverable 1.

1.  Write a query that filters the date column from the Measurement table to retrieve all the temperatures for the month of June.
2.  Convert the June temperatures to a list.
3.  Create a DataFrame from the list of temperatures for the month of June.
4.  Generate the summary statistics for the June temperatures DataFrame.


## Deliverable 2: Determine the Summary Statistics for December

Follow the instructions below to complete Deliverable 2.

1.  Write a query that filters the date column from the Measurement table to retrieve all the temperatures for the month of December.
2.  Convert the December temperatures to a list.
3.  Create a DataFrame from the list of temperatures for the month of December.
4.  Generate the summary statistics for the December temperatures DataFrame.


## Surfs_up-Analysis Results
1.  

- Image of summary statistics for the June temperatures
    ![image_name](https://github.com/raneymjohnGit/surfs_up/blob/main/Resources/June_Temps.png)

- Image of summary statistics for the December temperatures
    ![image_name](https://github.com/raneymjohnGit/surfs_up/blob/main/Resources/December_Temps.png)

- Image of summary statistics for the June precipitations
    ![image_name](https://github.com/raneymjohnGit/surfs_up/blob/main/Resources/June_Prcps.png)
 
- Image of summary statistics for the December precipitations
    ![image_name](https://github.com/raneymjohnGit/surfs_up/blob/main/Resources/December_Prcps.png)

## Surfs_up-Analysis Summary

1.  Average June temperature is 75 and Average December temperature is 71, which is not bad considering december month is a winter month 
2.  In June also the minimum temperature is 64 only considering June is a Summer month. We might need to consider the precipitation also before staring an ice cream shop.
3.  December maximumn temperature is 83 which is a good sign to start an ice cream shop.

Additional Queries:

1.  June Precipitation statistics
        
-- Following code will give information about precipitation for the month of June

month_str = "06"  

results = session.query(Measurement.prcp).filter(func.strftime("%m", Measurement.date) == month_str).all()  

june_prcp = list(np.ravel(results))  

June_Prcp_df = pd.DataFrame(june_prcp,columns=["June Prcps"])  

June_Prcp_df.describe()  



2.  December Precipitation statistics

-- Following code will give information about precipitation for the month of December

month_str = "12"  

results = session.query(Measurement.prcp).filter(func.strftime("%m", Measurement.date) == month_str).all()  

december_prcp = list(np.ravel(results))  

December_Prcp_df = pd.DataFrame(december_prcp,columns=["December Prcps"])  

December_Prcp_df.describe()  

