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

Display Indicates that the method’s return value is to be displayed on a form or a report.
The value **cannot be altered** in the form or report
Edit Indicates that the method’s return type is to be used to provide information for a field that is used in a form. The value in the field **can be edited** and that users can also **write data** to the fields.

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




Sources
https://docs.microsoft.com/en-us/dynamicsax-2012/developer/indexes-overview
https://mindmajix.com/
https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/deprecated-x-index-hint-clause
