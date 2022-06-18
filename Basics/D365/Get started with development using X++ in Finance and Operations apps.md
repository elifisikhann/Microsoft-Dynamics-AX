# Get started with development using X++ in Finance and Operations apps

X++ has a user-friendly memory management model that is identical to .NET. A few areas where X++ differs from other managed languages are:

-   Strong data access statements
-   Tight integration with system and user metadata
-   A strong extensibility story with Pre/Post event handlers and chain of command
-   Case insensitivity, meaning that "While," "while," and "WHILE" are the same (C# is case-sensitive)
- 
## Data types

**Primitive data types** are the most common data types that you will encounter. The primitive data types are:  
`anytype`,  `boolean`,  `date`,  `enum`,  `guid`,  `int`,  `int64`,  `real`,  `str`,`timeOfday`, and  `utcdatetime`.

### Composite data types
-   **Arrays**  - Contain a list of items that have the same data type. You can retrieve an element in the array with an integer index. You can use arrays in different ways. Dynamic arrays are open and fixed-length arrays specify a certain length. Partly on disk arrays can be dynamic or fixed, with an option to determine how many items are held in memory.
-   **Containers**  - Are dynamic collections of primitive items or other containers. Containers can be useful to pass different types of values, but they are not ideal when used in processes that frequently change the size or contents.
-   **Classes**  - Can be used as a data type to declare an instance of a class within a method.
-   **Delegates**  - Can be defined on a method, table, form, or query. When a delegate is called, it will also call their subscriber methods. Delegates never return a value and have a default value of “no handlers added,” which means nothing is called when you call them.
-   **Tables**  - Can be used to declare an instance of a table. Once a table instance is declared, you can manipulate the data within the table. We recommend that the table variable has the same name as the table, but you should use camel casing. For example, the table EcoResProduct would be declared by using camel casing as ecoResProduct.

### User-defined data types

Extended data types (EDT) are user-defined types that are based on the  `boolean`, `int`,  `int64`,  `real`,  `str`,  `date`, and  `container`  data types. EDTs can be used on variables, method parameters and field declarations, and they provide several benefits. First, they make code easier to read because the EDT name can be defined by the user. Therefore, instead of using just  `str`, you could use an EDT called Color, which would be a more meaningful name. You can also set certain properties on the EDT that all instances of that type use. Additionally, you can create hierarchies for EDTs so an EDT can inherit the properties of a parent.

## Variables

Variables are identifiers that designate a storage location where a value of a data type is stored. The size, precision, default value, and conversion functions depend on the variable's data type. Variables can be declared anywhere in a code block in a method; they do not have to be declared at the beginning of a method.


**int a = 1 << 2 (this equals 1*2*2.)**

**int a = 1 >> 2 (this equals 1/2/2.)**

**You need to create and assign a data type to a variable. The variable should only have access to a defined list of values “Invent,” “Sale,” and “Purchase.” Which data type should you use?**

The string data type should be used.
**The enum data type should be used.**
The integer data type should be used.
The container composite data type should be used.


**You need a conditional statement that checks if a variable equals “In progress,” “Completed,” or “Canceled.” Different code needs to run, depending on what the variable equals. A default block of code needs to run if the variable does not equal any of the values. What conditional statement is most appropriate?**

Error handling
A ternary operation
If statement
**Switch statement**


**An error is sometimes thrown in a certain try…catch block. You know that the issue can be fixed within the code during the error handling code block. What statement could you use when the error is found to run the code again?**

The throw statement should be used in the catch statement to rerun the try block.
The finally statement should be used in the catch statement to rerun the try block.
**The retry statement could be used in the catch statement to rerun the try block.**
A business system function should be used in the catch statement to rerun the try block.


Several pieces of X++ code come together to perform tasks.
-   Variables can be used with a data type to assign values to an object.
-   Operators and global functions compare, manipulate, and calculate the variable values.
-   Methods are written to perform specific tasks with those variables.
-   Conditional statements determine the flow of code within those methods.
-   Error handling deals with exceptions that might occur during the code runtim









