# Population Analysis with MS Power BI

Power BI Desktop consists of the three parts: data preparation (query editor), data modeling (relationship view and data view) and data visualisation (report view). The project will cover all of the aspects provided by MS Power BI.

## Data Preparation
### Cleaning Data
The query editor is to manipulate and clean source data without changing them. The frist source files are the following:
* population-country-1950-1999.csv
* population-country-2000-2049.csv
* population-country-2050-2100.csv

After loading those files, I deleted NA or blank rows and set headers. I combined those three data tables after checking the headers and data types are matching each other. I changed column names and removed unncessaory columns. As finding incorrect data in the combined table, I used the 'replace values' function to replace incorrectly-formated data such as '9-May' values to '5-10' in the 'Age-group' column. I checked and changed the data type of each column. It's always useful to apply and ensure if there are any erros in the table. I unpivoted male and female poplulation and changed the header names and split the popluation gender column by the delimiter of '-'. I also created a new group is a great way to oragnise queries. I multiplied the popuplation column to nomalise the scale.

### Star Schema

Having a better oganisation of data table is crucial to analyse data efficiently. The project will turn the combined data structure into a star schema (from a fact table to dim tables). It is imortant to understand the differnce between duplicates and reference, as it affects the performance of computation.

I created a reference model from the combined table, and named 'DIM-region' and removed the duplidated rows. Creating the full regional table, I loaded the 'codes-country-region.txt' file with the delimiter of tab. Similar to the cleaning process of the combined data, I set the column names and deleted and named columns. I also created the 'Regions-Fullnames' table by using the function 'enter data' and copyed the regional codes in the 'codes-country-region' table and manually entered the region names after removing all the duplicated rows. The two tables, 'codes-country-region' and 'Regions-Fullnames', can be now merged into the 'merge queries' function. I used the merged table to merge with 'DIM-region' table. After the merge, I investigated the duplicated rows by using the 'keep rows' function by checking the 'Country-ID' column in the 'codes-country-region' table, and adjusted null data manually while ensuring the data type of each column. I created another reference model from the combined table,  and named 'DIM-AgeGroup', using the conditonal column function to catagorise the age group.

### Storing Data
By disabling load, it creates larger free memory space, so I have disabled all tables apart from the Population-Combined, DIM and FACT tables.

## Data modeling
I could connect three data tables: two DIM tables and one FACT table as shown in the picture. There are three aspects to consider when establishing the relationship between tables. They are cardinarlity, cross filter direction and active properties.

I can also use the embedded languages like M-Lanaguage and DAX-Language to add new columns. The project has a limited use of those languages, but I created the 'Calendar' table, and added columes using the 'calendar' function written in DAX-Language.
