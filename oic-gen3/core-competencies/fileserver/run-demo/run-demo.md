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
- Download the Visual Builder application if you are running this application on your environment and import and setup in your Oracle Integration environment
    [OrderApplication](files/OrderApplication1-1.0.zip?download=1)

## Task 1: Modify the Order ID in the sales order file

1. Open the **sales.csv** file which you have downloaded in the previous lab, modify Order Id and save it to your desktop.

    > **Note:** If you are a Bootcamp user, please modify the Order IDs to unique values, as all participants will be using the same database. This will help prevent duplicate entries, which may otherwise violate unique constraints and result in data insertion failures

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

**Congratulations!** You have successfully learned how to use file events in OIC and insert data into ATP by leveraging the out-of-the-box capabilities of the ATP adapter. Thank you!

## Learn More

- [Activate Integration](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/activate-and-deactivate-integrations.html)

- [Monitor Integration](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/track-integration-instances.html#GUID-46A7C0A0-CBE4-4F1B-9B45-62A5AFA89D74)

## Acknowledgements

- **Author** - Subhani Italapuram, Product Management - Oracle Integration
- **Last Updated By/Date** - Subhani Italapuram, May 2025
