# Introduction

## About this Workshop

This workshop shows you how to design and develop a Real time Synchronization Usecase in Oracle Integration 3 integrating with the HCM cloud. Out of the box, The Oracle HCM Cloud Adapter enables you to create an integration with Oracle Human Capital Management (HCM) Cloud applications.
In this workshop, you would be experiencing ATOM Feeds feature which is available in the HCM cloud to extract the feeds and you would be leveraging HCM Cloud and FTP Adapters of Oracle Integration 3 to implement this usecase.
HCM Atom feeds provide notifications of Oracle Fusion Human Capital Management (HCM) events. When an event occurs in Oracle Fusion HCM, the corresponding Atom feed is delivered automatically to the Atom server. The feed contains details of the REST resource on which the event occurred. Subscribers who consume these Atom feeds use the REST resources to retrieve additional information about the resource.

Estimated Time: 2 hours

### What is Oracle Integration 3?
With Oracle Integration 3 (OIC), you have the power to *integrate* your cloud and on-premises applications, *automate* business processes, *gain insight* into your business processes, visually *develop* web and mobile applications, use an SFTP-compliant file server to *store* and *retrieve* files, and *exchange* business documents with a B2B trading partner—all in one place.

[First Glimpse - Oracle Integration 3](youtube:yW3TEBWkFbg)

### Objectives

In this workshop, you will learn how to:

* Provision Oracle Integration 3 in Oracle Cloud Infrastructure.
* Configure HCM Cloud Adapter.
* Configure FTP Adapter
* Create a Real-Time Synchronization scenario using ATOM feeds


### Prerequisites

* An Oracle Free Tier or Paid Cloud Account.
* A Chrome browser.

## Task 1: Leverage the HCM Cloud Adapter in Oracle Integration 3

Oracle Integration 3 provides native connectivity to Oracle and non-Oracle Software as a Service (SaaS) and On-premises applications, such as Oracle ERP Cloud, Oracle Service Cloud, Oracle HCM Cloud, Salesforce.com, Workday, EBS, SAP, NetSuite and so on. OIC adapters simplify connectivity by handling the underlying complexities of connecting to applications using industry-wide best practices

With the help of this cookbook series, you can design and implement HCM Cloud Integration patterns leveraging Oracle Integration 3 features and functionalities

As an Integration Developer, if you have a requirement to integrate an HCM Cloud application with any other SaaS or On-premise application, then this cookbook series helps you to go through the pre-requisite steps, common use cases, HCM Cloud adapter functional capabilities and several implementation considerations along with lab exercises to provide hands-on experience.

The Oracle HCM Cloud Adapter enables customers to easily integrate their on-premises or SaaS applications with Oracle HCM Cloud without having to know about the specific details involved in the integration

The Oracle HCM Cloud Adapter provides the following benefits:
- Integrates easily with the Oracle HCM Cloud application’s WSDL file to produce a simplified, integration-centric WSDL.
- Supports invoking of business objects using the HCM Data Loader, regardless of how they were created. The HCM Data Loader is a tool for bulk-loading and maintaining data. The data can be from any source. You use the HCM Data Loader for data migration, ongoing maintenance of Oracle HCM Cloud data, and coexistence scenarios where core HR data is uploaded regularly.
- Exposes the Business Resource (REST) API, which represents an Oracle Fusion Applications REST API resource.
- Supports consumption of the Oracle HCM Cloud REST API.
- Automatically handles security policy details required to connect to the Oracle HCM Cloud application
- Supports the following security policies for selection during Oracle HCM Cloud Adapter connection configuration:
    - Username Password Token With PGP Key Support
    - Username Password Token
    - OAuth Authorization Code Credentials
- Provides standard error handling capabilities.
- Supports subscribing to the HCM Atom feed.
- Enables you to upload files to Oracle WebCenter Content (Universal Content Manager) in encrypted or unencrypted format
- Supports HCM data extracts, a flexible tool for generating data files and reports. The Oracle HCM Cloud Adapter works as an extract discovering tool under Oracle HCM Cloud. The data extract process is automated as per the following steps:
    - Invoking the given HCM data extract by the client outside the Oracle HCM Cloud Adapter.
    - Discovering the extract as delivered in Oracle WebCenter Content.
    - Fetching the extract output in its format as it is delivered to Oracle WebCenter Content and persisting the extract to Oracle Integration staging.
    - Defining the XML schema by the user for the extract output for transformation using a stage file action that is available in an orchestrated integration.

###	Video Preview

* [HCM Cloud Integration Patterns](https://videohub.oracle.com/media/HCM%20Cloud%20Integration%20Patterns/1_43t43y77)
* [HCM Cloud Atom Feed Pattern](https://videohub.oracle.com/media/HCM%20Cloud%20Atom%20Feed%20Pattern/1_pe1llsce)

You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)
* [Using the Oracle HCM Cloud Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/hcm-adapter/index.html)

## Acknowledgements

* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Feb 2023
