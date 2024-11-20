# DDL-Commands

## AIM:
To study and implement DDL commands and different types of constraints.

## THEORY:
1.CREATE:
This is used to create a new relation (table)

Syntax:
CREATE TABLE (field_1 data_type(size),field_2 data_type(size), .. . );

2.ALTER:
This is used to add some extra fields into existing relation. 

Syntax:
ALTER TABLE relation_name ADD (new field_1 data_type(size) );

(a)ALTER TABLE ...ADD...:
ALTER TABLE std ADD (Address CHAR(10));

(b )ALTER TABLE...MODIFY...:
ALTER TABLE relation_name MODIFY (field_1 newdata_type(Size)

( c) ALTER TABLE..DROP.... 
ALTER TABLE relation_name DROP COLUMN (field_name);

(d)ALTER TABLE..RENAME...:
ALTER TABLE relation_name RENAME COLUMN (OLD field_name) to (NEWfield_name);

3.DROP TABLE:
This is used to delete the structure of a relation. It permanently deletes the records in the table. 
Syntax:
DROP TABLE relation_name;

4.RENAME:
It is used to modify the name of the existing database object. 
Syntax:
RENAME TABLE old_relation_name TO new_relation_name;

CONSTRAINTS:
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE statement) or after the table is created (using ALTER TABLEstatement).
1.NOT NULL: When a column is defined as NOTNULL, then that column becomes a mandatory column. It implies that a value must be entered into the column if the record is to be accepted for storage in the table. 
Syntax:
CREATE TABLE Table_Name (column_name data_type (size) NOT NULL, );

2.UNIQUE: The purpose of a unique key is to ensure that information in the column(s) is uniquei.e. a value entered in column(s) defined in the unique constraint must not be repeated across the column(s). A table may have many unique keys. 

Syntax:
CREATE TABLE Table_Name(column_name data_type(size) UNIQUE, ….);

3.CHECK: Specifies a condition that each row in the table must satisfy. To satisfy the constraint, each row in the table must make the condition either TRUE or unknown (due to a null). Syntax:
CREATE TABLE Table_Name(column_name data_type(size) CHECK(logicalexpression), ….);

4.PRIMARY KEY: A field which is used to identify a record uniquely. A column or combinationof columns can be created as primary key, which can be used as a reference from other tables. A table contains primary key is known as Master Table. 
● It must uniquely identify each record in a table.

● It must contain unique values. 

● It cannot be a null field. 

● It cannot be a multi port field. 

● It should contain a minimum number of fields necessary to be called unique.

Syntax:
CREATE TABLE Table_Name(column_name data_type(size) PRIMARY KEY, ….);

5.FOREIGN KEY: It is a table level constraint. We cannot add this at column level. To reference any primary key column from other table this constraint can be used. The table in which the foreign key is defined is called a detail table. The table that defines the primary key and is referenced by the foreign keyis called the master table. 

Syntax:
CREATE TABLE Table_Name(column_name data_type(size)FOREIGNKEY(column_name)REFERENCES table_name);  

6.DEFAULT : The DEFAULT constraint is used to insert a default value into a column. The default value will be added to all new records, if no other value is specified.

Syntax:
CREATE TABLE Table_Name(col_name1,col_name2,col_name3 DEFAULT ‘’);

### Question 1:

Write a SQL Query for Creating a table name as "Employee" with the following attributes

eid as primarykey with autoincrement

name as varchar(50)

designation as varchar(30)

Answer:
CREATE TABLE Employee(

eid INTEGER PRIMARY KEY AUTOINCREMENT, name VARCHAR(50), designation VARCHAR(30)

);

Output:

![image](https://github.com/user-attachments/assets/f3bffbec-a545-4ca0-8b3e-2196b321e6d9)


### Question 2:

Consider a situation already created a table "customer" from that create a new table"customerbackup" with all the attributes available in the table "customer" 

Create a table name as "customerbackup" with all the attributes available in the table" customer"

Answer:

CREATE TABLE customerbackup AS

SELECT * FROM customer;

Output:

![image](https://github.com/user-attachments/assets/ca3ca458-92ff-4b8f-a4b0-ad6ccd8c72e9)



### Question 3:

Write a SQL Query for creating a table "Students" which already exists so use proper keyword inorder to avoid error message

Create a table name as "Students" with the following attributes ,use default keyword in the attribute year as 2

id as number

grade as varchar(50)

year as integer

Answer:

CREATE TABLE IF NOT EXISTS Students(

id number, grade varchar(50), year integer

);


Output:

![image](https://github.com/user-attachments/assets/9e0426b9-0f73-4586-8f2a-3cdc259953a4)

### Question 4:

Create a table name as "Employee" with the following attributes

eid as primarykey with autoincrement

name as varchar(50)

designation as varchar(30)

dob as date

doj as date

Answer:

CREATE TABLE Employee(

eid INTEGER PRIMARY KEY AUTOINCREMENT, name VARCHAR(50), designation VARCHAR(50), dob DATE, doj DATE, );

Output:

![image](https://github.com/user-attachments/assets/3efbb430-77b4-4632-9b87-18c8ad445205)





