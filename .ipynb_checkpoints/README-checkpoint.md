# Cloud Data Warehouse (Sparkify data)
## About Sparkify
Sparkify is a music startup, they store songs data and their logs in separate JSON files, analyzing those data becomes diffcult, in order to handle those large data, they need to process and extract data using ETL pipelines, then store it in a data warehouse using AWS cloud.

## Database Design
### Staging 
* Staging events - log data
* Staging songs - songs data
### Fact Table
#### songplays - records in event data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
### Dimension Tables
#### users - users in the app
user_id, first_name, last_name, gender, level
#### songs - songs in music database
song_id, title, artist_id, year, duration
#### artists - artists in music database
artist_id, name, location, lattitude, longitude
#### time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

#### AWS Redshift Cluster (tables)
![results](https://imgur.com/WkgC0cv.png) 

## User Manual
#### In order to run the code .. 
1) To check cluster is up run IaC file.
2) Run execute.ipynb to run create_tables.py and etl.py
3) Open Amazon Redshift Cluster to check your tables and data is there.
4) Delete the cluster from IaC file.