# Data CLeaning Project
## Project Overview 
This data Analysis project involves cleaning AirBnb Data set to prepare it for further Analysis. 
I will also provide insights on customer versus Product Analysis.

## Data Source
The data set was downloaded from kaggle as a csv file.
## Tools 
- Pandas (Data importation and Cleaning)
## Steps Taken
1. Importing data file
```
   df = pd.read_csv('AB_NYC.csv')
```
2. Removing any duplicates
```
df = df.drop_duplicates()
```
3. Deleting columns that would be irrelevant for Analysis
```
df=df.drop(columns=['name','neighbourhood','calculated_host_listings_count'])
```
4. Checking for Null values and Data type in all columns
```
df.info()
```
5. Cleaning Host Name Column
-Converting dtype and removing nan values
```

















