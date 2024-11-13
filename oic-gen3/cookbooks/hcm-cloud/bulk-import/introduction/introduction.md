# Introduction

## About this Workshop

HCM customers who use different sources of recruiting new talent require an ability to import Pending Workers using data from multiple external systems. In this workshop we will explore how to use Oracle Integration 3 to pick up any structured data file containing new hires and how to generate the input file that can be loaded into HCM.

OIC 3 will trigger a scheduled integration to retrieve this file. Data from the file is imported into a structured schema. Using OIC 3 mapping capabilities the data is transformed into HCM Data Loader compatible file format with native schema definition and subsequently zipped, sent to UCM, and imported using HDL.

This lab walks you through the steps to create Integration flow.

The following diagram shows the interaction between the systems involved in this use case.
    ![Pending Worker Import](images/pending-worker-import.png)

Estimated Time: 60 minutes

### Objectives

In this workshop, you will learn how to:

* Configure HCM Cloud Adapter to import bulk data.
* Configure FTP Adapter to read XML file
* Transform XML data to Pending Workers DAT file


### Prerequisites

* An Oracle Free Tier or Paid Cloud Account Tenancy
* Oracle Integration Instance provisioned in OCI.
* Access to HCM Cloud Environment


You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)
* [Using the Oracle HCM Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/hcm-adapter/index.html)

## Acknowledgements

* **Author** - Kishore Katta, Product Management, Oracle Integration
* **Contributors** - Subhani Italapuram, Product Management, Oracle Integration
* **Last Updated By/Date** - Kishore Katta, November 2024
