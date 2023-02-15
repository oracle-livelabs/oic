# Create and Configure Connections

## Introduction


This lab will walk you through the steps to create connections for all the services which will be used in the Integration Flow.

Estimated Time: 10 minutes

### Objectives
In this lab, you will:
- Create a connection with File Server
- Create a connection with HCM Cloud Adapter

    > **Note:**  You can use an existing connection if one has already been configured for your environment.

### Prerequisites
This lab assumes you have:
- Completed all the previous labs


## Task 1: Create a connection with File Server

To access the File Server from an Integration, you will need to create an FTP Connection.  

1. In the left Navigation pane, click ***Design*** &gt; ***Connections*** &gt; click ***Create***
2. In the *Create Connection* dialog, select the **FTP** adapter to use for this connection. To find the adapter, enter FTP in the search field. Click on the highlighted adapter
3. From the *Create Connection* dialog, *Name* your connection as **File Server** and leave the rest of the configurations as default. Click ***Create***.  
    > **Note:**  If you get an error that the identifier already exists, enter unique connection name and remember this name for use later in the workshop.

4. Enter the following configurations in the *FTP Connection* with the information you previously gathered from the File Server Settings page.  
    | Field                   | Value                                                 |
    |-------------------------|-------------------------------------------------------|
    | FTP Server Host Address | From File Server Settings - IP and Port Information   |
    | FPT Server Port         | From File Server Settings - IP and Port Information   |
    | SFTP Connection         | Yes                                                   |
    | Security                | FTP Server Access Policy                              |
    | Username                | Your Oracle Integration username                      |
    | Password                | Your Oracle Integration password                      |

5. Confirm your Connection by clicking ***Test***, then ***Diagnose & Test***. You should see the *Connection File Server was tested successfully* confirmation message. Click ***Save*** and exit the Connection editor.

##	Task	2: Create a connection with HCM Cloud Adapter
Create a connection with the Oracle ERP Cloud Adapter.

1. In the left Navigation pane, click ***Design*** &gt; ***Connections*** &gt; click ***Create***
2. In the *Create Connection* dialog, select the ***Oracle HCM Cloud*** adapter to use for this connection. To find the adapter, enter `hcm` in the search field. Click on the highlighted adapter.
3. In the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**        | **Value**          |       
    | --- | ----------- |
    | Name         | `HCM Cloud`       |
    | Description  | `HCM Cloud Connection for OIC LiveLabs` |

    Keep all other values as default.

4. In the *Oracle HCM Cloud Connection* dialog, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |HCM Cloud Host | `your-hcm-host-name` |
    |Security Policy | **Username Password Token**|
    |Username | `fin_impl`|
    |Password | `<hcm-password>`|

5. Click on ***Test*** and wait until you receive a confirmation box that the test was successful.

6. Click ***Save*** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

You may now **proceed to the next lab**.

## Learn More


* [Using the FTP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/ftp-adapter/ftp-adapter-capabilities.html)
* [Using the Oracle HCM Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/hcm-adapter/index.html)

## Acknowledgements
* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Feb 2023
