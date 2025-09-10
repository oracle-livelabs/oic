# Introduction

## About this Workshop

This workshop demonstrates how to integrate Oracle Integration (OIC) with Oracle ERP Cloud to automate the creation of invoices using the ERP Cloud adapter. In real-world business scenarios, managing invoices efficiently is crucial for maintaining smooth financial operations. By leveraging OIC, organizations can streamline this process, reducing manual efforts and minimizing errors.

In this workshop, we will build an OIC integration flow that receives an invoice and lines data payload in JSON format. The integration flow will:

  - Validate the specified business unit to ensure it exists.
  - Verify the supplier's existence within the ERP system.
  - Check the validity of the supplier's site.

Once these validations are complete, the integration will invoke Oracle ERP Cloud's business services to create the invoice and associated line items. Upon successful completion, the system will return a status to the user, indicating whether the invoice was created successfully or if any errors occurred.

  The following diagram shows the runtime interaction between the systems involved in this use case:
  ![Create Invoice Architecture](../create-flow/images/create-invoice-architecture.png)

Estimated Time: 90 minutes

### Objectives

In this workshop, you will learn how to:

* Creating a Project
* Creating Connections
* Create a Real-Time Integration scenario using ERP Cloud Business Services.
* Use Business Object to Integrate with ERP Cloud.

### Prerequisites

* Oracle Integration Instance.
* Access to the ERP Cloud environment
* A Chrome browser.


You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)
* [Using the Oracle ERP Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/erp-adapter/index.html)

## Acknowledgements

* **Author** - Kishore Katta, Director Product Management, Oracle Integration
* **Contributors** - Subhani Italapuram, Director Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Sep 2025
