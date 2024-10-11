# Create SOAP Connections

## Introduction


This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 15 minutes

### Objectives
In this lab, you will:

- Create ERP Cloud Integration Service connection using SOAP adapter
- Create ERP Cloud Callback connection using SOAP adapter

    > **Note:**  You can use an existing connection if one has already been configured for your environment.

### Prerequisites
This lab assumes you have:

- Completed all the previous labs

## Task 1: ERP Cloud Integration Service Connection

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You can please skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.
3. In the *Create Connection* dialog, select the **SOAP** adapter to use for this connection. To find the adapter, enter *soap* in the search field. Click on the highlighted adapter
4. From the *Create Connection* dialog, enter the following information and click on ***Create***:

    > **Note:**  If you get an error that the identifier already exists, enter unique connection name and remember this name for use later in the workshop.

    | **Field**   | **Value**                                        |
    | ----------- | ------------------------------------------------ |
    | Name        | `ERP Cloud Integration Service`                  |
    | Description | `ERP Cloud Integration Service for OIC LiveLabs` |

    Keep all other values as default.

    > **Note:** If you are a Bootcamp user then execute step 5 only and skip other steps.
    If you are a non Bootcamp user then skip step 5 and continue with other steps..

5. Search for **ERP Cloud Integration Service**, Please note that the connection with the name **ERP Cloud Integration Service** is already created by the instructors, configured and shared with other projects.
Do not get confused with the same name, both the connections are in the different projects so, we are good with it. And click on **ERP Cloud Integration Service** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Configuration* page, enter the following information:

    | **Field**       | **Values**                                                              |
    | --------------- | ----------------------------------------------------------------------- |
    | WSDL URL        | enter ***https://ERPCloudHost/fscmService/ErpIntegrationService?wsdl*** |
    | Security Policy | select ***Username Password Token***                                    |
    | Username        | Enter ***Enter ERP Cloud username***                                    |
    | Password        | Enter ***Enter ERP Cloud password***                                    |

7. Confirm your Connection by clicking ***Test***, then ***Validate & Test***. You should see the *Connection ERP Cloud Integration Service was tested successfully.* confirmation message. Click ***Save*** and exit the Connection editor.

## Task 2: ERP Cloud Callback Connection

> **Note:** If you are a Bootcamp user then skip step 1.

1. [Download the erpcbkinterface-onjobcompletion.wsdl](https://c4u04.objectstorage.us-ashburn-1.oci.customer-oci.com/p/EcTjWk2IuZPZeNnD_fYMcgUhdNDIDA6rt9gaFj_WZMiL7VvxPBNMY60837hu5hga/n/c4u04/b/livelabsfiles/o/oic-library/erpcbkinterface-onjobcompletion.wsdl)

2. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You can please skip this step if you are already in the project.
3. In the **Connections** section, click ***Add*** to create a new connection.
4. In the *Create Connection* dialog, select the **SOAP** adapter to use for this connection. To find the adapter, enter *soap* in the search field. Click on the highlighted adapter
5. From the *Create Connection* dialog, enter the following information and click on ***Create***:

    > **Note:**  If you get an error that the identifier already exists, enter unique connection name and remember this name for use later in the workshop.

    | **Field**   | **Value**                             |
    | ----------- | ------------------------------------- |
    | Name        | `ERP Cloud Callback`                  |
    | Description | `ERP Cloud Callback for OIC LiveLabs` |

    Keep all other values as default.

    > **Note:** If you are a Bootcamp user then execute step 6 only and skip other steps.
    If you are a non Bootcamp user then skip step 6 and continue with other steps..

6. Search for **ERP Cloud Callback**, Please note that the connection with the name **ERP Cloud Callback** is already created by the instructors, configured and shared with other projects.
Do not get confused with the same name, both the connections are in the different projects so, we are good with it. And click on **ERP Cloud Callback** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

7. In the *Configuration* page, enter the following information:

    | **Field**       | **Values**                                            |
    | --------------- | ----------------------------------------------------- |
    | WSDL URL        | upload the ***erpcbkinterface-onjobcompletion.wsdl*** |
    | Security Policy | select ***Security Assertion Markup Language(SAML)*** |

    ![erpcloud-callback](images/erpcloud-callback-conn.png)

8. Confirm your Connection by clicking ***Test***, then ***Validate & Test***. You should see the *Connection ERP Cloud Callback was tested successfully.* confirmation message.
9. Click ***Save*** and exit the Connection editor.

You may now **proceed to the next lab**.

## Learn More

- [Using the FTP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/ftp-adapter/ftp-adapter-capabilities.html)
- [Using the SOAP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/soap-adapter/index.html)

## Acknowledgements

- **Author** - Subhani Italapuram, Product Management, Oracle Integration
- **Last Updated By/Date** - Subhani Italapuram, Kishore Katta Oct 2024
