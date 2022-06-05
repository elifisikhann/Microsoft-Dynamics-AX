## Work with performance and monitoring tools in Finance and Operations apps



### Diagnose performance issues by using Trace parser

By using Trace parser, you can consume traces, and analyze performance in your Finance and Operations apps deployment. This ensures that you have an idea of what is currently happening in your deployed environments and helps ensure that business users have the **response time** that they need for their daily processes.

Trace parser is available in the **PerfSDK** folder on your development environment deployments.

### Diagnose issues and analyze performance by using Trace parser

You can create traces by performing the actions that you want to analyze.

To capture a trace, you must first ensure that you have completed the list of tasks that you need to analyze to avoid having metadata and other tasks included in your trace. You must also add the System tracing user role to the user who needs to complete the trace. In the Finance and Operations user interface, go to **System administration > Users > Users**. From there, you can select the user and select **Assign roles** on the **User's roles** FastTab.

Some of these performance issues may include 

- l**ong-running X++ methods, **
- **time-consuming SQL queries, **
- **or client server calls**.

--------------------

##### Scenario:

Contoso USA users are experiencing performance issues when they try to post a payment journal. The time it has been taking for the journal to post is taking much longer than it should. As a developer for Contoso USA, you have been tasked to diagnose why posting payment journals is taking so long.

Follow these steps to investigate the performance issues:

1. Login to Finance and Operations apps and start a trace from the **Help and support** menu.

2. Name the trace.

3. Select **Start**.

4. Perform the business operation that you are diagnosing. In this case, you would post a payment journal.

5. Stop the trace.

6. Download the trace. It is important to keep in mind that when the trace is downloaded, it will be deleted.

7. Select **Upload trace**. You should receive a message in the Action center that the trace has been uploaded.

8. Return to the **Tracing** main menu

9. Select **Captured traces**. The captured traces page will open with the trace you just captured.

10. Now you can launch Trace Parser, import the trace and analyze.------------------

11. Before you can analyze a trace, you need to download the Trace Parser. To download the trace parser application, follow these steps:

    1. In your developer virtual machine, open File Explorer.
    2. Find the Trace Parser .exe file. In most Tier 1 boxes, the download can be found in E:\AppRing3\10.0.8.10012\retail\Services\PerfSDK\Scripts.
    3. When Trace Parser is downloaded, start it.
    4. Register the database. To do this, specify the server name, and then name the database.
    5. Select **Register**.
    6. Select **Yes** when you are asked if you want to create the database.

    --------------------------

    

### Load testing by using the Performance SDK

#### Run a single user performance test with the Performance SDK

To start a performance test, follow these steps:

1. Create a task recording of a business process. When the recording is saved as a developer recording, and the XML file is downloaded, you need to configure your development environment. The development environment setup requires the downloading of zip files, adding folders into the PerfSDK library, and configuring files.
2. Generate a C# performance test from the task recorder file that you downloaded in Visual Studio. You will need to add references to specific DLLs and create new C# classes for the task recorder.
3. When the setup is completed, you will be able to run the single user testing in the **Test Explorer** through Visual Studio. Be sure to run your business process's end-to-end scenario first before you capture it to avoid slow or additional tasks while you are recording.
4. When you record your scenario in the task recorder, enter values manually instead of selecting them from the drop-down lists to ensure that the tests can create data.
5. Replay your task recording before downloading it to make sure that every step was recorded. Restart Visual Studio if you don't see your test case after the solution has been built.

#### Set up Azure DevOps for multi-user testing

Before running a multi-user performance test, you need to verify several prerequisites on your environment:

- Visual Studio Enterprise Edition will need to be in the development environment that you are using.
- You need to have a tier-2 or above sandbox environment on the same application and platform update as your development environment.
- You cannot proceed with multi-user testing without performing a single user test or having the C# testing classes generated for end-to-end scenarios.

When the development environment has been properly configured, the tier-2 or above sandbox must be prepared for multi-user testing. This process includes installing the same certificates that were created for the development environment on the tier-2 or above sandbox for all Application Object Servers (AOS) and ensuring that the users are created in the system.

### Monitor performance by using SQL Insights

SQL performance tools are viewed in LCS through the **Environment Monitoring** page on the **SQL Insights** tab. Within this tab, you can view **Performance Metrics**, **Index Analysis**, **Live View**, **Queries**, and **Actions** for a specific environment.



- **Performance Metrics** - Shows you the most expensive queries that were run in the system during a selected period based on duration in milliseconds, logical input/output, execution count, CPU time in milliseconds, and wait time. The data collection is pulled once daily and is stored for 30 days. On the **Statement** tab within **Performance Metrics**, you can view the query and download the query run plan.
- **Index Analysis** - Shows aggregated table and index information from user scans, seeks, updates, and row count. You can view the trend for your selected index and additional table metrics.
- **Live View** - Shows you the current DTU and running and blocking statements.
- **Queries** - Shows a list of predefined queries that are used to retrieve metrics on an on-demand basis. Most queries are run synchronously to ensure that the results are returned instantaneously. If you're having performance issues, the query runs could cause a time-out error. If this happens, select the option to turn off **Use Fast Query** and rerun the query.
- **Actions** - Shows a list of predefined actions that you should use to mitigate issues in sandbox and production environments. These actions include adding or dropping an index, updating statistics on a table, rebuilding indices, terminating a blocking statement, and others. You can view environment history based on the action that was performed.

#### Advanced troubleshooting with SQL Insights

For advanced troubleshooting, you can view the raw information logs. Before exporting the logs, you can use predefined queries to get the raw logs for an issue to aid in your diagnostics and monitoring. The different types of predefined queries include slow queries, deadlocks, crashes, and financial reporting issues.

In addition to raw logs, an advanced SQL troubleshooting tool enables performance analysis. These tools are similar to the DynPerf tool that is used in Microsoft Dynamics AX 2012.

### Create a SQL trace by using the SQL Profiler

There are many reasons why you would want to use the SQL Profiler. For example, you may need to see all the long-running queries on the SQL server system, not just the long-running queries in Finance and Operations apps.

To access and use the SQL Profiler, follow these steps:

1. In SQL Server Management Studio, open **SQL Server Profiler** from the **Tools** menu.
2. Connect to the database.
3. In the **Trace Properties** windows, name your trace.
4. When you have specified all properties, select **Run**.
5. While the SQL Profile trace is running, you perform the process or processes that are of concern. For example, users may be experiencing slowness when adding data to the SalesTable. In this case, you will ask the user to perform the task, while the trace is running.
6. When the process is complete, stop the trace by selecting the **Stop** button in the menu.
7. Now you can analyze the trace by reviewing the trace results. The following screenshot shows what the trace looks like when it is stopped.

### Monitor server health metrics in LCS

By using the **Environment Monitoring** and **SQL Insights** that come in a user-friendly dashboard, you can see measurements and diagnostics of your environment's health. 

Within the **Health metrics** dashboard, some issues are reported directly to the Microsoft Service Engineering Team and some are mitigated immediately.



#### Types of health checks performed with Health metrics

Several types of health checks can be performed within the **Health metrics** interface, which you can use to make observations about your environment. The health checks span various services and components of the environments, including the following:

- AOS
- Batch frameworks
- Data Import/Export framework
- Microsoft Azure SQL
- Management reporter

The checks are performed based on multiple data sources, like the telemetry that is collected from the environments, the checks that are done by a continuously monitoring watchdog service, CP counters, along with other system-level counters that the environment produces. As previously mentioned, some health checks are reported to the Microsoft Service Engineering team for direct investigation.



On the **Environment Monitoring** page, select the **Health metrics** tab to view the monitoring dashboard. Health metrics are collected for all machines and components that relate to the environment that you selected in LCS. The health metrics that you can view are CPU usage, available memory, errors logged per second, and batch heartbeat.

The **Activity** tab contains several different charts and sections. The user interaction chart shows user activities on various machines in the environment, as well as the SQL utilization trend. The **activity load** section shows the various activities that were performed on each machine, while the **user load** section shows all the system users and the time that the user spent on a specific machine. 





**What is the performance tool that can consume traces and analyze performance?**

Performance SDK

Health monitor

SQL Insights

**Trace parser**



**You need to see an individual user’s activity on a specific environment. How would you accomplish this task?**

**Check the activity monitor in LCS.**

Use Visual Studio to run diagnostics.

Check the Full details page for an environment in LCS.

View the System administration module in Finance and Operations apps.



**Is it true that some diagnostics from Health metrics in LCS are sent directly to the Microsoft Service Engineering team?**

**Yes**

No







