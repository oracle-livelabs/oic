# Create ERP Cloud External Report Service Connection using SOAP Adapter

## Introduction

This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Create ERP Cloud External Report Service connection using SOAP adapter

    > **Note:**  You can use an existing connection if one has already been configured for your environment.

### Prerequisites

This lab assumes you have:

- Completed all the previous labs

## Task 1: Create ERP Cloud External Report Service Connection using SOAP Adapter

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You can please skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.
3. In the *Create Connection* dialog, select the **SOAP** adapter to use for this connection. To find the adapter, enter *SOAP* in the search field. Click on the highlighted adapter
4. From the *Create Connection* dialog, enter the following information and click on ***Create***:

    > **Note:**  If you get an error that the identifier already exists, enter unique connection name and remember this name for use later in the workshop.

    | **Field**        | **Value**          |
    | --- | ----------- |
    | Name         | `ERP Cloud External Report Service`       |
    | Description  | `ERP Cloud External Report Service for OIC LiveLabs` |

    Keep all other values as default.

    > **Note:** If you are a Bootcamp user then execute step 5 only and skip other steps.
    If you are a non Bootcamp user then skip step 5 and continue with other steps..

5. Search for **ERP Cloud External Report Service**, Please note that the connection with the name **ERP Cloud External Report Service** is already created by the instructors, configured and shared with other projects.
Do not get confused with the same name, both the connections are in the different projects so, we are good with it. And click on **ERP Cloud External Report Service** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Configuration* page, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |WSDL URL | enter ***<https://ERPCloudHost/xmlpserver/services/ExternalReportWSSService?WSDL>*** |
    |Security Policy | select ***Basic Authentication*** |
    |Username | Enter ***Enter ERP Cloud username received from the instructor*** |
    |Password | Enter ***Enter ERP Cloud password received from the instructor*** |

7. Confirm your Connection by clicking ***Test***, then ***Validate & Test***. You should see the *Connection ERP Cloud External Report Service was tested successfully.* confirmation message. Click ***Save*** and exit the Connection editor.

You may now **proceed to the next lab**.

## Learn More

- [Using the REST Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/rest-adapter/index.html)
- [Using the SOAP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/soap-adapter/index.html)

## Acknowledgements

- **Author** - Subhani Italapuram, Product Management, Oracle Integration
- **Last Updated By/Date** - Subhani Italapuram, Oct 2024
