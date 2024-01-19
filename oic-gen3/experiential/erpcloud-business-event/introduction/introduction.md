# Introduction

## About this Workshop
The ERP Cloud Business Events Workshop will cover the recommended steps to complete an end-to-end use case based on ERP Cloud Business Events in Oracle Integration 3. This workshop will leverage the Oracle ERP Cloud Adapter, which enables you to create an integration with Oracle Enterprise Resource Planning (ERP) applications. One of the key differentiators of this adapter is support for subscribing to business events raised by various modules in Oracle ERP Cloud and Oracle Supply Chain Cloud.

This workshop will showcase the event subscription capabilities to create an App Driven i.e., real-time integration, with updates in ERP Cloud sent immediately to the Oracle Autonomous Database. The steps outlined in this workshop can be used to demo the event-driven capabilities of the ERP Cloud adapter in Oracle Integration 3.

Estimated workshop time: 2 hours

### What is Oracle Integration 3
With Oracle Integration 3 (OIC), you have the power to *integrate* your cloud and on-premises applications, *automate* business processes, *gain insight* into your business processes, *develop* visual applications, use an SFTP-compliant file server to *store* and *retrieve* files, and *exchange* business documents with a B2B trading partner—all in one place.

[First Glimpse - Oracle Integration 3](youtube:yW3TEBWkFbg)


### Objectives
In this workshop, you will learn the following:
- Create Connections and Integrations in OIC
- Capture ERP Purchase Order events and orchestrate the data to a target database table

### Prerequisites
This lab assumes you have the following:
- Oracle Cloud Account with credits to provision services.
- Oracle ERP Cloud access


## Leveraging the ERP Adapter in Oracle Integration 3
The Oracle ERP Cloud Adapter enables you to easily integrate on-premises or SaaS applications with Oracle ERP Cloud without having to know about the specific details involved in the integration.

The Oracle ERP Cloud Adapter provides the following key benefits:
- Provides declarative support for subscribing to business events raised by various modules in Oracle ERP Cloud and Oracle Supply Chain Management Cloud.
- Integrates easily with the Oracle ERP Cloud application’s WSDL file to produce a simplified, integration-centric WSDL.
- Generates automatic mapping to the selected business object, event subscription, or business (REST) API.
- Simplifies connection creation by automatically identifying the required service resources based on the Oracle ERP Cloud host name you specify when creating a new connection on the **Connections** page.
- Supports several security policies for selection during Oracle ERP Cloud Adapter connection configuration:
    - Username Password Token With PGP Key Support
    - Username Password Token
    - OAuth Authorization Code Credentials
- Provides standard error handling capabilities.
- Enables you to upload a file in the Oracle ERP Cloud business tables.
- Enables you to upload files to Oracle WebCenter Content (Universal Content Manager) in encrypted or unencrypted format.

## Leveraging the Oracle Autonomous Data Warehouse (ADW) adapter in Oracle Integration 3
The Oracle Autonomous Data Warehouse Adapter enables you to integrate the Oracle Autonomous Data Warehouse database with Oracle Integration through use of direct connectivity. Use the Oracle Autonomous Data Warehouse Adapter to execute SQL queries or stored procedures in the Oracle database.
The Oracle Autonomous Data Warehouse Adapter provides the following benefits:
- Support for using direct connectivity to connect to the Oracle Autonomous Data Warehouse database in place of using the on-premises connectivity agent.
- Support for the bulk data import operation
- Support for invocation of stored procedures in the Oracle database.
- Support for updating or inserting multiple records in a single request.


You may now **proceed to the next lab**.

## Want to Learn More?
* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)
* [Using the Oracle ERP Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/erp-adapter/oracle-erp-cloud-adapter-capabilities.html)
* [Using the Oracle ADW Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/adw-adapter/oracle-autonomous-data-warehouse-adapter-capabilities.html#GUID-5561EE1B-D13F-4BA5-913A-C07D11B1207E)


## Acknowledgements
* **Author** - Ravi Chablani, Product Management - Oracle Integration
* **Author** - Subhani Italapuram, Product Management - Oracle Integration
* **Last Updated By/Date** - Ravi Chablani, Jan 2024
