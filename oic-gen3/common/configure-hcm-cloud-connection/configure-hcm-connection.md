# HCM Cloud Connection

## Introduction

This lab walks you through the steps to configure the ERP Cloud Adapter connection.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:

* Understand different authentication schemes supported by HCM Cloud Adapter

### Prerequisites

This lab assumes you have:

* All previous labs successfully completed.

##	Task	1: Create HCM Cloud Adapter Connection
Create a connection with the Oracle ERP Cloud Adapter.

1. Show the left Navigation menu, and click ***Design*** &gt; ***Connections***.
2. Click ***Create***.
3. In the *Create Connection* dialog, select the ***Oracle HCM Cloud*** adapter to use for this connection. To find the adapter, enter `hcm` in the search field. Click on the highlighted adapter.
4. In the *Create Connection* dialog, enter the following information and click on ***Create***:

    | **Field**        | **Value**          |       
    | --- | ----------- |
    | Name         | `HCM Cloud`       |
    | Description  | `HCM Cloud Connection for OIC LiveLabs` |

    Keep all other values as default.

5. In the *Oracle HCM Cloud Connection* dialog, enter the following information:

    | **Field**  | **Values** |
    |---|---|
    |HCM Cloud Host | `your-hcm-host-name` |
    |Security Policy | **Username Password Token**|
    |Username | `<hcm-username>`|
    |Password | `<hcm-password>`|


6. Click on ***Test*** and wait until you receive a
confirmation box that the test was successful.

    > **Note:** The first time you run the test, it could take up to 2 minutes for completion.

7. Click ***Save*** and wait for the confirmation box. Exit the connection canvas by clicking the back button on the top left side of the screen.

You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)
* [Using the Oracle HCM Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/hcm-adapter/understand-oracle-hcm-cloud-adapter.html)


## Acknowledgements

* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Feb 2023
