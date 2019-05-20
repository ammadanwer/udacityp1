## Summary
This project is the first project for Udacity Data Engineering Nanodegree Program.
The task includes facilitating the Sparkify start up in setting up a data warehouse
that would have the songs data to which the users are listeniing to. 
This would help Sparkify analyze the user activities.

The project is written in `python` and uses `pandas` to read and process the files 
while `postgres` is used to store the data for analysis.

##Source Data
The source data is in log files given the `data` directory. Theer are 2 directories inside data
 containing different types of log files:
* log_data
* song_data

Log files contains songplay events of the users in json format 
while song_data contains list of songs details.

## Database Schema
Following are the fact and dimension tables made for this project:
#### Dimension Tables:
   * users
        * columns: user_id, first_name, last_name, gender, level
   * songs
        * columns: song_id, title, artist_id, year, duration
   * artists
        * columns: artist_id, name, location, lattitude, longitude
   * time
        * columns: start_time, hour, day, week, month, year, weekday
   
#### Fact Table:
   * songplays
        * columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

## To run the project:
   * Run command to install requirements.
        > pip install -r requirements.txt
        
   * Run `python create_tables.py`. This will create the database and all the required tables.
   * Run `python etl.py`. This will start pipeline which will read the data from files and populate the tables.
