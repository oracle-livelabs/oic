# ERP Cloud Extracts

## Introduction

This lab walks you through the steps to create Integration flow.

This use case explores the use of Oracle Integration to extract data from Oracle Business Intelligence Publisher (BIP).

This use case includes the following steps:

* Get the most recent list of approved invoices.
* Extract the most recent payment data and update other applications to reflect new payments.
* Deliver the report to UCM or SFTP or trigger a report using ERP integration service

The data file can be larger than 10MB. Oracle Integration supports handling large files as an attachment (instead of base64 encoding). We recommend that you use CSV format to reduce the size of the file.

See this blog article to learn how to handle files from various interfaces and file size constraints.

 The following diagram shows the interaction between the systems involved in this use case.
  ![FBDIImport](images/bulk-export-callback.png)

Estimated Time: 60 minutes

### Objectives

In this lab, you will:

* Connect to ERP Cloud to extract the bulk data
* Understand how to bulk export the data from the Oracle ERP cloud leveraging out of the box ERP cloud
  adapter capabilities


### Prerequisites

This lab assumes you have:

* All previous labs successfully completed.

##	Task	1: Create ERP Cloud callback Connection using SOAP adapter
Create a connection with the SOAP Adapter.

1. [Download the erpcbkinterface-onjobcompletion.wsdl](files/erpcbkinterface-onjobcompletion.wsdl?download=1)
2. In the left Navigation pane of OIC, Click ***Design*** > ***Connections*** and Click ***Create***.
3. In the *Create Connection* dialog, select the ***SOAP*** adapter. To find the adapter, enter `SOAP` in the search field. Click on the highlighted adapter.
4. In the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**        | **Value**          |       
    | --- | ----------- |
    | Name         | `ERP Cloud Callback`       |
    | Description  | `ERP Cloud Callback Connection for OIC LiveLabs` |


    Keep all other values as default.

5. In the *Configuration* page, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |WSDL URL | upload ***the erpcbkinterface-onjobcompletion.wsdl*** |
    |Security Policy | select ***Security Assertion Markup Language(SAMPL)***|
    |

![Create ERP Cloud Callback configuration](images/create-erpcallback-configuration.png)

6. Click on ***Test***  and click on ***Validate and Test***  and wait until you receive a
confirmation box that the test was successful.

    > **Note:** The first time you run the test, it could take up to 2 minutes for completion.

7. Click ***Save*** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

##	Task	2: Create ERP Cloud Integration Service Connection using SOAP adapter
Create a connection with the SOAP Adapter.
1. In the left Navigation pane of OIC, Click ***Design*** > ***Connections*** and Click ***Create***.
2. In the *Create Connection* dialog, select the ***SOAP*** adapter. To find the adapter, enter `SOAP` in the search field. Click on the highlighted adapter.
3. In the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**        | **Value**          |       
    | --- | ----------- |
    | Name         | `ERP Cloud Integration Service`       |
    | Description  | `ERP Cloud Integration Service Connection for OIC LiveLabs` |


    Keep all other values as default.

4. In the *Configuration* page, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |WSDL URL | enter ***https://ERPCloudHost/fscmService/ErpIntegrationService?wsdl*** |
    |Security Policy | select ***Username Password Token*** |
    |Username | Enter ***Enter ERP Cloud username received from the instructor*** |
    |Username | Enter ***Enter ERP Cloud password received from the instructor*** |

5. Click on ***Test***  and click on ***Validate and Test***  and wait until you receive a
confirmation box that the test was successful.
6. Click ***Save*** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

## Task 3: Create the ERP Bulk Extract Integration

1. In the left Navigation pane, click ***Design*** > ***Integrations***.
2. On the **Integrations page**, click ***Create***.
3. On the **Integration Style** dialog, select ***Scheduled Orchestration***, followed by ***Create***
![Select Integration Style](images/select-integration-style-1.png =40%x*)
4. In the **Create New Integration** dialog, enter the following information:

    | **Element**          | **Value**          |       
    | --- | ----------- |
    | Name         |```
    <copy>ERP Bulk Extract</copy
    ```
    |
    | Description |```
    <copy>This integration starts the extraction of payable transactions in the ERP Cloud</copy
    ```
    |

Accept all other default values.

5. Click ***Create***.
6. Click on Horizontal to change the layout to Horizontal
![Select Horizontal Layout](images/horizontallayout.png =30%x*)

## Task 4: Create the Initiate Extract Activity

1. Click the ***+*** sign after **Schedule** in the integration canvas.

2. Select the **ERP Cloud** connection which you have created in the previous labs. This invokes the ERP Cloud Configuration Wizard.

3. On the **Basic Info** page,
     - for the **What do you want to call your endpoint?** element, enter ***InitiateExtract***
     - for the **What does this endpoint do?** element, enter ***This endpoint starts the extraction of payable transactions***
     - Click ***> (Next Step)***.
4. From the **Actions** page,
    - select ***Query, Create, Update or Delete Information*** option
    - Click ***> (Next Step)***.
4. From the **Operations** page,
    - select ***Services*** from the **Browse by** list
    - In the **Select a Service** field, enter ***ERPIntegrationService*** and select it from the list
    - If required, scroll down the page(not the previous component), from **Select the Operation to perform on the Business Service** list, select ***Export Bulk Data***
    - Click ***> (Next Step)***.
6. Review the summary and click ***Done***.
7. Click ***Save*** to persist changes.
![InitiateExtract](images/initiateextract.png)

## Task 5: Define the data Mapping
A map action named InitiateExtract is automatically created. We will define this data mapping.
1. Select the action **Map InitiateExtract** and click on **...** and click on **Edit**
2. In the Target section, expand the ***InitiateExtract Request*** element.
    - Right click on **Job Name** and then click on ***Create Target Node***
![InitiateExtractMapping1](images/InitiateExtractMapping1.png)
    - Click on ***Switch to Developer View*** which is there on bottom right corner. (Note: If it is already in Developer View then no need to click on this icon. If you find expression editor in the edit mode which means you are in Developer view)
![mappingsdeveloperview](images/mappingsdeveloperview.png)   
    - Enter the value given below
    ```
    <copy>"oracle/apps/ess/financials/commonModules/shared/common/outbound,FinOutboundProcess"</copy
    ```
    - Click on Save
    ![saveliteral](images/saveliteral.png)  

    - Right click on **Parameter List** and then click on ***Create Target Node*** and enter the value given below.
    ```
    <copy>"92,/oracle/apps/ess/financials/commonModules/shared/common/outbound;PayablesTransactionsExtract,BIPREPORT,FULL_EXTRACT,#NULL,300000046987012,#NULL,#NULL,#NULL,#NULL,#NULL,12-19,N,N,300000046975971,#NULL,#NULL,#NULL,FULL_EXTRACT,#NULL,#NULL,#NULL,PayablesTransactionsExtract,#NULL"</copy
    ```
    - Right click on **Job Options** and then click on ***Create Target Node*** and enter the value given below.
    ```
    <copy>"ExtractFileType=ALL"</copy
    ```
    - For **Callback URL**, skip this mapping for now. We will assign a value after we design and activate the callback flow
    - Right click on **Notification Code** and then click on ***Create Target Node*** and enter the value given below.
    ```
    <copy>30</copy
    ```
![initiateextractMapping](images/initiateextractMapping.png)
7. Click on ***Validate***
A confirmation message appears.
8. Click ***< (Go back)***
9. Click ***Save*** to persist changes.

## Task 6: Define Tracking Fields
Manage business identifiers that enable you to track fields in messages during runtime.

> **Note:** If you have not yet configured at least one business identifier **Tracking Field** in your integration, then an error icon is displayed in the design canvas.
    ![Error Icon in Design Canvas](images/error-icon.png =10%x*)

1. Click on the ***(I) Business Identifiers*** menu on the top right.
    ![Open Business Identifiers For Tracking](images/open-business-identifiers.png =20%x*)

2. From the **Source** section, expand ***schedule*** > ***startTime***. Drag the ***startTime*** field to the right side section:

    ![Assign Business Identifiers](images/assign-business-identifiers.png =40%x*)

3. Click on the ***(I) Business Identifiers*** menu on the top right again to close Business Identifier section and Click ***Save*** and Click on ***< (Go back)*** button.

## Task 7: Create the ERP Bulk Extract Callback Integration

1. In the left Navigation pane, click ***Design*** > ***Integrations***.
2. On the **Integrations page**, click ***Create***.
3. On the **Integration Style** dialog, select ***App Driven Orchestration***, followed by ***Create***
4. In the **Create New Integration** dialog, enter the following information:

    | **Element**          | **Value**          |       
    | --- | ----------- |
    | Name         |```
    <copy>ERP Bulk Extract Callback</copy
    ```
    |
    | Description |```
    <copy>This integration is triggered when it receives a callback from the ERP Bulk Extract integration. When it receives the callback, it downloads the extract, and uploads it to an FTP server</copy
    ```
    |

Accept all other default values.

5. Click ***Create***.
6. Click on Horizontal to change the layout to Horizontal

## Task 8: Create the ERP Cloud Callback Trigger

1. Search for the **ERP Cloud Callback** connection which you have created in the previous Task and click on it. This invokes the SOAP Adapter Configuration Wizard.

2. On the **Basic Info** page,
     - for the **What do you want to call your endpoint?** element, enter ***BulkExtractCallback***
     - for the **What does this endpoint do?** element, enter ***This endpoint defines an ERP Cloud callback.***
     - Click ***> (Next Step)***.
3. From the **Operations** page,
    - select ***onJobCompletion*** from the **Selected Operation**
    - Click ***> (Next Step)***.
4. From the **Callback Operations** page,
    - select ***No Response*** (It is a Default option. If not, select No Response)
    - Click ***> (Next Step)***.
5. From the **Headers** page, keep defaults and Click ***> (Next Step)***
6. Review the summary and click ***Done***.
7. Click ***Save*** to persist changes.
![callback trigger](images/callbacktrigger.png)

## Task 9: Create the Download Activity
1. Hover over the outgoing arrow for the **BulkExtractCallback** activity and click ***+*** icon.
2. In the Search field, begin typing **ERP Cloud Integration Service** to find your connection and Click on it.
The Configure SOAP Endpoint wizard appears.
3. On the **Basic Info** page,
     - for the **What do you want to call your endpoint?** element, enter ***DownloadFile***
     - Click ***> (Next Step)***.
4. From the **Operations** page,
    - select ***getDocumentsForFilePrefix*** from the **Operation** list
    - Click ***> (Next Step)***.
Note: Be careful to select the correct operation as many of them have similiar names.    
5. From the **Headers** page,
    - select ***Accept attachments in response***
    - Click ***> (Next Step)***.
Note: The SOAP adapter allows rich capability to accept content as an attachment, instead of base64-encoded data.
If you don't see this option, it is likely you selected the wrong operation. Click Back and verify you have the correct operation.
6. Review the summary and click ***Done***.
7. Click ***Save*** to persist changes.
![Download File](images/downloadfile.png)

## Task 10: Define the Data mapping for Download Activity
A map action named DownloadFile is automatically created. We will define this data mapping.
1. Select the action **Map DownloadFile** and click on **...** and click on **Edit**
2. In the Target section, expand the **DownloadFile Request**, expand **Body** and expand **getDocumentsForFilePrefix**.
    - Click the **Toggle functions** button located above the Target section toolbar
    - In the Component palette, expand the **String** node.
    - Drag the concat function and drop it on **prefix** element in the Target section.
![Toggle File](images/togglefunctions.png)

In the Expression window, edit the concat function to use the following parameters:

    - "ESS_"
    - //requestId
    - "_BIPReport0"

The complete expression should read: concat ( ***"ESS__", //requestId, "_BIPReport0"*** )
    - Click **Save** icon in the Expression editor to commit the expression

![prefix element](images/prefixelement.png)

3. Map the **account** element to the following expression: ***"fin$/payables$/export$"***
    - Right-mouse click on the **account** node and select **Create Target Node**.
    - Click Edit icon in the Expression editor to enable edit mode.
    - Enter the literal value ***"fin$/payables$/export$"***
    - Click **Save** icon in the Expression editor to commit the data.

4. In the same way, map the **comments** element to the following expression:

    - ***concat ( "processedby=", //requestId )***

5. Click on ***Validate***
    - A confirmation message appears.
6. Click ***< (Go back)***
7. Click ***Save*** to persist changes.


## Task 11: Create the Write Extract Activity
1. Hover over the outgoing arrow for the **DownloadFile** activity and click **+** icon.
2. In the Search field, begin typing **File Server** to find your connection
3. Select the connection named File Server.
The Configure Oracle Adapter Endpoint Configuration Wizard appears.
4. On the **Basic Info** page,
     - for the **What do you want to call your endpoint?** element, enter ***WriteExtract***
     - Click ***> (Next Step)***.
5. From the **Operations** page,
    - select ***Write File*** from the **Select Operation** list
    - Enter ***/home/users/```<<your oic usernumber>>```*** in the **Output Directory** field
    - Enter ***PayablesExtract.xml*** in the **File Name Pattern** field
    - Click ***> (Next Step)***.  
6. From the **Schema** page,
    - select ***No*** to the **Do you want to specify the structure for the contents of the file?**
    - Click ***> (Next Step)***.
7. Review the summary and click ***Done***.
8. Click ***Save*** to persist changes.
![writeextract2ftp](images/writeextract2ftp.png)

## Task 12: Define the Data mapping for WriteExtract

A map action named WriteExtract is automatically created. We will define this data mapping.
1. Select the action **Map WriteExtract** and click on **...** and click on **Edit**
2. In the Source section, expand **DownloadFile Response**, then expand the **getDocumentsForFilePrefixResponse**, and then expand **result**.
3. In the Target section, expand the **WriteExtract Request**, expand **ICSFile**.
4. Map the **Content** element in the Source section to the **FileReference** element in the Target section.
5. Click on ***Validate***
    - A confirmation message appears.
6. Click ***< (Go back)***
7. Click ***Save*** to persist changes.


## Task 13: Define Tracking Fields

Manage business identifiers that enable you to track fields in messages during runtime.

1. Click on the ***(I) Business Identifiers*** menu on the top right.
2. From the **Source** section, expand ***onJobCompletion*** > ***requestId***. Drag the ***requestId*** field to the right side section:
3. Click on the ***(I) Business Identifiers*** menu on the top right again to close Business Identifier section
4. Click ***Save***
5. Click on ***< (Go back)*** button.

## Task 14: Activate the ERP Bulk Extract Callback Integration
1. On the **Integrations** page, click on the ***Activate*** icon of **ERP Bulk Extract Callback** Integration.
2. On the **Activate Integration** dialog, select ***a tracing level***.
![tracinglevel](images/tracinglevel.png)
3. Click ***Activate***.

    The activation will be complete in a few seconds. If activation is successful, a status message is displayed in the banner at the top of the page, and the status of the integration changes to **Active**.

Note: Wait for few seconds and refresh the screen and make sure that your integration is in Active mode.

4. Click on **...(Actions)** menu of the **ERP Bulk Extract Callback** integration (Refresh the page if required)
![integrationactionsmenu](images/integrationactionsmenu.png)
5. Click on ***Run details***
6. Copy **Metadata URL** and save it in some text file.

## Task 15: Map the Callback URL in ERP Bulk Extract Integration.
1. In the left Navigation pane, click ***Design*** > ***Integrations***.
2. On the **Integrations page**, click ***ERP Bulk Extract*** to edit the integration.
3. Select the action **Map InitiateExtract** and click on **...** and click on **Edit**
2. In the Target section successively expand the ***InitiateExtract Request*** element.
    - Right click on **Callback URL** and then click on ***Create Target Node***
    - Click on ***Switch to Developer View*** which is there on bottom right corner. (Note: If it is already in Developer View then no need to click on this icon)
    - Enter the Metadata URL which you have copied.
    - Remove ***?wsdl*** and add ***/*** at the end along with the double quotes as per the image given below.
    - Click on Save
    ![callbackURL](images/callbackurl.png)
    7. Click on ***Validate***
    A confirmation message appears.
    8. Click ***< (Go back)***
    9. Click ***Save*** to persist changes.
    10. Click ***< (Go back)***

## Task 16: Activate the ERP Bulk Extract Integration

1. On the **Integrations** page, click on the ***Activate*** icon.
    ![Click to Activate Integration](images/click-activate-integration.png)
2. On the **Activate Integration** dialog, select **a tracing level** as ***Audit***.
3. Click ***Activate***.

    The activation will be complete in a few seconds. If activation is successful, a status message is displayed in the banner at the top of the page, and the status of the integration changes to **Active**.

## Task 17: Run the ERP Bulk Extract Integration

Refresh your page after few seconds.
1. Select **ERP Bulk Extract**,  Click on **...(Actions)** menu and Click on ***Run***
    ![Run Integration](images/run-integration.png)
2. Click on ***Run***
3. Click the link which appears on top to track the instance.
The track instance page appears. The Integration state should be processing or successful.
OR you can also track by clicking on ***Home***, ***Observability*** and ***Instances***
4. Make sure that both the integrations **ERP Bulk Extract** and **Bulk Extract Callback** completed successfully. If not, fix the issues.


## Task 18: Verify
Wait 5 minutes before performing this procedure.
1. Open a browser to sign in to the ERP Cloud using the information provided to you.
2. Click on Navigator Menu(On top lift corner), select Tools tab, click Scheduled Processes.
3. Expand Search and search for the Process Id returned from your integration.
4. Click the process to open and verify that the Payables transaction job completed successfully.
5. Using an FTP client of your choice, log in to the File server
6. Open the FTP directory which you have mentioned in the Callback integration flow and verify the PayablesExtract.xml file exits.
7. Download the PayablesExtract.xml file and review.
8. Congratulations! You have finished your integration flow.


You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud)
* [Using the Oracle ERP Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud/erp-adapter)

## Acknowledgements

* **Author** - Subhani Italapuram, Director Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Director Product Management, Oracle Integration
* **Last Updated By/Date** -
