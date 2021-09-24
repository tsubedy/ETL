# ETL Project:

Extraction: (Project part I)
- data were obtained from various websites using web scraping technique as well as downloading csv files from the source websites
- The following dataset were used in this project
    
    Web Scraping (as in jupyter notebook part I): 
    - california couty population 2021 using web scraping technique from the site: https://worldpopulationreview.com/us-counties/states/ca
    - california county fips from - https://en.wikipedia.org/wiki/List_of_counties_in_California#List
    
    Downloading CSV files:
    - statewide_covid_19_vaccination_by_county.csv from https://data.chhs.ca.gov/dataset/vaccine-progress-dashboard
    - statewide_covid_19_cases_by_county.csv from https://data.chhs.ca.gov/dataset/covid-19-time-series-metrics-by-county-and-state
   
Transfermation:

The datafiles obtained from the above mentioned sources are then converted into Pandas dataframe to observe if there are inconsistencies or data error, unnecessary rows or columns of interests and were removed. 

Only the columns and rows of interests were chosen to create new datafiles. County fips and county names are considered as primary keys when importing to SQL using Postgres PGAdmin. The mapping of relational database is done using quick DBD (screenshot for ER diagram is provided as a separate png file)

SQL Database is created and the tables are imported to Postgres and table querries are performed to test if all datafiles are ready for querries. The SQL table schema and querry sames are saved in a separate sql file.

Loading: (project part II) 

Once the database is created in sql, the datafiles are loaded into jupyter notebook using sqlalchemy connenction engine (as shown in part II).
Some of the 'views' that are created in sql are used to retrieve the data files in jupyter notebook. 

The database is now ready to perform further analysis.

Limitations:

- Data files are based on only a particular sources and not crossed checked with any other sources
- The database can be used to analyse the covid cases, deaths, and vaccination trends by counties, by months (2020, 2021). Simialry, some mathematical operations as well as statistical analysis can be performed on the limited database (it doesn't provide a wide range of scope)
- Analysis is not performed as it is beyond the scope of this project. 






     
     
     
     
     
