# Airbnb Optimization

The following instructions should be used to guide you in building a functional ETL pipeline using several languages and technologies

### Getting Started:
1. For the entirity of the project, we'll be using Python on Jupyter Notebook, which can be used by installing the Anaconda Navigator; in addition to being easy to use and offering error feedback, it's also compatible with R if chosen to work with. An alternative IDE is JetBrains' Pycharm, another excellent platform that supports frontend technologies like HTML, CSS, and Javascript. Both environments can be found here:
- Anaconda Navigator: https://docs.anaconda.com/anaconda/install/
- JetBrains' PyCharm: https://www.jetbrains.com/pycharm/download/#section=windows

2. In order to build our ETL pipeline, we also need a powerful database to upload and warehouse our data, also create the tables with our specifications. We're going to use Google BiqQuery to quickly run our SQL queries and effectively store our data. Being the world's most popular open-source database, MySQL is also a viable option which gives it's users access to several drivers and solid security.
- Google BigQuery: https://cloud.google.com/bigquery
  - Installation Tutorial: https://www.youtube.com/watch?v=sV2XX7LbYEw

- MySQL: https://dev.mysql.com/downloads/installer/ 
  - Installation Tutorial: https://www.youtube.com/watch?v=OM4aZJW_Ojs

Step 1: Using a Google account, create a new project on https://console.cloud.google.com/home/ under BigQuery. Assign a unique name to your project so you don't forget where you're storing your data.

![image](https://user-images.githubusercontent.com/38171817/117841446-12a49780-b24b-11eb-9009-6d235b8d927d.png)

Step 2: Create a new dataset with a unique name, possibly the name of the project you're working on or simply "Set1." Keep everything as it's default, however you can choose a table expiration date as an option.

![image](https://user-images.githubusercontent.com/38171817/117846671-a5dfcc00-b24f-11eb-9f5d-2869a1e37e76.png)

![image](https://user-images.githubusercontent.com/38171817/117850485-569b9a80-b253-11eb-8b34-f149d00f34ea.png)

Step 3: Next, we're going to upload our csv file onto our table by selecting "Google Cloud Storage" as the source and pasting our CSV URL into the GCS bucket. Finally, before creating the table, check the box for "Auto Detect" to recognize the schema. Repeat this step for all tables included.

![image](https://user-images.githubusercontent.com/38171817/117855040-138ff600-b258-11eb-8e0b-546383927874.png)

![image](https://user-images.githubusercontent.com/38171817/117855333-5fdb3600-b258-11eb-8061-272f919b22ee.png)


## Procedure

### Extract
1. Airbnb Open Data in NYC https://www.kaggle.com/peterzhou/airbnb-open-data-in-nyc?select=reviews_detail.csv
2. NYC Zipcode Population https://data.beta.nyc/en/dataset/pediacities-nyc-neighborhoods/resource/7caac650-d082-4aea-9f9b-3681d568e8a5 
3. Google Drive with files https://drive.google.com/drive/folders/1dZmn02aiDG0zZgxVGTezfJk3AlBZqfRt?usp=sharing
### Load

### Transform

## Code Demo
Our program can be found here: 

## Contact Information
Feel free to contact our team regarding any component of this repo:
- saqif.ahmed@baruchmail.cuny.edu
- mehdi.emon@baruchmail.cuny.edu
- soichiro.miyazaki@baruchmail.cuny.edu
- steven.smith@baruchmail.cuny.edu
