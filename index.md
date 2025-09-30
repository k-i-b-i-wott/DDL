# Data Definition Language
- Set of commands used to create a structure and maintain databases.

- DDL basically deals with the storage of the data and not the data itself
### Commands used in DLL
- CREATE
- DROP  
- ALTER  
- TRUNCATE
- RENAME


## 1 Create

This command is used to create table in the relational database.
This can be done by specifying the names and data types of various columns.  

```sql 
CREATE TABLE Students
        (
            id INT PRIMARY KEY,
            firstName VARCHAR(50) NOT NULL,
            lastName VARCHAR(50) NOT NULL,
            course VARCHAR(100) NOT NULL
        );


````

## 2 ALTER

Alter command is used for altering the table in many forms like: 

1.   Add a column
2. Rename existing column
3. Drop a column
4. Modify the size of the column or changedatatype of the column

## ADD using ALTER

The above command will add a new column to the table.And the resulting table   

```sql

ALTER TABLE Students 
ADD
(Address  VARCHAR(200)); 


```
## RENAME using ALTER:

```sql 

ALTER TABLE 
    Students 
    RENAME 
    Marks TO Age ; 

```
## DROP using ALTER:

```sql

ALTER TABLE Student 
DROP
(Age);  

```
## MODIFY using ALTER:

```sql

ALTER TABLE 
Students 
MODIFY
(name varchar(300)); 

```

## 3. TRUNCATE

This command removes all the records from a table. But this command will not destroy the table's structure.
This will delete all the records from the table

```sql

TRUNCATE TABLE Students; 

```


## 4. DROP

This command completely removes the table from the database along with the destruction of the table structure

```sql
DROP TABLE Student; 

```

###  Advantages of DDL
 
**Defines Structure:**  DDL commands like CREATE and ALTER allow you to set up and modify the structure of database objects (tables, indexes, views), organizing data effectively.

**Manages Schema:** allows users to easily create, update, or remove entire database schemas, making it simpler to maintain and update the database structure over time.

**Enforces Data Integrity:** DDL allows the implementation of rules and constraints (PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL) that ensure data remains accurate and consistent.

**Standardized:** DDL commands are standardized across most SQL-based databases, making it easier to apply knowledge across different database systems.


## Disadvantages of DDL

**Irreversible Changes**  
**Risk of Data Loss**  
**Complex for Large Databases** : Altering the structure of large databases can be complicated and may require downtime or additional planning to avoid disrupting operations.

