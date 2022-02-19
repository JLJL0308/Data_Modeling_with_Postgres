# Project description:
The data is provided by a fictional music steaming startup "Sparkify". The company is trying to understand users' music listening activities. However, it is difficult to query the existing JSON log data. This project aims to design a star schema and build an ETL pipeline to transfer the data from the local JSON files into the tables.

# Technologies and tools:
Python, SQL, PostgreDB

# How to run the scripts:
1. Open terminal, run "python create_tables.py" to create the tables.
2. Run "python etl.py" to transfer the data through the ETL pipeline.
3. In Jupeternotebook, open "test.ipynb" to run the tests and observe the results.

# Repository:
data: the raw data provided by Sparkify.
sql_queries.py: SQL queries that creates tables and insert data.
create_tables.py: python files that runs the SQL queries.
etl.ipynb & etl.py: scripts that constructs the ETL pipeline.
test.ipynb: tests that varifies the tables and transformed data.

# Schema:
## Fact Table:
    songplays - records in log data associated with song plays i.e. records with page NextSong
                Columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
  
## Dimension Tables
    users - users in the app
            Columns: user_id, first_name, last_name, gender, level
    
    songs - songs in music database
            Columns: song_id, title, artist_id, year, duration
    
    artists - artists in music database
              Columns: artist_id, name, location, latitude, longitude
    
    time - timestamps of records in songplays broken down into specific units
           Columns: start_time, hour, day, week, month, year, weekday


# ETL pipeline:
1. Extract data from the JSON files for each column above.
2. Insert the data to coresponding tables.
2. Join different tables and filter out unwanted data.
