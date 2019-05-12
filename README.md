## Sparkify Data Model

Data Modelling with Postgres (based on Songs Metadata and User Activity Logs)

### Getting Started
Download the project:
You can download it as zip and unpack the files or you can clone the repository from our github link

#### Prerequisites
Postgres (https://www.postgresql.org/download/)
Python 3.5 or above (https://www.python.org/downloads/)

#### Installing
You need to install this python dependencies (*optional:You can always create a virtual environment and install all the 
dependencies for python inside your virtual environment*)
In Terminal/CommandPromt:
```
pip install -r requirements.txt
```
#### Executing and Setting Up
After the pre-requisites are satisfied:
In Terminal/CommandPromt:
Create the database: studentdb, username: student, password: student
```
python create_tables.py
```
Populate the database
```
python etl.py
```
### View and Analyze
You can always analyze and query the database with this tool: pgadmin https://www.pgadmin.org/download/
or,
You can you use the test.ipynb notebook to query according to your needs

### Facts and Dimensions Tables:
This database is built upon a star schema with songplays (as facts) table at the centre and users, songs, artists, time 
etc. (as dimensions) around it connected 

### About the data
you can dump your user activity log files and song metadata files inside the data folder. The folder structure for 
metadata and user activity logs are already created. You just need to dump your files there

### Example Queries
Once you are done setting up you can get started with some exciting queries like
-- Who are the most heard artists in Sparkify
```
SELECT a.name, COUNT(*) FROM songplays s JOIN artists a ON s.artist_id=a.artist_id
GROUP BY a.name ORDER BY COUNT(*) DESC
```

-- What are most heard songs in Sparkify
```
SELECT a.title, COUNT(*) FROM songplays s JOIN songs a ON s.song_id=a.song_id
GROUP BY a.title ORDER BY COUNT(*) DESC
```
### Authors
* **Supratim Das** - *Initial work*
