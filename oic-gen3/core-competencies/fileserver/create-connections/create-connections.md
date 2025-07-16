# Create Connections

## Introduction

This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Create an Oracle Autonomous Transaction Processing connection

### Prerequisites

This lab assumes you have:

- Completed all the previous labs.

## Task 1: Create an Oracle Autonomous Transaction Processing Connection

Create a connection with the Oracle Autonomous Transaction Processing Adapter.

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You can please skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.

3. In the *Create Connection* dialog, select the **Oracle ATP** adapter to use for this connection. To find the adapter, enter `ATP` in the search field. Click on the highlighted adapter.
    
4. In the *Create Connection* dialog, enter the following information and click **Create**

    | **Field**        | **Value**          |
    | --- | ----------- |
    | Name         | `ATP Database`       |
    | Role  | Select `Invoke` |
    | Description  | `ATP Connection for LiveLabs` |

    Keep all other values as default.

    > **Note:** If you are a Bootcamp user then execute step 5 only and skip other steps.
    If you are a non Bootcamp user then skip step 5 and continue with other steps..

5. Search for **ATP Database**, Please note that the connection with the name **ATP Database** is already created by the instructors, configured and shared with other projects. Do not get confused with the same name, both the connections are in the different projects. Click on **ATP Database** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Oracle ATP Connection* dialog, enter the following information:

    | **Field**  | **Value** |
    |---------------|----------------|
    |Service Name | `<your-adb-tns-name>` (Use the TNS Name obtained in **Setup lab** &gt; **Task 2** &gt; **Step 6**) |
    |Security Policy | **JDBC Over SSL**|
    |Wallet | **Upload wallet file (Zip)** |
    |Wallet Password | `<wallet-password>`|
    |Database Service Username | `<db-service-username>` (Default: `ADMIN`)|
    |Database Service Password | `<db-service-password>` |
    
    > **Note:**  The information obtained from the Lab *Setup* will be used to fill in the details to create Connection.

7. Click on **Test**, followed by **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.


You may now **proceed to the next lab**.

## Learn More

- [Shared Connection across the Projects](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/design-project.html#GUID-8B2FBBB5-4F68-4690-AD73-19F79E5577C8)
- [Oracle Integration ATP Adapter](https://docs.oracle.com/en/cloud/paas/application-integration/atp-adapter/oracle-autonomous-transaction-processing-adapter-capabilities.html#GUID-706DC653-CD39-4C75-89CA-B7CF5867EDF1)

## Acknowledgements

- **Author** - Subhani Italapuram, Oracle Integration Product Management
- **Last Updated By/Date** - Subhani Italapuram, May 2025
