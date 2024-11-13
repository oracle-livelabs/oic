# Create REST Connection

## Introduction

This lab will walk you through the steps to create a REST connection.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Create REST connection.

### Prerequisites

This lab assumes you have:

- Completed all the previous labs.

## Task 1: Create Connection using REST adapter

Create a connection with the REST Adapter.

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You can please skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.
3. Select the **REST** adapter. To find the adapter, enter `REST` in the search field. Click on the highlighted adapter.
4. In the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**        | **Value**          |
    | --- | ----------- |
    | Name         | REST Interface     |
    | Role         | Trigger       |
    | Description  | REST Interface Connection for OIC LiveLabs |

    Keep all other values as default.

    > **Note:** If you are a Bootcamp user then execute step 5 only and skip other steps.
        If you are a non Bootcamp user then skip step 5 and continue with other steps..

5. Search for **REST**, Please note that the connection with the name **REST Interface** is already created by the instructors, configured and shared with other projects.
Do not get confused with the same name, both the connections are in the different projects so, we are good with it. And click on **REST Interface** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Configuration* page, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |Security Policy | OAuth 2.0 Or Basic Authentication |

7. Click on ***Test***  and wait until you receive a confirmation box that the test was successful.
8. Click ***Save*** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

You may now **proceed to the next lab**.

## Learn More

- [Using the FTP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/ftp-adapter/ftp-adapter-capabilities.html)
- [Using the REST Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/rest-adapter/index.html)

## Acknowledgements

- **Author** - Subhani Italapuram, Product Management, Oracle Integration

- **Last Updated By/Date** - Subhani Italapuram, November 2024
