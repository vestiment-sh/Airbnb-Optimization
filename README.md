# Airbnb Optimization

The following instructions are a guide to build a functional ETL pipeline using several languages and technologies to code valuable programs, queries, and store data in a secure environment. You're going to extract data from data sources as CSV files, transform them to your specifications, and load them onto a safe database. The goal is to determine the specific factors that constitute a lucrative Airbnb listing. The Kaggle dataset is the Airbnb listings data, providing us with information regarding all the listings in New York and their specific attributes. The NYC zipcode dataset offers additional information regarding the specific zip codes in NYC.

### Getting Started:
1. For the entirety of the project, we'll be using Python on Jupyter Notebook, which can be used by installing the Anaconda Navigator; in addition to being easy to use and offering error feedback, it's also compatible with R if chosen to work with. An alternative IDE is JetBrains' Pycharm, another excellent platform that supports frontend technologies like HTML, CSS, and Javascript. Both environments can be found here:
- Anaconda Navigator: https://docs.anaconda.com/anaconda/install/
- JetBrains' PyCharm: https://www.jetbrains.com/pycharm/download/#section=windows

2. In order to build our ETL pipeline, we need a powerful database server to upload data to and host our data warehouse, while also being able to create the tables with our specifications. We're going to use Google BiqQuery to quickly run our SQL queries and effectively store our data. Since Google Bigquery is on the cloud, it is easy to access on any computer without any need to install anthing onto your computer. 
 
- Google BigQuery: https://cloud.google.com/bigquery
  - Set-Up Tutorial: https://www.youtube.com/watch?v=sV2XX7LbYEw


## Procedure

### Extract
We will be downloading data from two sources. Below are the direct links to the datasets if additional information is needed:
1. Airbnb Open Data in NYC https://www.kaggle.com/peterzhou/airbnb-open-data-in-nyc?select=reviews_detail.csv
2. NYC Zip Borough Population https://data.beta.nyc/en/dataset/pediacities-nyc-neighborhoods/resource/7caac650-d082-4aea-9f9b-3681d568e8a5 

### Transform
1. Using Jupyter Notebook, create a Python program to clean the data using your 2 CSV files
Configure your script to:
- Drop listing information that has Null data
- Remove unnecessary characters - i.g. "$", ","
- Convert correct datatypes
- Adjust Zipcode so that they are all 5 integers
- Create necessary columns

2. Example Code: https://github.com/vestiment-sh/Airbnb-Optimization/blob/main/ETL.ipynb

### Load
Before preceding, please ensure that you are logged into your google account that you would like your data to be linked to.

Step 1: Using a Google account, create a new project on https://console.cloud.google.com/bigquery by clicking on the dropdown menu on the top of the page which is on the right side of where it says "Google Cloud Platform". A window will pop up which has the "New Project" button in the top right, click that. Assign a unique name to your project so you don't forget where you're storing your data.

![image](https://user-images.githubusercontent.com/38171817/117841446-12a49780-b24b-11eb-9009-6d235b8d927d.png)

Step 2: Once the project is created, go to the same drop down menu on the top of the page from before and open your project. This will populate it into the schema next to the console. Create a new dataset with a unique name by clicking the option shown in the picture. You can name the dataset according to your needs or simply as "Set1." Keep all other settings in this window as it's default, however you can choose a data location and table expiration date as an option if needed. By default, the data is going to be stored in the US multi-region.

![image](https://user-images.githubusercontent.com/38171817/117846671-a5dfcc00-b24f-11eb-9f5d-2869a1e37e76.png)

![image](https://user-images.githubusercontent.com/38171817/117850485-569b9a80-b253-11eb-8b34-f149d00f34ea.png)

Step 3: Next, we're going to upload our csv file. Make sure to click on the name of the dataset you just created to open it and click create a new table as shown in the picture. 
- Under Source, make sure to select the "Upload" option in the "Create Table From" dropdown.
- Browse your computer for the CSV file containing the dataset and select it. Make sure to select the file format as CSV in the drop down menu. 
- Under Destination, select the "Search for a project" option and choose the name of the project that you created earlier. For dataset name, type in the name you gave the dataset if it is not there already. Finally under "Table Name" give your table a name.
- Under Schema, make sure to select the "Schema and input parameters" under Auto detect. 
- Finally under advanced options, under "Header rows to skip" type in "1" so that the table recognizes the first row as a header row.
- Keep all other options as their default and click the "Create Table" button in the bottom right. 
- Repeat this procedure for each dataset you intend to upload. 

![image](https://user-images.githubusercontent.com/38171817/117855040-138ff600-b258-11eb-8e0b-546383927874.png)

![image](https://user-images.githubusercontent.com/38171817/117855333-5fdb3600-b258-11eb-8061-272f919b22ee.png)

## [Organizing the Data into Tables According to our Dimensional Model](https://docs.google.com/document/d/1NqRo34g1V0mCR7Ryq8_PGqHvDbwxl-gnJlO1VjQp69w/edit?usp=sharing)
Implement your dimensional model diagram by running SQL queries on the Google BigQuery console. 

## [Analysis for NYC Listings](https://github.com/vestiment-sh/Airbnb-Optimization/blob/main/Analysis.ipynb)
We analyzed the listing data for trends, looking for insight as to which predictors have the most significance in determining price of an Airbnb listng.

## [Predict Price](https://github.com/vestiment-sh/Airbnb-Optimization/blob/main/Price_Prediction.ipynb)
We created a prediction model with our findings to try and predict the daily price of a listing based on the factors. 


## Contact Information
Feel free to contact our team regarding any component of this repo:
- saqif.ahmed@baruchmail.cuny.edu
- mehdi.emon@baruchmail.cuny.edu
- soichiro.miyazaki@baruchmail.cuny.edu
- steven.smith@baruchmail.cuny.edu
