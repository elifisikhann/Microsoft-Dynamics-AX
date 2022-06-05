# Q&A About AX



#### **What is MorphX in AX 2012?**

MorphX is an integrated development environment (IDE) of Microsoft Dynamics AX. MorphX is used to modify forms, reports, tables, menus, etc. 

Includes:

- Data Dictionary
- Tools for creating menus, forms and reports for Windows- and Web clients
- Compiler and debugger for the object oriented programming language X++
- Version control system
- Label (multi language text) systems

#### What is **IntelliMorph**?

IntelliMorph is the **Runtime Environment embedded technology** that controls the user interface (menus, forms, and reports) for Windows- and Web-clients with the correct contents, size, and layout according to:

- The language your texts are displayed in.
- What features you can access.
- How wide you want the fields on your installation.
- The formats you are using for dates and numbers.

**For example:**

1.When you use field groups, IntelliMorph can automatically update the layout of all related forms and reports whenever a modification is made to the field groups.

2.When you create **reports**, it is recommended that you use the **Auto design.**



#### What is X++

X++ is the object-oriented programming language that is used in the MorphX environment.

Integrates SQL queries into standard Java-style code. 

#### **Difference between edit and display method?**

Display Indicates that the *method’s return value* is to be displayed on a form or a report.
The value **cannot be altered** in the form or report
Edit Indicates that the *method’s return* *type* is to be used to provide information for a field that is used in a form. The value in the field **can be edited** and that users can also **write data** to the fields.

#### **Difference between perspectives and table collection?**

Perspectives can organize information for a report model in the Application Object Tree 
A perspective is a collection of tables. You use a report model to create reports.
Table collection is a collection of tables, which sharing across all the virtual companies.

#### **How can we restrict a class to be further extended?**

Using Final Keyword for ex: public final class

#### **Which classes are used for data import-export?**

SysDataImport and SysDataExport

#### **From which table u can get the user permissions stored in Ax?**

AccessRightList table.

#### **What should we do if we need the last record to be active when a form is opened?**

In the properties of the data source table set the **start position** property as last.

#### **What is the sequence of events while a report is generated?**

Init, Run, Prompt, Fetch, send, Print

#### **Name a few X++ classes/Coreclasses related to Queries?**

Query, QueryRun, QueryBuildRange, QueryBuildDataSource, QueryBuildLink

#### **Define AOT?**

**Ans:** The Application Object Tree (AOT) is a tree view of all the application objects within Microsoft Dynamics AX. The AOT contains everything you need to customize the look and functionality of a Microsoft Dynamics AX application

#### **Define AOS?**

**Ans:** The Microsoft Dynamics AX Object Server (AOS) is the second-tier application server in the Microsoft Dynamics AX three-tier architecture.
The 3-tier environment is divided as follows:

1. First Tier – Intelligent Client --handles the user interface 
2. Second Tier – AOS --handles the business logic
3. Third Tier – Database Server-- the database runs on a server
   

### **What is an index?**

An index is a table-specific database structure that **speeds** the retrieval of rows from the table. Indexes are used to improve the **performance** of data retrieval and sometimes to ensure the **existence of unique** records.

indexes are synchronized with the database.

Once created, indexes are managed automatically by the DBMS every time a record is inserted, updated, or deleted. 

When an index is disabled, it's deleted from the database and rebuilt if it's enabled later

********

 *The system attempts to order the index according to the first field, and if there is more than one record with the same value in this field, the sorting conflict is resolved by looking at the next field and so on.* When selecting table fields for an index consider the following:

- Fields that are often searched by a range.

- Fields that frequently participate in joins.

- Fields that are frequently used to order or group a result set.

  In theory, a table can have an unlimited number of indexes. However, it's common to have at most a few indexes enabled because every insert, update, and delete causes each index to be updated and can affect performance.

  **********

  There are two types of indexes: unique and non-unique. 

Whether an index is unique is defined by the index's **AllowDuplicates** property.

System Index (RecId - DataAreaId)

Microsoft Dynamics AX requires a unique index on each table so if there are no indexes on a table or all the indexes are disabled, a system index is automatically created. The system index is created on the RecId and DataAreaId fields if the DataAreaId field exists. Otherwise the system index is created on the RecId field. 

If there are indexes on a table but none of them are unique, the runtime estimates the average key length of the existing indexes, chooses the index with the smallest key length and appends the RecId column to create a unique index.



#### **Difference between Primary & Cluster index?**

**Primary index:** It works on unique indexes. The data should be unique and not null. Retrieve data from the database.
**Clustered Index:** It works on unique and non-unique indexes. retrieve data from the AOS.

Creates a physical column in table.

The advantages of having a clustered index are as follows:

1. Search results are quicker when records are retrieved by the clustered index, especially if records are retrieved sequentially along with the index.
2. Other indexes that use fields that are a part of the clustered index might use less data space.
3. Fewer files in the database; data is clustered in the same file as the clustering index. This reduces the space used on the disk and in the cache.

The disadvantages of having a clustered index are as follows:

1.  It takes longer to update records (but only when the fields in the clustering index are changed).
2. . More data space might be used for other indexes that use fields that are not part of the clustered index (if the clustering index is wider than approximately 20 characters).

#### **When the record is generated, what is its utility?**

When the record is entered in the table the record is generated by the kernel. It is unique for each table.



#### Difference between InMemory and TempDB

| 1. Holds data temporarily in client or server tier | 1. Holds data temporarily in database till the scope is valid |
| -------------------------------------------------- | ------------------------------------------------------------ |
| 2. These tables can't be stored in Database        | 2. These tables are stored in the database                   |
| 3. Can't apply security                            | 3. Can apply security                                        |
| 4. We cannot use InMemory table buffers            | 4. TempDB table buffer can be used in coding                 |



**InMemory tables**

**Tier:** InMemory tables are instantiated in the active memory of which ever tier the process is running on, either the client or the server tier. InMemory tables are never represented in the database management system.
An InMemory table is held in memory until its size reaches 128 KB. The dataset is then written to a disk file on the server tier. The disk file for an InMemory table has the naming convention $tmp.$$$.

**Scope:** An InMemory table is instantiated when the first record is inserted. The instantiated InMemory table continues to exist only while a record buffer variable that references the table exists. The memory or disk space for the InMemory table is de-allocated as soon as the record buffer goes out of scope.

**Indexes:** can be defined on an InMemory table just as you would a persisted table. If an InMemory table is created by copying a persisted table, the indexes are also copied to the InMemory table. Indexes are useful for quickly retrieving data from InMemory tables, especially if the InMemory table data is in a disk file.



##### **TempDB tables**

**Capabilities of TempDB Tables:**

1. Can be joined with other AX tables
2. Can be either per company or global.
3. Can be used from Enterprise Portal by using .NET Business Connector.
4. Can have foreign key columns.
5. TempDB tables can be instantiated from the client or server tier.
6. Can have indexes columns.
7. Can have methods, but cannot override.
8. Usable as a query
9. Transaction support.
10. No configuration key is required.

**Limitations of TempDB Tables:**

1. Cannot be a valid time state table.
2. Cannot have any delete actions.
3. No Record Level Security (RLS).
4. Cannot use the Table browser form.
5. Cannot be in a table collection.
6. No view support.

**Lifetime of TempDB Tables:**
A TempDB table is instantiated in the underlying database management system when the first SQL operation is sent to the database system from the AOS. (select, insert, update, or delete)

The situations that cause a TempDB table to be dropped are:

1. Variable goes out of scope.
2. Controlled restart of the AOS.
3. Restart of the database system.
4. Closure of the AX32.exe client.
5. From Online Users form.

**TempDB Tables for Disabled Tables**
You can disable a regular persisted database table by disabling the configuration key that controls the table. Disabling the key causes the system to automatically create a TempDB style of temporary table that matches the fields and schema of the database table. This temporary table exists in the underlying SQL Server database and is managed by the Application Object Server (AOS).
The purpose of automatically creating this TempDB table is to enable AOT objects that reference the disabled table to continue to compile and run. You can read and write to this TempDB table even though the configuration key is disabled.
**Note:** All table buffer variables inherit the methods of the xRecord class. One such method is setTmp, which creates an InMemory temporary table that has the same schema as the regular table. However, the setTmp method cannot create an InMemory table from a TempDB table. You can call the method isTempDb to determine whether the setTmp method is available.

#### **Difference between temp table and container?**

1. Data in containers are stored and retrieved sequentially, but a temporary table enables you to define indexes to speed up data retrieval.
2.  Containers provide slower data access if you are working with many records. However, if you are working with only a few records, use a container.
3.  Another important difference between temporary tables and containers is how they are used in method calls. When you pass a temporary table into a method call, it is passed by reference. Containers are passed by value. When a variable is passed by reference, only a pointer to the object is passed into the method. When a variable is passed by value, a new copy of the variable is passed into the method. If the computer has a limited amount of memory, it might start swapping memory to disk, slowing down application execution. When you pass a variable into a method, a temporary table may provide better performance than a container

#### **Differentiate refresh(), reread(), research(), executequery()**

**refresh()** will not reread the record from the database.  It basically just refreshes the screen with whatever is stored in the form cache.
**reread()** will only re-read the CURRENT record from the DB so you should not use it to refresh the form data if you have added/removed records.  It’s often used if you change some values in the current record in some code, and commit them to the database using .update() on the table, instead of through the form data source.  In this case, .reread() will make those changes appear on the form.
**research()** will rerun the existing form query against the data source, therefore updating the list with new/removed records as well as updating existing ones.  This will honor any existing filters and sorting on the form.
**executeQuery()** is another useful one.  It should be used if you have modified the query in your code and need to refresh the form.  It’s like research() except it takes query changes into account.

#### **What is an EDT, Base Enum, how can we use array elements of an EDT?**

**EDT –** To reuse its properties. The properties of many fields can change at one time by changing the properties on the EDT. Relations can be assigned to an EDT are known as Dynamic relations.
EDT relations are Normal and Related field fixed.
Why not field fixed – field fixed works on only between two tables 1- 1 relation. And Related field fixed works on 1- many tables. so EDT uses related field fixed.
**BaseEnum** – which is a list of literals. Enum values are represented internally as integers. you can declare up to 251 (0 to 250) literals in a single enum type. To reference an enum in X++, use the name of the enum, followed by the name of the literal, separated by two colons. ex -NoYes:: No.

#### **What is the function of super()?**

This method calls the system methods to execute.
It is used to instantiating the variables at the parent class. Used for code redundancy.

#### **How many kinds of lookups can be made and how?**

By using table relations

1. Using EDT relations.
2. Using morphx and using X++ code(Syslookup class).

#### **How many types of data validation methods are written on the table level?**

validateField(): It is executed when we move the cursor from one field to another one.

validateWrite(): It is executed before inserting or updating a registry in the table.

validateDelete()

aosvalidateDelete(),aosvalidateInsert(), aosvalidateRead(),aosvalidateUpdate().

`Validate delete will be called automatically by AX when you delete record from UI. It won't be called if you call delete() from code or doDelete().`

`AOSValidateDelete will be called if you will call delete() or doDelete() method from code or deleting record from U`I.



#### **How many types of relations are available in Axapta, Explain each of them?**

Relations in Microsoft Dynamics AX:

- Keep the database consistent (enforce referential integrity).
- Are used by the Auto Join system in forms.
- Enable the look up of values in other tables (through lookup list/selection list boxes and the **View details** Form command).
- Are used to validate data.
- Automatically propagate changes from one table to another.
- Auto-define table relationships in queries.

Table relations are most commonly used in form fields to **enable the look up** of information in another table.

**Normal Relation:** enforce referential integrity such as foreign keys. For displaying lookup on the child table. to specify relation fields without conditions.
**Field fixed:** works as a trigger to verify that relation is active, if an enum field in the table has a specific value then the relation is active. It works on conditional relations and works on the enum type of data.   to specify relation fields to restrict the records in the primary table.
**Related field fixed:** works as a filter on the related table.it only shows records that match the specified value for an enum field on the related table. to specify relation fields that restrict the records in the related table.

**ForeignKey** to specify a correspondence between a foreign key field in the present table to the primary key field in another parent table.



#### **How many types of Delete Actions are there in Standard Ax and define the use of each?**

##### Cascade

A cascading deletion action will delete all records in the related table, where the foreign key is equivalent to the primary key of the current table. That is, deleting the *parent* record will also delete the *child* record(s) in the related table.

This cascading will take place whether the deletion is performed in code or directly by a user through the user interface.

##### Restricted

A restricting delete action will raise an error message if the user tries to delete a record, where records exist in the related table where the foreign key is equivalent to the primary key of the current table.

This error will only appear if the deletion is performed through the user interface. A deletion from X++ code will be allowed to proceed and will **not** be cascaded to the related table. In this case the programmer should call .validateDelete() themselves prior to the call to .delete()

##### Cascade+Restricted

This delete action normally works as a Restricted delete action. However if the deletion is performed through X++ code, no error will be raised and the deletion **will** be cascaded to the related table.



#### **Utility and use of find method?**

Easy to retrieve record from foreign code. All the tables should have at least one find method that selects and returns one record from the table that matches the unique index specified by the input parameters. The last input parameter in a find method should be a Boolean variable called for update or update that is defaulted to false. When it is set to true, the caller object can update the record that is returned by the find method.

#### **Definition and use of Maps, how AddressMap (with methods) is used in standard AX?**

Maps define X++ elements that wrap table objects at run time. With a map, you associate a map field with a field in one or more tables. This enables you to use the same field name to access fields with different names in different tables. Map methods enable you to create or modify methods that act on the map fields.
Address map that contains an Address field. The Address map field is used to access both the Address field in the CustTable table and the ToAddress field in the CustVendTransportPointLine table























Sources

https://community.dynamics.com/365/financeandoperations/b/axtipsandtricks/posts/difference-between-inmemory-and-tempdb-tables-in-ax-2012



https://community.dynamics.com/ax/b/everydaylearningdynamicsax/posts/difference-between-temporary-table-and-container#:~:text=Data%20in%20containers%20are%20stored,few%20records%2C%20use%20a%20container.
