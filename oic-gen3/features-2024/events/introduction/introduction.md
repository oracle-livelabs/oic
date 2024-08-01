# Introduction

## About this Workshop

You can create and select events for publishing and subscribing to in integrations in Projects in Oracle Integration. You define the events in JSON-formatted or XML schema files.
This LiveLab provides an overview of projects and the life cycle of projects.
This Livelab provides an overview of the event design life cycle and describes event restrictions.

Estimated Time: 60 minutes

### What is Oracle Integration 3?
With Oracle Integration 3 (OIC), you have the power to *integrate* your cloud and on-premises applications, *automate* business processes, *gain insight* into your business processes, visually *develop* web and mobile applications, use an SFTP-compliant file server to *store* and *retrieve* files, and *exchange* business documents with a B2B trading partner—all in one place.

[First Glimpse - Oracle Integration 3](youtube:yW3TEBWkFbg)

Oracle Integration 3 provides native connectivity to Oracle and non-Oracle Software as a Service (SaaS) and On-premises applications, such as FTP adapter, REST adapter, Oracle ERP Cloud, Oracle Service Cloud, HCM Cloud, Salesforce.com, Workday, EBS, SAP, NetSuite and so on. OIC adapters simplify connectivity by handling the underlying complexities of connecting to applications using industry-wide best practices

As an Integration Developer, if you have a requirement with publish-subscribe pattern then, you can use  this live lab as a reference

### Objectives

In this workshop, you will learn how to:

* Creating Free Trial Account
* Provision Oracle Integration 3 in Oracle Cloud Infrastructure.
* Learn project and events management in Oracle Integration 3.
* Create a project, create connection, create an event based integration flow and create an application integration flow to publish the message and create two event based integration flows as subscribers.

### Prerequisites

* An Oracle Free Tier or Paid Cloud Account.
* A Chrome browser.

## Event Design Life Cycle

The publish and subscribe feature enables you to decouple producers and subscribers. This decoupling enables you to define an event and start building your subscriber for the event before the event is published. You can create an event type (can be a producer, subscriber, or someone else). Creating an event type defines a contract, meaning that there's a contract to produce and subscribe.

The event design life cycle consists of three high-level steps. These steps are described using an event named Patient Moved as an example. References are provided to more specific documentation for performing these steps

1. Create an event
2. Create an event publishing integration
3. Create an event subscription integration

## Restrictions

A maximum of 50 integrations can subscribe to events per service instance.

You may now **proceed to the next lab**.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)

## Acknowledgements

* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, July 2024
