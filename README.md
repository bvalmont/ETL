# ETL
#Load the Data After the data was cleaned, the next step in the ETL process is loading. For this project a relational database was chosen; specifically PostgreSQL. The reason for choosing a relational database is due to the fact that each table is related to players in the NFL. One table is named "nfl_arrests" and the other "nfl_profiles". Each table can be queried seperately; however as will be explaind later, the tables can be joined where the player's names match in both tables. Joining the tables in this way gives the most robust data than either of the tables do seperately.

##Steps in the loading process
