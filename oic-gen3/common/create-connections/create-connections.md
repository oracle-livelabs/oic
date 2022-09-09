# Create Connections

## Introduction


This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 20 minutes

### Objectives
In this lab, you will:
- Create an Oracle FTP Connection

### Prerequisites
This lab assumes you have:
- Completed all the previous labs.

## Task 1: Create Connection with File Server

To access the File Server from an Integration, you will need to create an FTP Connection.  
**Note**: You can use an existing connection if one has already been configured for your environment.

1. In the left Navigation pane, click **Design** > **Connections** > click **Create**
2. In the *Create Connection* dialog, select the **FTP** adapter to use for this connection. To find the adapter, enter FTP in the search field. Click on the highlighted adapter
3. From the *Create Connection* dialog, *Name* your connection as **File Server** and leave the rest of the configurations as default. Click **Create**.  
**Note**: If you get an error that the identifier already exists, enter unique connection name and remember this name for use later in the workshop.
4. Enter the following configurations in the *FTP Connection* with the information you previously gathered from the File Server Settings page.  
| Field                   | Value                                                 |
|-------------------------|-------------------------------------------------------|
| FTP Server Host Address | From File Server Settings - IP and Port Information   |
| FPT Server Port         | From File Server Settings - IP and Port Information   |
| SFTP Connection         | Yes                                                   |
| Security                | FTP Server Access Policy                              |
| Username                | Your Oracle Integration username                      |
| Password                | Your Oracle Integration password                      |

5. Confirm your Connection by clicking **Test**, then **Diagnose & Test**. You should see the *Connection File Server was tested successfully* confirmation message. Click **Save** and exit the Connection editor.

##	Task	2: Create Connection using REST adapter
Create a connection with the REST Adapter.

1. In the left Navigation pane of OIC, Click **Design** > **Connections** and Click **Create**.
2. In the *Create Connection* dialog, select the **REST** adapter. To find the adapter, enter `REST` in the search field. Click on the highlighted adapter.
3. In the *Create Connection* dialog, enter the following information and click on **Create**:

    | **Field**        | **Value**          |       
    | --- | ----------- |
    | Name         | REST Interface     |
    | Role         | Trigger       |
    | Description  | REST Interface Connection for OIC LiveLabs |

    Keep all other values as default.

4. In the *Configuration* page, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |Security Policy | OAuth 2.0 Or Basic Authentication |

5. Click on **Test**  and wait until you receive a confirmation box that the test was successful.
6. Click **Save** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

You may now **proceed to the next lab**.


## Learn More

* [Oracle Integration FTP Adatper](https://docs.oracle.com/en/cloud/paas/application-integration/ftp-adapter/ftp-adapter-capabilities.html)
* [Oracle Integration REST Adatper](https://docs.oracle.com/en/cloud/paas/application-integration/rest-adapter/rest-adapter-capabilities.html)

## Acknowledgements
* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Last Updated By/Date** -
