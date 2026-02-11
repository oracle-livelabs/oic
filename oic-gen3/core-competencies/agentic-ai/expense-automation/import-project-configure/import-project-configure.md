# Import the Project and Configure

## Introduction

In this section, you'll import the pre built *Intelligent Expense Automation with Agentic AI* project into your Oracle Integration environment and configure the necessary connections for the integrations. The project contains four integrations that will become agentic AI tools.

You'll need to configure three essential connections:

- FTP Adapter Connection - For retrieving patient data files from healthcare repositories
- HCM Cloud Connection - For creating an expense record.
- REST Adapter Connection - For Trigger Interface
- OpenAI LLM Connection - For the AI agent's Large Language Model reasoning capabilities

By the end of this section, you'll have a fully operational project with all connections configured and tested, ready for agentic AI tool registration.

Estimated Time: 30 minutes

### Objectives

In this lab, you will:

- Import a Project

### Prerequisites

This lab assumes you have:

- All previous labs completed.
- [Download](https://objectstorage.us-phoenix-1.oraclecloud.com/p/pPTpr7j-uEqeREEidVSaOBtI8m8hafxYqXJpUiX9QmyUJ_3wYFwx_2yXc9JNhxGj/n/oicpm/b/oiclivelabs/o/oic3/core-competency/agentic-ai/lab_artifacts.zip) the Lab artifacts and unzip on your local computer. The lab artifacts contains a .car file (OIC Project) and few .csv and .json files which will act as data source for this usecase.

## Task 1: Import Project

1. Login into Oracle Integration console.

2. Navigate to the Projects Section. If you don't see the Projects option, you may need to expand the menu by clicking the hamburger icon (☰) at the top left.

3. On the Projects page, look for an **Add** button in the top-right corner of the page. Click *Add* and Select *Import* action

    ![Start New Project](images/start-new-project.png)

4. Locate the OIC project file **INTEL\_EXPEN\_AUTOM\_WITH\_AGENT\_AI-EXPENSECREATION.car** on your local computer. Refer the Prerequisites section above to download the artifacts. Drag the file and drop it into the upload area in the dialog

5. Click on *Import*.

6. Upon successful import, you should see Project Name: **Intelligent Expense Automation with Agentic AI** and clone the project with modify the project name which consists of your initials and delete the imported project so that others can do these steps if it is shared environment.

## Task 2: Explore the Imported Project

1. Once inside the project, you should see the Project Overview page showing:

    - Project Name: Intelligent Expense Automation with Agentic AI
    - Integrations section with the four integrations:

        - **1. Read Expense Receipt** — Retrieves expense receipt images from a file server and uses AIs-powered document understanding to extract structured expense details such as date, amount, merchant, and line items.
        - **2. Approval Required** — Applies AI reasoning and policy evaluation to determine whether the expense complies with organizational rules or requires managerial approval.
        - **3. HITL-Raise Approval Request** — Triggers a human-in-the-loop review when exceptions, policy violations, or confidence thresholds demand explicit authorization before proceeding.
        - **4. Create Expense in Oracle HCM** — Once validated, automatically creates the expense record in Oracle HCM, ensuring accurate categorization, audit traceability, and seamless downstream processing.

    - Decisions
        - Expense Approval: A decision table used to determine whether approval is required based on the expense type (Food or Airfare) and the expense amount.
    - Human-In-The-Loop
        - Expense Workflow: If approval is required, this workflow is triggered and a task is assigned to the user. The user must log in to the Process Workspace to approve or reject the task.
    - Connections
        - REST Connection
        - FTP Connection : This is the place where your files are stored
        - HCM Cloud Connection

TIP: Edit each integration and click on **Learn about the Integration** to understand the details of the integration flow.
![Learn About the Integration](images/learn-about-integration.png)

## Task 3: Configure Connections

All the connections are in draft state. We will configure the connections used by the integration flows.

**REST Connection Configuration**

1. Edit the REST Connection.

2. Configure the Security Policy as **OAuth 2.0 Or Basic Authentication**

3. Click on **Test** and *Save* the connection.

**HCM Connection Configuration**

1. Edit the HCM Connection.

2. Configure the host and username and password.

3. Click on **Test** and *Save* the connection.

**FTP Adapter Connection Configuration**

Keep the following information handy. Note: Refer File Server Setup section
    - File Server IP Address.
    - File Server Port.
    - Your Oracle Integration username.
    - Your Oracle Integration password.

1. Edit the FTP Adapter Connection.

2. Configure the below properties in the connection properties page. Enter the following configurations you previously gathered from the File Server Settings page.  

    | Field                   | Value                                                 |
    |-------------------------|-------------------------------------------------------|
    | FTP Server Host Address | From File Server Settings - IP and Port Information   |
    | FPT Server Port         | From File Server Settings - IP and Port Information   |
    | SFTP Connection         | Yes                                                   |
    | Security                | FTP Server Access Policy                              |
    | Username                | Your Oracle Integration username                      |
    | Password                | Your Oracle Integration password                      |
    {: title="FTP Adapter Connection Properties"}

3. Confirm your Connection by clicking **Test**, then **Diagnose & Test**. You should see the *Connection File Server was tested successfully* confirmation message. Click **Save** and exit the Connection editor.

4. Click on **Test** and *Save* the connection.

**OpenAI LLM Adapter Connection Configuration**

1. Edit the open AI LLM Adapter Connection.

2. Configure the below properties in the connection properties page.

    | Field                   | Value                                                 |
    |-------------------------|-------------------------------------------------------|
    | Base URL                | **<https://api.openai.com>**                                |
    | Models                  | **gpt-4o-mini**                                           |
    | API Key                 | <You open ai API Key> Refer: <https://platform.openai.com/api-keys>   |
    {: title="OpenAI Adapter Connection Properties"}

3. Click on **Test** and *Save* the connection.

Verify that all the connections are in Configured state.

## Task 4: Configure the File(FTP) Server

1. Using an FTP Client of your choice, connect to FTP Server with the information from [File Server Setup](?lab=setup)

2. Copy the files (food.jpeg, food_comliant.jpeg) into FTP server location. For example, copy these two files to the folder /home/users/fileserveroic3user/oicusername. You can create your own folder under /home/users/fileserveroic3user and copy the files in into new directory which you have created.

## Task 5: Configure the Decision and Activate

1. Click on *Decision* tab, edit the decision **Expense Approval**, review the business rules and go back to the *Decisions*
2. Activate **Expense Approval** decision.

## Task 6: Configure the Human in the loop(HITL) and Activate

1. Click on *Human in the loop* tab, edit the form **Expense Form**, review the form and activate the form
2. Edit the **Expense Workflow**, review **Start event**, review **End event** and click on **Expense Approval** user action OR select **Expense Approval** action , click on **Open Properties**
![Expense Workflow1](images/expense-workflow1.png)
3. Click on the user under **Assignees** and remove the existing user and add your oic username.
![Expense Workflow2](images/expense-workflow2.png)
4. Select the form under UI section if it is not selected already.
5. select **Expense Approval** action, click on **Open Data Association**, check *Input* and *Output* assignments.
![Expense Workflow3](images/expense-workflow3.png)
![Expense Workflow4](images/expense-workflow4.png)
6. Go back to *Workflows* which is under *Human in the loop* tab by clicking *back* button
7. Activate *Expense Workflow*
8. Please note that If, existing workflow is not working then try to create new workflow and use existing workflow as a reference for json samples.

## Task 7: Configure the integrations and Activate

1. Edit **Read Expense Receipt** integration, go through all the actions of the integration flow and modify the compartment name if required in OCI Document Understanding action and activate it.
2. Edit **Approval Required** integration, Edit *OCI Generative AI* action and modify the *Region, Compartment, Model and Model ID* as per your OCI environment and Edit *Decision Service* and make sure that it is pointing to the correct decision service if not, make a note of source and target mappings and delete the *Decision Service*, add new decision service which will point to the correct decision service and map the source and target elements. And finally,  activate the integration flow.
3. Edit **HITL-Raise Approval Request** integration, Edit *Human in the loop* action and make sure that it is pointing to the correct process or HITL if not, make a note of source and target mappings and delete the *Human in the loop* action, add new *Human in the loop* action which will point to the correct process and map the source and target elements. And finally,  activate the integration flow, refer the mappings given below in the screenshot.
![HITL mappings](images/hitl-mappings.png)

4. Edit **Create Expense Oracle HCM** integration, go through the all the actions and please note that we have hard coded username as *CASEY.BROWN* to create the expense report on behalf of actual user to reduce the number of calls for this lab. And finally, activate the integration flow

You may now **proceed to the next lab**.

## Learn More

- [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)

- [About Projects](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/integration-projects.html)

- [Activate Integration](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/activate-and-deactivate-integrations.html)

- [Monitor Integration](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/track-integration-instances.html#GUID-46A7C0A0-CBE4-4F1B-9B45-62A5AFA89D74)

- [Open AI Adapter](https://docs.oracle.com/en/cloud/paas/application-integration/openai-adapter/openai-adapter-capabilities.html)

## Acknowledgements

- **Author** - Ankur Jain, Kishore Katta, Subhani Italapuram, Product Management, Oracle Integration
- **Last Updated By/Date** - Subhani Italapuram, Feb 2026
