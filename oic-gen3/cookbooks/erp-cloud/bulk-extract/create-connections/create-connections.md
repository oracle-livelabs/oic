# Create Connections

## Introduction


This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 15 minutes

### Objectives
In this lab, you will:
- Create an Oracle FTP Connection using FTP adapter
- Create ERP Cloud Integration Service connection using SOAP adapter
- Create ERP Cloud Callback connection using SOAP adapter
- Create ERP Cloud connection using ERP Cloud Adapter

    > **Note:**  You can use an existing connection if one has already been configured in your environment

### Prerequisites
This lab assumes you have:
- Completed all the previous labs

## Task 1: File Server Connection

> **Note: Ignore this section if you have a file server connection created already in your Project as part of one of the previous labs.**

To access the File Server from an Integration, you will need to create an FTP Connection.  

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You may skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.
3. Select the **FTP** Adapter.
4. From the *Create Connection* dialog, *Name* your connection as **File Server** and select *Role* as **Invoke** and leave the rest of the configurations as default. Click **Create**
    > **Note: If you are a Bootcamp user then execute step 5 ONLY and skip the other steps.
    If you are a non Bootcamp user then skip step 5 and continue from step 6..**

5. In the *Use a shared Connection* section, Search for **File**. Click on **File Server** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

![File Server Connection Reference](images/fileserversharedconn.png)

Please note that the connection with the name **File Server** is already created in your training instance, which is configured and shared with other projects. Although both the connections names are similar, they exist in the different projects. You can share adapter connection resources across projects. For example, you may have two projects that need to integrate with a common system, such as Oracle ERP Cloud. The connection you created is referencing the shared connection in the instance.

![Shared Connection](images/connection-sharing.png)

6. Enter the following configurations in the *FTP Connection* with the information you previously gathered from the File Server Settings page.  

    | Field                   | Value                                                 |
    |-------------------------|-------------------------------------------------------|
    | FTP Server Host Address | From File Server Settings - IP and Port Information   |
    | FPT Server Port         | From File Server Settings - IP and Port Information   |
    | SFTP Connection         | Yes                                                   |
    | Security                | FTP Server Access Policy                              |
    | Username                | Your Oracle Integration username                      |
    | Password                | Your Oracle Integration password                      |

7. Confirm your Connection by clicking **Test**, then **Diagnose & Test**. You should see the *Connection File Server was tested successfully* confirmation message. Click **Save** and exit the Connection editor.

## Task 2: ERP Cloud Integration Service Connection

> **Note: Ignore this section if you have a ERP Cloud Integration Service connection created already in your Project as part of one of the previous labs.**

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You may skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.
3. In the *Create Connection* dialog, select the **SOAP** adapter to use for this connection. To find the adapter, enter *soap* in the search field. Click on the highlighted adapter
4. From the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**   | **Value**                                        |
    | ----------- | ------------------------------------------------ |
    | Name        | `ERP Cloud Integration Service`                  |
    | Description | `ERP Cloud Integration Service for OIC LiveLabs` |
    | Role | `Trigger and Invoke` |

    Keep all other values as default.
    > **Note: If you are a Bootcamp user then execute step 5 ONLY and skip the other steps.
    If you are a non Bootcamp user then skip step 5 and continue from step 6..**

5. In the *Use a shared Connection* section search for **ERP Cloud Integration Service** and select the connection which is already created/shared in the Training instance. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Configuration* page, enter the following information:

    | **Field**       | **Values**                                                              |
    | --------------- | ----------------------------------------------------------------------- |
    | WSDL URL        | enter ***https://ERPCloudHost/fscmService/ErpIntegrationService?wsdl*** |
    | Security Policy | select ***Username Password Token***                                    |
    | Username        | Enter ***Enter ERP Cloud username***                                    |
    | Password        | Enter ***Enter ERP Cloud password***                                    |


5. Confirm your Connection by clicking ***Test***, then ***Validate & Test***. You should see the *Connection ERP Cloud Integration Service was tested successfully.* confirmation message. Click ***Save*** and exit the Connection editor.


## Task 3: ERP Cloud Callback Connection

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You may skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.
3. In the *Create Connection* dialog, select the **SOAP** adapter to use for this connection. To find the adapter, enter *soap* in the search field. Click on the highlighted adapter
4. From the *Create Connection* dialog, enter the following information and click on ***Create***:

  | **Field**   | **Value**                             |
  | ----------- | ------------------------------------- |
  | Name        | `ERP Cloud Callback`                  |
  | Description | `ERP Cloud Callback for OIC LiveLabs` |

Keep all other values as default.

  > **Note: If you are a Bootcamp user then execute step 5 ONLY and skip the other steps.
  If you are a non Bootcamp user then skip step 5 and continue from step 6..**

5. In the *Use a shared Connection* section search for **ERP Cloud Callback** and select the connection which is already created/shared in the Training instance. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Configuration* page, enter the following information:

    | **Field**       | **Values**                                            |
    | --------------- | ----------------------------------------------------- |
    | WSDL URL        | [Download the erpcbkinterface-onjobcompletion.wsdl](https://c4u04.objectstorage.us-ashburn-1.oci.customer-oci.com/p/EcTjWk2IuZPZeNnD_fYMcgUhdNDIDA6rt9gaFj_WZMiL7VvxPBNMY60837hu5hga/n/c4u04/b/livelabsfiles/o/oic-library/erpcbkinterface-onjobcompletion.wsdl) upload the ***erpcbkinterface-onjobcompletion.wsdl*** |
    | Security Policy | select ***Security Assertion Markup Language(SAML)*** |

    ![erpcloud-callback](images/erpcloud-callback-conn.png)

7. Confirm your Connection by clicking ***Test***, then ***Validate & Test***. You should see the *Connection ERP Cloud Callback was tested successfully.* confirmation message.
8. Click ***Save*** and exit the Connection editor.

## Task 4: Create ERP Cloud Adapter Connection

> **Note: Ignore this section if you have a ERP Cloud connection created already in your Project as part of one of the previous labs.**

Create a connection with the Oracle ERP Cloud Adapter.

1. In the left Navigation pane, click ***Projects***, click on the project which you have created.
    You may skip this step if you are already in the project.
2. In the **Connections** section, click ***Add*** to create a new connection.

3. In the *Create Connection* dialog, select the ***Oracle ERP Cloud*** adapter to use for this connection. To find the adapter, enter `erp` in the search field. Click on the highlighted adapter.
4. In the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**        | **Value**          |
    | --- | ----------- |
    | Name         | `ERP Cloud`       |
    | Description  | `ERP Cloud Connection for OIC LiveLabs` |

    Keep all other values as default.

    > **Note: If you are a Bootcamp user then execute step 5 ONLY and skip the other steps.
    If you are a non Bootcamp user then skip step 5 and continue from step 6..**

5. Search for **ERP Cloud**, Please note that the connection with the name **ERP Cloud** is already created by the instructors, configured and shared with other projects.
Do not get confused with the same name, both the connections are in the different projects so, we are good with it. And click on **ERP Cloud** and click on **Save**. Exit the connection canvas by clicking the back button on the top left side of the screen.

6. In the *Oracle ERP Cloud Connection* dialog, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |ERP Cloud Host | `your-erp-host-name` |
    |Security Policy | **Username Password Token**|
    |Username | `<erp-username>`|
    |Password | `<erp-password>`|

7. Click on ***Test*** and wait until you receive a
confirmation box that the test was successful.

    > **Note:** The first time you run the test, it could take up to 2 minutes for completion.

8. Click ***Save*** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

At the End of this section you should have following connections created in your Project

- ERP Cloud
- File Server
- ERP Cloud Callback
- ERP Cloud Integration Service

You may now **proceed to the next lab**.

## Learn More

* [Using the FTP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/ftp-adapter/ftp-adapter-capabilities.html)
* [Using the SOAP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/soap-adapter/index.html)

## Acknowledgements
* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Sep 2025
