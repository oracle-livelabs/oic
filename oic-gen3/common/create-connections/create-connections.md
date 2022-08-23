# Create Connections

## Introduction


This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 10 minutes

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
2. select the **FTP** Adapter and click **Select**.
3. From the *Create Connection* dialog, *Name* your connection as **File Server** and leave the rest of the configurations as default. Click **Create**.  
**Note**: If you get an error that the identifier already exists, change the Connection Name and remember this name for use later in the workshop.
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

You may now **proceed to the next lab**.


## Learn More

* [Oracle Integration FTP Adatper](https://www.oracle.com/pls/topic/lookup?ctx=en/cloud/paas/integration-cloud&id=ICSFT-GUID-59194DED-31DC-4E3D-893C-0064D7CC65A0)

## Acknowledgements
* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Last Updated By/Date** - 
