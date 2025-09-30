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
While there isn't a direct RENAME command for all objects in SQL Server, you can use system stored procedures like sp_rename to rename tables, columns, indexes, and other objects.

```sql 

   EXEC sp_rename 'practice.students.firstName','first_Name','COLUMN';

```
## DROP using ALTER:

```sql

ALTER TABLE practice.students
DROP COLUMN IF EXISTS address;
```


```sql

ALTER TABLE practice.students
ALTER COLUMN lastName VARCHAR(100) NOT NULL;

```

## 3. TRUNCATE

- This command removes all the records from a table. But this command will not destroy the table's structure.
  
- This will delete all the records from the table
his command removes all the records from a table while preserving the table's structure.

- It's a DDL (Data Definition Language) operation and cannot be rolled back in many database systems.

- Much faster than DELETE for removing all records because it doesn't generate individual row delete operations.

- Resets identity/auto-increment columns to their seed value.

- Requires higher privileges than DELETE (usually requires DROP table permission)

```sql

TRUNCATE TABLE Students; 

```

## When to Truncate

- When you need to quickly remove all records from a large table

- When you want to reset identity counters

- When you don't need to filter specific records

- When you don't need the operation to be logged for rollback


## 4. DROP

This command completely removes the table from the database along with its structure, indexes, constraints, and triggers.

It's irreversible - once executed, the table and all its data are permanently deleted.

All relationships and dependencies with other tables will be broken.

Requires careful consideration as data recovery is difficult without backups.

```sql
DROP TABLE Student; 

```


## TRUNCATE vs DROP - Comparison Table

| Feature | TRUNCATE | DROP |
|---------|----------|------|
| **Data Removal** | Removes all records | Removes all records |
| **Table Structure** | ✅ Preserved | ❌ Destroyed |
| **Speed** | ⚡ Very Fast | ⚡⚡ Fastest |
| **Rollback** | Limited | Not possible |
| **Identity Reset** | ✅ Yes | ❌ No (table gone) |
| **Storage Space** | Reclaims data space | Reclaims all space |
| **Use Case** | Empty table for reuse | Remove table permanently |

## Simple Analogy:
- **TRUNCATE** = Emptying a filing cabinet (keep the cabinet)
- **DROP** = Throwing away the entire filing cabinet

## When to Use:
- **TRUNCATE** → Quickly clear a table you plan to reuse
- **DROP** → Permanently remove a table entirely













###  Advantages of DDL
 
**Defines Structure:**  DDL commands like CREATE and ALTER allow you to set up and modify the structure of database objects (tables, indexes, views), organizing data effectively.

**Manages Schema:** allows users to easily create, update, or remove entire database schemas, making it simpler to maintain and update the database structure over time.

**Enforces Data Integrity:** DDL allows the implementation of rules and constraints (PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL) that ensure data remains accurate and consistent.

**Standardized:** DDL commands are standardized across most SQL-based databases, making it easier to apply knowledge across different database systems.


## Disadvantages of DDL

**Irreversible Changes**  
**Risk of Data Loss**  
**Complex for Large Databases** : Altering the structure of large databases can be complicated and may require downtime or additional planning to avoid disrupting operations.

