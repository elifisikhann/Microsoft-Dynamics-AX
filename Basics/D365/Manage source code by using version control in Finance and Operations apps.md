## Manage source code by using version control in Finance and Operations apps

# Configure Visual Studio to connect to Azure DevOps

Visual Studio integrates with Azure DevOps to help you to collaborate with other developers and protect the integrity of your stable builds.

The integration of Visual Studio and Azure DevOps lets you:

- Connect an Azure DevOps project to Finance and Operations apps.
- View, get, and roll back changes.
- Resolve merge conflicts to avoid losing work.
- Conduct code reviews to ensure that your source is the best it can be.

Bringing all these features together lets you, the developer, handle all your duties in one place. Mastering them will help your projects run smoothly and improve your ability to contribute to a development team.



When you have a project in Azure DevOps to host your repository, you are ready to connect with Visual Studio to start developing. Everything you need to interact with Azure DevOps is found under the **Team** heading on the menu bar or in the **Team Explorer** window.

![Screenshot of the team explorer window view.](https://docs.microsoft.com/tr-tr/learn/modules/manage-source-code-version-control-finance-operations/media/team-explorer.png)

To connect to an Azure DevOps project from Visual Studio, follow these steps:

1. Select **Manage Connections** in the **Team Explorer** window or under the **Team** header on the menu bar. This option might appear simply as a green plug icon.
2. All the existing project connections from your local machine will be available to select in the window that appears. Right-click and select **Connect** to make the connection.
3. In the window that opens in the **Team Explorer** window, select **Manage Connections**.
4. Select **Connect to Team Project**. This will open a new dialog box.
5. In the dialog box, select **Servers**.
6. This opens a new dialog box, where you will enter the Azure DevOps URL. If the URL looks like `clientname.visualstudio.com`, and it usually does, the remaining fields will be automatically populated.
7. After you confirm these settings, a new dialog box will prompt you to sign in to Azure DevOps.
8. When you have signed in, select the box for the desired Azure DevOps project on the **Team Projects** pane.
9. Select **Connect**.
10. Select **Advanced Configuration** to open a dialog box for adjusting the parameters of your workspace mapping.
11. Select **Advanced** in this dialog box for more options.
12. Change the workspace from a **Private** workspace to a **Public** workspace.
13. In the **Working folders** table, remove all existing mappings.
14. On a new row of the table, map the **Projects** folder of the desired branch of your Azure DevOps project to your local user's **Projects** folder for Visual Studio.
15. On another row in the table, map the **Metadata** folder of the same branch of your Azure DevOps project to the **Packages Local Directory** folder of the **AOS Service** drive.
16. Select **OK**.
17. Select **Close** to exit all open dialog boxes.



# Manage and perform code reviews

To submit code for review from Visual Studio, follow these steps:

1. Go to **My Work** in the **Team Explorer** window.
2. Make sure that all the changes you want to have reviewed are visible in the **In Progress Work** section.
3. In the **In Progress Work** section, select **Request Review**.
4. Enter any users that you would like to review your changes.
5. Enter a name and description for your changes.
6. Select **Submit Request**.
7. Optionally, you can name your shelveset and select **Suspend** so that you can work on other changes while you wait for review.

To perform a code review, follow these steps:

1. Right-click **code review request**.
2. Select **Open**.
3. Select **Accept** to let the requestor know that you have agreed to review their work.
4. Open each file in the shelveset and use the **Difference** window to see the changes side by side with the original file contents.
5. In the **Team Explorer** window, add any comments that you have to the relevant files. Comments link to a text selection, like in a Microsoft 365 document, so be aware of that when you add each new comment.
6. When you have reviewed each file, select **Send Comments** to let the reviewer know what changes you have recommended.
7. If you have no comments, select **Close Review** and indicate that the changes passed your review so that the reviewer knows to check them in.





If you happen to make a mistake, perhaps your code reviewer will catch that mistake and send you one or more comments. To view and address these comments, follow these steps:

1. Go to the **My Work** page in **Team Explorer**.
2. If you suspended your work after submitting it for review, select it in the **Suspended Work** section.
3. Select **Resume**.
4. Right-click **Code review request**.
5. Select **Open**.
6. Select each comment to view the relevant code and incorporate the review feedback.
7. After you have addressed the feedback in a comment, select the box for that comment to indicate that you have done so.
8. Depending upon your team's practices and the scope of the changes that you make in response to feedback, you might want to submit a new code review after you have addressed all of the comments.





**You are setting up Visual Studio to connect to Azure DevOps on a machine that hosts a Finance and Operations apps environment. Which of the following should you do?**

Set the permissions of the workspace to Public Workspace (limited).

Map the folder for the branch in source control to the local Visual Studio documents Projects folder.

**Map the Metadata folder for the branch in source control to the Packages Local Directory folder of the AOS drive.**

Set the location of the workspace to Server.



**Suppose you have just used Get Latest Version to bring updated files from source control into Visual Studio, and you suspect that local changes you wanted to keep were removed during an auto-merge. Which of the following can you do to troubleshoot the issue?**

Roll back the changesets that you pulled from source control.

Go to Pending Changes in Team Explorer for a list of differences between your workspace and source control.

Use the Undo button to restore the changes that you wanted to keep.

**Check the Output window in Visual Studio for logs of which files were auto-merged.**



**Which of the following source control features is not accessible from Visual Studio?**

Checking in your pending changes.

Submitting and responding to code review requests.

Rolling back changesets from source control.

**Creating a new Azure DevOps project.**









