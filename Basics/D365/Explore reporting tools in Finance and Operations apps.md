# Explore reporting tools in Finance and Operations apps

The five reporting experiences are:

-   **Operational views**  - Show specific data that is needed for the organization. This includes creating reports that can be customized to show analytical data and transactional views.
    
-   **Business documents**  - Reports that are used to capture and exchange processed business data. This includes regulatory documents and documents that capture business transactions, such as sales invoices.
    
-   **Analytical tools and visualizations**  - Present the data in a way that allows users to manipulate and explore their data. Creating a view of customer sales for each quarter could be an example of an analytical report.
    
-   **Electronic reporting**  - Can be used to configure formats for electronic documents. This tool is used often with tax reporting, electronic invoicing, or any report that would need to be sent electronically.
    
-   **Financial reporting**  - Provides in-depth accounting management tools based on financial activity across a company. Financial reporting includes documents such as balance sheets and cash flow.

Use an **operational view** if you need a report that is intended for the organization to monitor data and transactions. If the report does not need to be shared or printed, and if data should be near real time.

You should use a **business document** when you need a report for the back office to show real-time transactional data. The data needs to be distributed as a file through email or printers. If you need to let users create their own views to explore near real-time data quickly by using dashboards, tiles, and visualizations, you should consider using analytical tools and visualizations such as Power BI.

**Electronic reporting** should be used if the user needs to be able to create real-time reports on transactional data that allow electronic transfer and use Microsoft Excel export capabilities. The financial reporting tool should be considered when accounting reports need to be created for financial officers, and the reports need printing and Excel export capabilities.

### Create and modify report data sources and supporting classes

Reports use data sources to pull data. SQL Server Reporting Services (SSRS) and Power BI are two reporting tools that use data sources. This unit covers the creation and modification of data sources for these reporting tools.

![Diagram of Data sources that can be assigned to an S S R S report.](https://docs.microsoft.com/en-au/learn/modules/explore-reporting-tools-finance-operations/media/data-sources.png)
In the report parameters, you can select the data source for the data set and the data source type. The data source type can be the following:
-   **Query**  - A query data source type uses an existing query or a new query.
-   **Business logic**  – Use this type to get a data source other than Finance and Operations apps.    
-   **Report data provider class**  – You can use this type when a query cannot be used alone. In this case, additional logic is needed to run the report. Along with the RDP class, a contract class is also needed to define the report parameters.    
-   **Enum provider**  – An AX enum provider can be used when the report parameter is an Enum type to filter the report view.


Power BI can connect to data sources, ranging from files, databases, other Power BI datasets and data flows, Azure databases, online services, and even web URLs.


## Implement reporting security requirements

**Authorization** is used to grant access to elements of the program through security permissions. Security permissions are combined into privileges, which are then combined into duties.

**Data security** is used to deny user access to tables, fields, and rows in the database. Data security uses the extensible data security framework **(XDS)** to control access to transactional data by assigning data security policies to security roles. These policies can restrict access to data, based on either the effective date or user data. We recommend that you use the extensible data security to help secure data.

In addition to these security options, the **Table Permissions Framework** can help protect data and is enforced by the Application Object Server (AOS). The Table Permissions Framework allows you to grant or deny Create, Read, Update, or Delete (CRUD) permissions to the data in a table. You can use this to give certain roles access to view and manipulate certain datasets.

## Publish a report

PowerShell
*C:\AosService\PackagesLocalDirectory\Plugins\AxReportVmRoleStartupTask\DeployAllReportsToSSRS.ps1 -PackageInstallLocation \"C:\AosService\PackagesLocalDirectory\" *

PowerShell
*C:\AosService\PackagesLocalDirectory\Plugins\AxReportVmRoleStartupTask\DeployAllReportsToSSRS.ps1 -Module ApplicationSuite -ReportName TaxVatRegister.Report*


****************************
**You need to create a report that a power user can create to explore data. The creation of the report should only take a few minutes and needs to allow the user to create charts and dashboards. This report does not need to be printed, sent by email, or exported to a file. What reporting tool should you use?**

Operational views
Business documents
**Analytical tools and visualizations**
Financial reporting


**You are implementing Finance and Operations apps and need to grant and deny user access to certain data and menu items. What tools are available that will allow you to do this?**

 - Role-based security
 - Extensible data security framework
 - Table permissions framework
 **- All the above**



**What are some reasons to deploy a report from the PowerShell?**

 - **You can deploy all the reports at once, and you can deploy reports in environments that are not Production and do not have Visual Studio.**
 - There is no reason to deploy reports from PowerShell. They should always be deployed from Visual Studio.
 - PowerShell can be used to deploy reports in the Production environment.
 - If you want to deploy reports to Finance and Operations apps, you must use PowerShell.
