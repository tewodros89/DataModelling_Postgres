# Sparkify Project Description

A company Sparkify wants to analyze the data they've been collecting by using their new music streaming app which is songs and user activity. By using the collected data, the analytics team interested in what songs users are listening to and they want to do some Song Play Analysis. 
Thus, at this stage analytics team don't have an easy way to query their raw data to do some analytical work. 
Therefore, to solve their problems we create and define fact and dimension tables using star schema and create an ETL pipeline using Python and Postgres.

This project uses 3 files which is run sequentially which are sql_queries.py, create_tables.py and etl.py. 1st we update sql_queries.py file with all essential code to be used in other two files. 2nd we create_tables.py must be run before ETL script to make sure required database and tables are created before inserting data. The sql_queries.py used to Create table, Drop table, Insert statement, and Select query for Songs Play table. And “create_tables.py” contains Python functions that connects with Postgres database and used to drop database, creates database, drops tables, and creates tables. Finally, “etl.py” contains Python functions that processes data from JSON formatted files stored on local drives and insert them into respective tables. 


**Songs Dataset** Contains JSON formatted files with metadata about a song and its artist. 

For example, here are file paths to two files in this dataset.

song_data/A/B/C/TRABCEI128F424C983.json 
song_data/A/A/B/TRAABJL12903CDCF1A.json

**Log Dataset** contains user activity for a given day
For example, here are file paths to two files in this dataset.

log_data/2018/11/2018-11-12-events.json
log_data/2018/11/2018-11-13-events.json

The star schema includes the following tables.

###### Fact Table

**songplays**
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

###### Dimension Tables

**users** - users in the app
user_id, first_name, last_name, gender, level

**songs** - songs in music database
song_id, title, artist_id, year, duration

**artists** - artists in music database
artist_id, name, location, latitude, longitude

**time** - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday


