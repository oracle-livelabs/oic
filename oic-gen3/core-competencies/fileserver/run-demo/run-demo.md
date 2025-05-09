# Run end-to-end Integration Flow

## Introduction

This lab will walk you through the steps to run the integration flow.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:

- Create a file in the File Server
- Track message flow triggered
- Verify the sales orders record in ATP Table

### Prerequisites

This lab assumes you have:

- Completed all previous labs successfully

## Task 1: Create a sales order file in the File Server

1. Copy the below data set in a file **sales.csv** and save it to your desktop.

    ```
    <copy>
    Order ID,Region,Country,Item Type,Sales Channel,Order Priority,Order Date,Ship Date,Units Sold,Unit Price,Unit Cost,Total Revenue,Total Cost,Total Profit
    2225000001,Australia and Oceania,Tuvalu,Baby Food,Offline,H,2025-05-01,2025-05-05,9925,255.28,159.42,2533654,1582243.5,951410.5

    </copy>
    ```

    > **Note:** If you are a Bootcamp user then modify Order IDs to the unique values as all the participants would be using same database and it may cause duplicates in the database table

2. Connect to the File Server. Copy sales.csv from your desktop to a folder on the File Server that you specified in the integration flow

## Task 2: Monitor your integration flow

1. From the *Projects* page, Click on **Observe &gt; Instances**
2. Click on **Instance id** in the Confirmation Window which will Navigate to the **Tracking** page.

## Task 3: Verify sales orders record in ATP Table

Follow these steps to view the sales orders record in the designated DB table.

1. If you are not already logged in to Oracle Cloud Console, log in and select **Autonomous Database** from the navigation menu.

    > **Note:**  You can also directly access your Autonomous Data Warehouse or Autonomous Transaction Processing service in the **Quick Actions** section of the dashboard.

2. Navigate into your ATP database by clicking on the instance link.
3. In your ATP Database Details page, click the **Database Actions** button.
4. Sign in with your database instance's default administrator account

5. The SQL Worksheet appears. In the *Navigator* on the left, select the **V\_SALES\_ORDERS** table, then right-click on **Open**.

6. Click on **Data** in the left menu to display the table data. Verify your inserted Sales Orders records.

**Congratulations!** You have learned how to download a file from File Server and bulk import data into ADW leveraging Out of the box ADW adapter capabilities. Thank you!

## Learn More

- [Activate Integration](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/activate-and-deactivate-integrations.html)

- [Monitor Integration](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/track-integration-instances.html#GUID-46A7C0A0-CBE4-4F1B-9B45-62A5AFA89D74)

## Acknowledgements

- **Author** - Subhani Italapuram, Product Management - Oracle Integration
- **Last Updated By/Date** - Subhani Italapuram, May 2025
