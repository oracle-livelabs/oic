# ERP Cloud Adapter Connection configuration

## Introduction

This lab walks you through the steps to create Integration flow.

This Lab explores the use of Oracle Integration to subscribe to Oracle ERP Cloud Events and
push the relevant event information to downstream systems. As part of the lab you will build the following use case scenario:

1.  You create and activate an integration that subscribes to an ERP Cloud Purchase Order (PO) event
2.  You then create a PO in ERP Cloud and a PO event is triggered.
3.  Your integration receives the PO event and pushes the data
    into the File Server.

    The following diagram shows the runtime interaction between the systems involved in this use case:
      ![POEvent](images/po-real-time-sync-1.png)

Estimated Time: 30 minutes

### Objectives

In this lab, you will:

* Understand how to subscribe to business events in Oracle ERP cloud leveraging out of the box ERP cloud
  adapter capabilities
* Connect to file server to write data records

### Prerequisites

This lab assumes you have:

* All previous labs successfully completed.

## Task 1: Configure File Server

Configure File Server settings. This is required as you are using Embedded File Server of Oracle Integration and using File Server as a target application in your integration flow.


You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud)
* [Using the Oracle ERP Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud/erp-adapter)

## Acknowledgements

* **Author** - Subhani Italapuram, Director Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Director Product Management, Oracle Integration
* **Last Updated By/Date** -
