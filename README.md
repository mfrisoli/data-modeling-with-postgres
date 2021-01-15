# Project: Data Modeling with Cassandra
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

Udacity Data Engineer Nanodegree Project


# Schema for Song Play Analysis
Star schema optimized for queries on song play analysis. the Schema is populated ETL pipeline using Python

## Purpose:
the pipeline and schema allows to obtain insight of songs played by Sparkify users and evaluate their interaction with the music app (app usage, free or paid account, etc.).
 
Using Pandas library, the data is extracted from JSON files and transoformed into a Pandas DataFrame, then this data gets arranged as required by the design of the schema and loaded into a PosgreSQL database so it can be queried.

## Index:
1. Schema
2. Requirements
3. Files
4. How to run


## 1. Star Schema




#### Fact Table
- songplays - records in log data associated with song plays i.e. records with page NextSong
-- songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
- users - users in the app
-- user_id, first_name, last_name, gender, level
- songs - songs in music database
-- song_id, title, artist_id, year, duration
- artists - artists in music database
-- artist_id, name, location, latitude, longitude
- time - timestamps of records in songplays broken down into specific units
-- start_time, hour, day, week, month, year, weekday

![Star Schema](https://udacity-reviews-uploads.s3.us-west-2.amazonaws.com/_attachments/339318/1586016120/Song_ERD.png "Star Schema")

<img src="https://udacity-reviews-uploads.s3.us-west-2.amazonaws.com/_attachments/339318/1586016120/Song_ERD.png" alt="Star Schema" width="500" height="600">
Image Credit: UDACITY

## 2. Requirements
- python3
- psycopg2
- pandas
- sql_queries

## 3. Files
This application is modularized into multiple python files
- create_tables.py
- etl.py (main program)
- sql_queries.py (sql queries module)
- test.ipynb
- data (JSON logfiles)
- etl.ipynb (prototype)

## 4. How to run
Is recommended that you use Jupyter Notebooks
1. Download all files into a directory
2. start a terminal window and make sure all requirements are installed
3. execute the following command to create the tables `$ python3 create_tables.py`
4. to extract, load and tranform the data into the database run the following command `$ python3 etl.py`




