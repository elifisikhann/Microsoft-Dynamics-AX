# Explore the test framework and tools in Finance and Operations apps

##  Unit test framework
Visual Studio comes with a SysTest Framework that allows you to write unit test code, integrate the tests, and then run the test to automate code testing. You can also import Task recorder recordings into Visual Studio to generate test code.
Your test can then be integrated into a test module which can be used to manage test code and `FormAdaptors`.
![Diagram of the Unit test model process from author tests, integrate tests and then execute tests.](https://docs.microsoft.com/tr-tr/learn/modules/explore-test-framework-tools-finance-operations/media/unit-test.jpg)


To create a new test case to test functionality in an application, follow these steps:

1.  Open Visual Studio as an administrator.
2.  Create a new project.
3.  Add a new Class to the project.
4.  Extend the  **SysTestCase**  class in the class declaration.
5.  Add methods to the class to define the test. These methods should use the  **[SysTestMethodAttribute]**  attribute.
6.  The following code represents an example test class by using the Fleet Management model.
7.  Save the class. Two test cases will be available in the Test Explorer.
8.  Build the project.
9.  On the  **Test**  menu, open  **Windows > Test Explorer**.
10.  Select  **Run selected test**  to run a specific test case. The results will display after the  **Test Explorer**  is complete.

# Acceptance test library
The Acceptance test library (ATL) is an X++ test library that allows developers to create consistent test data. It makes test code more readable, and methods that create test data become more easily discovered. ATL also supports high performance of test cases. You can use the classes within the ATL to create repeatable tests that will write test data and run processes by using that data. This feature can simplify some of the more complicated data setup and processes that would be required testing through the user interface (UI).

When creating classes and methods in ATL, you must follow rigid structuring and naming. Classes are grouped into the following concepts:

-   **Navigation**  - Discover entities and test data methods.
-   **Test data methods**  - These methods are used to set up test data.
-   **Entities**  - Represent data and associated behavior that is perceived as a single unit.
-   **Creators**  - Let you create specific test data.
-   **Commands**  - Run business operations.
-   **Queries**  - Find entities.
-   **Specifications**  - Describe expected entities at the end of the test.

# Task recorder
The Task recorder helps users write test cases that represent a business process task or business process. It focuses on high-responsiveness, a flexible extensibility application programming interface (API), and seamless integrations with consumers of business process recordings.

The Task recorder is integrated with the Lifecycle Services (LCS) business process modeler (BPM) tool so that users can produce business process diagrams from recordings to design their applications. Additionally, the Task recorder can auto-generate application verification tests and play back previously-recorded processes.

The Task recorder records the user actions including button selections, value entry, and navigation.
# Identify various categories and types of errors
Error statements are developed before testing to dictate what should be displayed when a test passes or fails. You can handle errors by using the  `Throw`,  `Try...catch`,  `Finally`, and  `Retry`  statements to handle exceptions. An exception is a regulated jump away from the code run.

The `throw` keyword is used to throw an exception enum value.
The `try...catch` keywords are used to process a thrown exception through the catch.
The code in the `finally` code block will run when the code leaves the `try` block either normally or because of an error.
The `retry` keyword can only be written in a `catch` block. This causes the code to jump back to the first line in the `try` code block.

# Configure the testing environment and prepare data
Accurate data is key to measuring the success of code. You will need to set up the test environment and prepare data to be tested in Visual Studio. You will also need to deploy a testing environment for users to test customization to code. A testing environment should be a Tier-1 environment to perform unit tests in.

To prepare the test environment with proper data, you can use the  **Data management**  workspace (**System administration > Data management**).

![](https://docs.microsoft.com/tr-tr/learn/modules/explore-test-framework-tools-finance-operations/media/data-management.png#lightbox)

# Run unit tests
Large projects can have multiple developers who are creating code in their own environments. Before pushing code changes to production, unit tests should be performed to verify the code. Unit tests must follow specific syntax. The class must extend the  `SysTestCase`  class. Test methods must be public, cannot have parameters, must return void, and need to be decorated with the  `SysTestMethod`.

Test methods typically have three distinct methods: arrange, act, and assert. The arrange method sets up all the variables. The act method does some processing. The assert method verifies if the result is expected. You can use the `setup()` method that is built into the framework to arrange the variables that will be used throughout the test methods.
You can choose from several different assert methods to verify the test. `AssertEquals()` is the most common, but other methods are available, such as `assertTrue()` and `assertNotNull()`.



**Which of the following is not a function of the Task recorder?**

 - Create task guides of a process that users can follow. 
 - Generate unit tests in Visual Studio. 
 - **Periodically run to automatically complete a task.** 
 - Create on-rails playback that limits users to only be able to
   select elements within the task recording.

**You are running the debugger. The breakpoint comes to a line saying custTable.insert(). How can you descend into the Insert method?**

 **- Select the Step Into button.** 
 - Select the Step Over button. 
 - Select the Step Out button.
