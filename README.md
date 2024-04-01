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
- Converting dtype and removing nan values
```
df['host_name']= df['host_name'].astype(str) 
df['host_name']= df['host_name'].str.replace("nan", " ")
```
- Removing all non-alphabetical characters
```
df['host_name'] = df['host_name'].str.replace('[^a-zA-Z]', '', regex=True)
```
- Creating space between any 2 names
```
df['host_name'] = df['host_name'].str.replace(r'([a-z])([A-Z])', r'\1 \2', regex=True)
df.head()
```
6. Sorting to Obtain data where the AirBnb is priced
```
df_priced = df[df['price'] != 0]
df_priced.head()
```
7. If we need data for where minimum nights is a year or less
```
df_year = df[df['minimum_nights'] <= 367]
df_year.head()
```
8. To get data where availability is atleast 1 day
```
df_available = df[df['availability_365'] !=0]
df_available.head()
```
9. Cleaning Last_Review column
- Converting data_type to string
```
df['last_review']= df['last_review'].astype(str)
```
- Deleting Nan values from the column
```
df['last_review']= df['last_review'].str.replace("nan", " ")
df.head()
```
10. Cleaning Reviews/month column
- Converting data_type to string
```
df['reviews_per_month']= df['reviews_per_month'].astype(str)
```
- Deleting Nan values
```
df['reviews_per_month']= df['reviews_per_month'].str.replace("nan", " ")
df.head()
```














