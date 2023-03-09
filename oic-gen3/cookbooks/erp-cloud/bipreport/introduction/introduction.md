# Introduction

## About this Workshop

This workshop shows you how to use Oracle Integration 3 with Oracle ERP Business Intelligence Publish (BIP) report. Out of the box, SOAP adapter helps an Integration developer to quickly consume BIP Report in a secured way using various authentication schemes.

The user creates a report in Oracle ERP Cloud and uploads it to a shared folder. Oracle Integration 3 connects to the ERP BIP service, pulls the report, decodes the response, applies the required transformations and writes it into the REST client.

Estimated Time: 1 hour 20 minutes

### What is Oracle Integration 3?
With Oracle Integration 3 (OIC), you have the power to *integrate* your cloud and on-premises applications, *automate* business processes, *gain insight* into your business processes, visually *develop* web and mobile applications, use an SFTP-compliant file server to *store* and *retrieve* files, and *exchange* business documents with a B2B trading partner—all in one place.

[First Glimse - Oracle Integration 3](youtube:yW3TEBWkFbg)

Oracle Integration 3 provides native connectivity to Oracle and non-Oracle Software as a Service (SaaS) and On-premises applications, such as Oracle ERP Cloud, Oracle Service Cloud, HCM Cloud, Salesforce.com, Workday, EBS, SAP, NetSuite and so on. OIC adapters simplify connectivity by handling the underlying complexities of connecting to applications using industry-wide best practices

With the help of this cookbook series, you can design and implement ERP Cloud Integration patterns leveraging Oracle Integration 3 features and functionalities

As an Integration Developer, if you have a requirement to integrate an ERP Cloud application with any other SaaS or On-premise application, then this cookbook series helps you to go through the pre-requisite steps, common use cases, ERP Cloud adapter functional capabilities and several implementation considerations along with lab exercises to provide hands-on experience.

The Oracle ERP Cloud Adapter enables you to easily integrate on-premises or SaaS applications with Oracle ERP Cloud without having to know about the specific details involved in the integration.

The Oracle ERP Cloud Adapter provides the following key benefits:
- Provides declarative support for subscribing to business events raised by various modules in Oracle ERP Cloud and Oracle Supply Chain Management Cloud.
- Integrates easily with the Oracle ERP Cloud application’s WSDL file to produce a simplified, integration-centric WSDL.
- Generates automatic mapping to the selected business object, event subscription, or business (REST) API.
- Simplifies connection creation by automatically identifying the required service resources based on the Oracle ERP Cloud hostname you specify when creating a new connection on the **Connections** page.
- Supports several security policies for selection during Oracle ERP Cloud Adapter connection configuration:
    - Username Password Token With PGP Key Support
    - Username Password Token
    - OAuth Authorization Code Credentials
- Provides standard error handling capabilities.
- Enables you to upload a file in the Oracle ERP Cloud business tables.
- Enables you to upload files to Oracle WebCenter Content (Universal Content Manager) in encrypted or unencrypted format.

###	Video Preview

[ERP Cloud Integration Patterns](youtube:nKXbh2ZPuMI)

### Objectives

In this workshop, you will learn how to:

* Creating Free Trial Account
* Provision Oracle Integration 3 in Oracle Cloud Infrastructure.
* Create and configure common connections which are useful for this workshop like REST Interface and ERP Cloud External Report Service Connection
* Learn ERP Cloud Integration Design Patterns and Usecases.
* Create an Integration flow to make a call to extract the data from ERP Cloud Oracle Business Intelligence Publisher (BIP) and gets the response back.

### Prerequisites

* An Oracle Free Tier or Paid Cloud Account.
* A Chrome browser.
* This workshop assumes that you have a report created in the Oracle ERP Cloud and uploaded it to a shared folder.


You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/integration-cloud)

## Acknowledgements

* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Jan 2023
