
# Merging and reading XML, TXT data in MySQL:

## Creation of the Database and its tables.
The Product Owner (from now on, P.O.) sends us three files (.xml, .txt and .sql) in order to merge them into a single database.
 the objective of merging them into a single database. To do this, it will be necessary to develop a program that facilitates the readability of the data as requested by the P.O., in addition to automating the cleaning process for future inputs that reach the database, and relate them to each other.

### Characteristics of the Database
In a .sql file (sql_code.sql) we start this project with the creation of the database "project1", where the information of the three files provided by the P.O. will be aggregated in different tables. For this, it is necessary to create a table for each file in MySQL Workbench ("data_sql", "data_xml", "data_txt").

The specifications that the tables must meet are:
- "data_sql": it must store the data from the data_sql.sql file. It must be the mother table, where the primary key is of numeric type and corresponds to the column "index_sql". The rest of the columns are of type text.
- "data_xml": it must store the data from the data_xml.xml file. Its primary key is "index_xml" and its foreign key is the column "index_sql", both of numeric type. The rest of the columns are of text type.
- "data_txt": it must store the data from the data_txt.txt file. Its primary key is "index_txt" and its foreign key is the column "index_sql", both of numeric type. The rest of the columns are of text type.

The three tables will be related through the column "index_sql".
For the creation of the tables we previously observe the content of the columns to adjust the characteristics of the column to the type of data it will contain.


## Reading and explanation of the structure of the .sql file:
The Product Owner (from now on, P.O.) sends us three files (.xml, .txt and .sql) in order to merge them into a single database. To do this, it will be necessary to develop a program that facilitates the readability of the data as requested by the P.O., in addition to automating the cleaning process for future inputs to the database.

### Characteristics of the .sql file:


One of the files we receive is an .sql file (data_sql.sql). After a first visualization of the document in MySQl Workbench we find:

- At the beginning of the file, we see the characteristics of the file, which are not necessary for the project objectives.

- From line 24 of this file, we observe a series of data arranged in such a way that we can see that it is a table.

- Regarding the structure of the data, it can be seen that the rows of the future table are organized within parentheses. In turn, within each parenthesis, we see the division of columns by commas (",").

- The large number of "errors" recorded is striking.

- It is evident that the name of the columns is not available in this file.

- At the beginning of each line there is a number corresponding to the "indices_sql". These indexes relate each row of the .sql file to the row of the same index in the .xml file and the .txt file.

- Moreover, these records present the data for a column that the P.O. has asked us to delete (d482xta).



### Cleaning the .sql file
Once everything discussed in the previous section has been observed, we proceed to work with the .sql file in MySQL Workbench. To do this we have to take into account the requirements of the O.P.:
- Change the "ERROR" to "NULL".
- Remove the column d482xta.

When taking the data to introduce of the section "VALUES" of the .sql file, we observe that they are inserted correctly in the table "data_sql" created in the database project1.
