# Login-System
This is a login system, that saves the credentials into a database.

Short Description: This script connects to a MySQL database, retrieves a list of databases and tables, updates the customers table by adding new columns, and prints the updated table information 📊.

Documentation:
Importing Modules 📚

The code starts by importing two modules:

    mysql.connector: a driver that allows Python to connect to a MySQL database 📈.
    tabulate: a module used to format tabular data in a visually appealing way 📊.

Establishing a Connection to the Database 📁

The code then establishes a connection to a MySQL database using the mysql.connector module. The connection parameters are:

    host: the hostname of the database server, which is 127.0.0.1 (localhost) 🏠.
    port: the port number used to connect to the database server, which is 3306 🔒.
    user: the username used to authenticate with the database server, which is root 👑.
    password: the password used to authenticate with the database server, which is also root 🔑.

Creating a Cursor Object 🖋️

A cursor object is created using the cursor() method of the connection object. This cursor object is used to execute SQL commands in Python 💻.
Retrieving a List of Databases 📂

The code executes the SQL command SHOW DATABASES using the cursor object, which retrieves a list of databases in the MySQL server. The result is stored in the cursor object 📝.
Printing the List of Databases 📄

The code then prints the list of databases by iterating over the cursor object and printing the first element of each row (i.e., the database name) 📊.
Switching to the credentials Database 🔀

The code executes the SQL command USE credentials to switch to the credentials database 🔓.
Defining a Function to Update Tables 🔄

A function named update_tables is defined, which updates the customers table by adding four new columns:

    postcode: a VARCHAR(10) column 📨.
    username: a VARCHAR(10) column 👥.
    key: a VARCHAR(255) column 🔑.
    created_at: a TIMESTAMP column with a default value of the current timestamp ⏰.

Retrieving a List of Tables 📊

The code executes the SQL command SHOW TABLES to retrieve a list of tables in the credentials database. The result is stored in the cursor object 📝.
Printing the List of Tables 📄

The code then prints the list of tables using the tabulate module. The table names are extracted from the cursor object and formatted into a grid with a single column header "Table Name" 📊.
Retrieving and Printing Table Columns 📝

For each table, the code executes the SQL command DESCRIBE <table_name> to retrieve the column information. The result is stored in the cursor object. The code then prints the column information using the tabulate module, with column headers "Name", "Lastname", "email", "postcode", "username", "key", and "created_at" 📊.
Verifying the Changes 🔍

The code executes the SQL command DESCRIBE customers to retrieve the updated column information for the customers table. The result is stored in the cursor object. The code then prints the updated column information 📊.
Closing the Cursor and Connection 🔚

Finally, the code closes the cursor and connection objects using the close() method 👋.
