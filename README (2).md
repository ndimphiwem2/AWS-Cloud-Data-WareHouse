DataWarehouse Project

The purpose of this project is to extract Sparkify music streaming data residing in S3 bucket into redshift cluster for analytics purposes. The process is to build an ETL pipeline that will extract data from S3 bucket and stages it in a in an event and sng staging tables in redshift cluster. Thereafter, transform the data into a star schema with Fact and dimensional tables or dimensional model for the analytics department to perform analytics.The analytics team is interested on what songs are being listened and how long, therefore they want to understand partterns from the data.

Database scheme designs

The design of the schema are divided into two staging tables which is staging events and songs events, and a star schema divided into FACT tables and Dimension tables. this is done for easy and fast read of the data during quering. Below indicates how the schema are designed:

Staging Tables

# 1. staging_events
# 2. staging_songs

Fact Table

1. songplays - sngplays informatiom - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

Dimension Tables

1. users - users information - user_id, first_name, last_name, gender, level
2. songs - songs in music database - song_id, title, artist_id, year, duration
3. artists - artists in music database - artist_id, name, location, lattitude, longitude
4. time - timestamps of records in songplays broken down into specific day-time information - start_time, hour, day, week, month, year, weekday

Running the files

The .py files can be run by going to file, then new, then Terminal. in the terminal, one can type "python name of the file.py". for example, for etl.py file, one can type "python etl.py" then enter to run the file and verify if it is correct by going to the cluster and use query editor and run some queries to test.