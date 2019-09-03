# Population Analysis with MS Power BI

Power BI Desktop consists of the three parts: data preparation (query editor), data modeling (relationship view and data view) and data visualisation (report view). The project will cover all of the aspects provided by MS Power BI.

## Data Preparation
### Cleaning Data
The query editor is to manipulate and clean source data without changing them. The frist source files are the following:
* population-country-1950-1999.csv
* population-country-2000-2049.csv
* population-country-2050-2100.csv

After loading those files, I cleaned the data by deleting NA or blank rows, setting headers and replacing incorrectly-formated data such as '9-May' values to '5-10' in the 'Age-group' column. I combined those three data tables after checking the headers and data types are matching each other. I unpivoted male and female poplulation and changed the header names and split the popluation gender column by the delimiter of '-'.

### Star Schema

Having a better oganisation of data table is crucial to analyse data efficiently. The project will turn the combined data structure into a star schema (from a fact table to dim tables). It is imortant to understand the differnce between duplicates and reference, as it affects the performance of computation. From the combined table I created reference models, the 'Regions-Fullnames'and 'DIM-AgeGroup' table.

![image1](https://github.com/myfriendtae/global_population_analysis/blob/master/screenshot1.png?raw=true)

### Storing Data
By disabling load, it creates larger free memory space, so I have disabled all tables apart from the Population-Combined, DIM and FACT tables.

## Data modeling
Connecting two DIM tables and one FACT table as shown in the picture, there are three aspects to consider: cardinarlity, cross filter direction and active properties.

![image2](https://github.com/myfriendtae/global_population_analysis/blob/master/screenshot2.png?raw=true)

## Visualisation
Here below are the examples of visulalisation created via MS Power BI.

![image3](https://github.com/myfriendtae/global_population_analysis/blob/master/screenshot3.png?raw=true)

![image4](https://github.com/myfriendtae/global_population_analysis/blob/master/screenshot4.png?raw=true)

![image5](https://github.com/myfriendtae/global_population_analysis/blob/master/screenshot5.png?raw=true)

![image6](https://github.com/myfriendtae/global_population_analysis/blob/master/screenshot6.png?raw=true)


