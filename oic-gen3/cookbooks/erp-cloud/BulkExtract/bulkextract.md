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

Estimated Time: 30 minutes

### Objectives

In this lab, you will:

* Connect to ERP Cloud to extract the bulk data
* Understand how to bulk export the data from the Oracle ERP cloud leveraging out of the box ERP cloud
  adapter capabilities


### Prerequisites

This lab assumes you have:

* All previous labs successfully completed.


## Task 1: Create the ERP Bulk Extract Integration

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

## Task 4: Create the Initiate Extract Activity

1. Click the ***+*** sign after **Schedule** in the integration canvas.

2. Select the FTP File Server which you have created in the previous labs. This invokes the FTP Adapter Configuration Wizard.

3. On the Basic Info page,
     - for the **What do you want to call your endpoint?** element, enter ***ReadAPInvoicesFileFromFTP***
     - for the **What does this endpoint do?** element, enter ***Retrieves the AP Invoices that comply with FBDI from an FTP location.***
     - Click ***> (Next Step)***.
4. From the **Operations** page,
    - select ***Read a File*** as an Operation
    - from the **Select a Transfer Mode** option, select ***ASCII***
    - Enter the following values and Click ***> (Next Step)***.

| **Element**        | **Value**   |
| --- | ----------- |
| Input Directory         | /upload/public_ftp/```<<your oic usernumber>>```       
| File Name | apinvoiceimport.zip |

5. On the **Schema** page,
    - in the **Do you want to specify the structure for the contents of the file** section, select No.
    - Click ***> (Next Step)***.
6. Review the summary and click ***Done***.
7. Click ***Save*** to persist changes.
![ReadFileFromFTP](images/readFileFromFTP.png)

## Task 5: Upload the file to ERP Cloud
1. Hover over the outgoing arrow for ReadAPInvoicesFileFromFTP and click + icon.
2. Begin typing ERP in the Search field to find the connection to your ERP Cloud.
3. Select the connection which you have created in the previous labs.
The Configure Oracle ERP Cloud Endpoint wizard appears.
4. On the Basic Info page,
    - In the **What do you want to call your endpoint?** field, enter ***ImportAPInvoicestoERPCloud***
    - In the **What does this endpoint do?** field, enter: ***Uploads files to UCM in ERP Cloud***
    - Click ***> (Next Step)***.
5. On the Actions page,
    - select ***Import Bulk Data into Oracle ERP Cloud***
    - Click ***> (Next Step)***.
6. On the Operations page,
    - select ***Import Payables Invoices*** (Search for it)
    - Click ***> (Next Step)***.
7. On the Response page, select the following options:
    - From the **Notification Mode** list, select ***Email & Bell Notification***
    - From the **Occurrence** list, select ***Send in any case***.
    - Click ***> (Next Step)***.
8. Review the summary and click ***Done***.
9. Click ***Save*** to persist changes.
![UploadFiletoERP](images/uploadFileToERP.png)

## Task 6: Define the data Mapping
A map action named ImportAPInvoicestoERPCloud is automatically created. We will define this data mapping.
1. Select the action **Map ImportAPInvoicestoERPCloud** and click on **...** and click on **Edit**
2. In the Sources section successively expand the following elements:

  a. ReadAPInvoicesFileFromFTP Response (FTP)

  b. Sync Read File Response

  c. File Read Response

  d. ICS File

3. In the Target section successively expand the following elements:

  a. Import Bulk Data

  b. ICS File

4. Drag the File Reference element From the Sources section, and drop it on the element of the same name in the Target section.
5. In the Sources and Target sections expand Properties located under ICS File.
6. Drag the following elements from the Sources and drop them on the element of the same name in the Target section:

   a. directory

   b. filename

![DataMapping](images/dataMapping.png)
7. Click on ***Validate***
A confirmation message appears.
8. Click ***< (Go back)***
9. Click ***Save*** to persist changes.

## Task 7: Define Tracking Fields
Manage business identifiers that enable you to track fields in messages during runtime.

> **Note:** If you have not yet configured at least one business identifier **Tracking Field** in your integration, then an error icon is displayed in the design canvas.
    ![Error Icon in Design Canvas](images/error-icon.png)

1. Click on the ***(I) Business Identifiers*** menu on the top right.
    ![Open Business Identifiers For Tracking](images/open-business-identifiers.png =20%x*)

2. From the **Source** section, expand ***schedule*** > ***startTime***. Drag the ***startTime*** field to the right side section:

    ![Assign Business Identifiers](images/assign-business-identifiers.png =40%x*)


3. Click on the ***(I) Business Identifiers*** menu on the top right again to close Business Identifier section and Click ***Save*** and Click on ***< (Go back)*** button.

## Task 8: Activate the integration

1. On the **Integrations** page, click on the ***Activate*** icon.

    ![Click to Activate Integration](images/click-activate-integration.png)

2. On the **Activate Integration** dialog, select ***Enable Tracing***, followed by ***Include Payload*** options.

3. Click ***Activate***.

    The activation will be complete in a few seconds. If activation is successful, a status message is displayed in the banner at the top of the page, and the status of the integration changes to **Active**.
## Task 9: Run the integration
Refresh your page after few seconds.
1. Click on ***Run***
    ![Run Integration](images/run-integration.png)
2. Click on ***Submit Now*** and then click on ***Submit Now*** again when prompted.
3. Click the link which appears on top to track the instance.
The track instance page appears. The Integration state should be processing or successful.
Importing of the invoices to the ERP Cloud might take few minutes.
OR you can also track by clicking on ***Design***, ***Observability*** and ***Instances***
## Task 10: Verify the Bulk Import
Wait 5 minutes before performing this procedure.
1. Open a browser to sign in to the ERP Cloud using the information provided to you.
2. Click on Navigator Menu(On top lift corner), Click on Payables, click Invoices and Click on the search in the Details panel located below the User menu.
3. Enter the invoice number and click search.
The invoice should appear in the search results.
4. Congratulations! You have finished your integration flow.






You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud)
* [Using the Oracle ERP Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud/erp-adapter)

## Acknowledgements

* **Author** - Subhani Italapuram, Director Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Director Product Management, Oracle Integration
* **Last Updated By/Date** -
