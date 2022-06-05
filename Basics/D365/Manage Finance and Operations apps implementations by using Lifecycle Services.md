## Manage Finance and Operations apps implementations by using Lifecycle Services

Lifecycle Services is your hub for environment management in the cloud. Environment creation, updates, code deployments, and database refresh all take place within Lifecycle Services. Additionally, Lifecycle Services allows you to stop and start key services without having to open a remote desktop protocol (RDP) session.



### Perform support tasks

From the main menu, on the **Full details** page of any environment in Lifecycle Services, select **History**, and then select **Environment Changes** from the drop-down menu. The resulting page shows you every package that has been applied from the Asset library to the environment, be that a platform update, a code package, or a database maintenance task.

For environments Tier 2 and up, the **Move database** option is also available under the **Maintain** menu. This option allows you to export a backup of the environment's database to the Asset library, import a backup from the Asset library, or refresh the environment's database directly from another Tier 2 environment.

Another option that is available in environments Tier 2 and up is Restart services, which allows you to **remotely restart IIS, Batch, the Lifecycle Services Diagnostic service, DIXF, or the Reporting server.**

### Additional support

### Dynamics 365 Community

### Issue search

---------------------------------

### Provision and manage environments

The table of cloud-hosted environments on the **Cloud-Hosted Environments** page of a project has an **Add** button so you can deploy new environments.

When you select the name, application version, platform version, and purpose of the environment that you want to deploy, you should consider changing a few key settings:

- **VM type** - Depends upon your client's needs.
- **Machine name** - Makes your RDP window headers more human-readable than a GUID.
- **Data** - If you don't want demo data, make sure that **None** is selected.



### Manage asset libraries

The asset library is divided into many categories that contain different kinds of files. Some of the types of files that you are most likely to use include:

- **BPM artifact** - Documents pertaining to the Business process model (BPM).
- **Database backup** - Files that you can use to restore an SQL or Azure SQL database.
- **Model** - Prepackaged extensions that you can install on an environment.
- **Software deployable package** - Packages that you built from Azure DevOps of code that was developed in Visual Studio.



The asset library can grow in two ways:

- Use the **Import** button to bring in files that are **published by Microsoft or Independent Software Vendors (ISVs).** This opens a table that you can filter for the package you need. When you find the correct package, select it and confirm your import.
- Add files to the asset library by **uploading files from your computer** by using the **Add** button. Enter a name and description for your asset and select **Upload File**, which will take you to another screen. Select **Browse** to open a File Explorer window, which you can use to locate the file. When you've made your selection, use the **Upload** button to add the file to your asset. With your asset complete, confirm it to add it to the library.

----------------

Remember, when making code changes, do not use the `.Extension` file extension so that you can avoid future compatibility issues.

-------------------



**Which of the following processes cannot be performed from Lifecycle Services?**

Deploy a new environment

Update the code on an existing environment

**Restore an image of an environment.**

Upgrade an environment to a new platform version.



**Which feature of Lifecycle Services can be used to export a backup of a database to the Asset library for environments that are Tier 2 or above?**

**Move database**

Apply updates

Reporting server

Environment changes



**To manage the Asset libraries, there are different file types that serve various functions. Which file is for prepackaged extensions that can be used to install on an environment?**

Database backup

Software deployable package

BPM artifact

**Model**





































