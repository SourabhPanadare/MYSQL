# MYSQL Basic Commands

  $ mysql -u root -p
  mysql> ALTER USER 'user-name'@'localhost' IDENTIFIED BY 'NEW_USER_PASSWORD';
  mysql> FLUSH PRIVILEGES;
  mysql> quit;
  
  mysql> SHOW DATABASES;
  mysql> USE db_name;
  mysql> SHOW TABLES;
  mysql> DESCRIBE table_name;  //Shows the alter view of table with (datatypes)
  

# MYSQL DataTypes

  a. Numeric DataType:-		
  
		TINYINT		Integer(-128 to 127)	
		SMALLINT	Integer(-32768 to 32767)		
		MEDIUMINT	Integer(-8388608 to 8388607)		
		INT			Integer(-2147483648 to 2147483647)		
		BIGINT		Integer(-9223372036854775808 to 9223372036854775807)		
						
		FLOAT		Decimal(upto 23 digits)			
		DOUBLE		Decimal(24 to 53 digits)	
		DECIMAL		'Double' stored as string
					DECIMAL(P,D)	P:- number of significant digits(1 to 65)
									D:- number of digits after the decimal point
					
		BIT			Bit(1 to 64)	Bit(7):- '1011101' 
		
  b. Boolean DataType:-(0 or 1)
  
		BOOLEAN     TINYINT(1) 0:- false and 1:- true
		
  c. String DataType:- 
  
		CHAR		String(0 - 255)			A fixed-length nonbinary string
        VARCHAR		String(0 - 255)			A variable-length non-binary string
		
		TINYTEXT	String(0 - 255)			A very small non-binary string
		TEXT		String(0 - 65535)		A small non-binary string
		MEDIUMTEXT	String(0 - 16777215)	A medium-sized non-binary string
		LONGTEXT	String(0 - 4294967295)  A large non-binary string
		
		BLOB		String(0 - 65535)		A small binary large object
		MEDIUMBLOB	String(0 - 16777215)	A medium binary large object
		LONGBLOB	String(0 - 4294967295)  A large binary large object
		
  d. Date and Time DataType:-
  
       DATE			A date value in (YYYY-MM-DD)
	   TIME			A time value in (hh:mm:ss)
	   DATETIME		A date and time value in (YYYY-MM-DD hh:mm:ss)
	   TIMESTAMP	A date and time value in (YYYYMMDDhhmmss)
	   
# MYSQL Crud Structure

  a. Create Table Command:-
  
	   1. Create Command - command used to create new table;
	   2. Insert Command - command used to insert new values in table; 
  
       CREATE TABLE table_name (column_name column_type constraints);
	   
	   column_name – Name of the particular column with any space.
	   column_type – Datatype of the column. Datatype can be – char(), varchar(), int(), float(), etc.
	   constraints – In order to give restrictions to particular column. Constraints can be – not null, primary key, foreign key, etc.
	   
	   Create table student(
	        id  int NOT NULL AUTO_INCREMENT,
			name varchar(30) NOT NULL, 
			marks int
	   );
	   
	   INSERT INTO table_name ( field1, field2,...fieldN ) VALUES ( value1, value2,...valueN );
	   
	   Insert into student (name, marks) values ('sourabh', 55);
	   
  b. Read Operation:-
	  
	  SELECT * FROM table_name; OR SELECT column_name FROM table_name;
	  
	  select * from student;
	  
  c. Update Operation :-
  
      1. Alter Command – This is the DDL command (Data Definition Language) used to change the structure of the table.
	  2. Update Command – This is the DML command(Data Manipulating Language) used to alter the records.
	  
	  ALTER TABLE table_name [alter_option [, alter_option] ...][partition_options];
	  
	  Alter table student modify name varchar(50) NOT NULL;
	  
	  UPDATE table_name SET column_name = new_value WHERE unique_column_name = some_value;
	  
	  Update student set marks = 100 
	  where id = 1;
	  
  d. Delete Operation:- 
  
	  1. Drop Command – DDL command	used to delete the table.
	  2. Truncate Command - command used to clear all the records of table.
      3. Delete Command – DML command used to delete the records of the table.	  
	  
	  DROP TABLE table_name;		
	  
	  Drop table student; //Delete student table from database
	  
	  TRUNCATE TABLE table_name;
	  
	  Truncate table student; //Makes student table empty
	  
	  DELETE FROM table_name WHERE unique_column_name = some_value;
	 
	  Delete from student 	//Removes value from table with id 2
	  where id = 2;
	  

	   