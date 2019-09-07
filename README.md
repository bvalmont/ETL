# ![Alt Text](https://www.bing.com/th?id=OIP.EKlqoGs8WygAu7Nq5-gKFgHaHa&w=208&h=206&c=7&o=5&pid=1.7)

# Load the Data
## After the data was cleaned, the next step in the ETL process is loading. For this project a relational database was chosen; specifically PostgreSQL. The reason for choosing a relational database is due to the fact that each table is related to players in the NFL. One table is named "nfl_arrests" and the other "nfl_profiles". Each table can be queried seperately; however as will be explaind later, the tables can be joined where the player's names match in both tables. Joining the tables in this way gives the most robust data than either of the tables do seperately.

## Steps in the loading process:
In this project SQL Alchemy was used to connect to PostgreSQL; so in essence SQL Alchemy is a ORM that will be connected to PostgreSQL through the use of python and Jupyter Notebooks.
1.  Connect the orm to the local database with the code below:
###### `engine = create_engine(f"postgresql://postgres:{secret.user_pass}@localhost:5432/nfl_etl")`
###### `connection = engine.connect()`
2.  Add the 2 panda dataframes to the local database with the code below:
###### `nfl_arrests_df.to_sql(name='nfl_arrests', con=engine, if_exists='append', index=True)`
###### `nfl_profiles_df.to_sql(name='nfl_profiles', con=engine, if_exists='append', index=True)`
