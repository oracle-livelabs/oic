# Get Started

## Introduction

To use OPA with certain Fusion-based cloud applications, you will need to create specific users in Oracle Identity Cloud Service (IDCS). For this workshop, we intend to use OPA with Oracle HCM Cloud, you must create the "FA HCM Journey Admin" user in IDCS to discover the processes in Journeys Integration. This lab provides instructions on how to create the necessary user in IDCS.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:
* Create a FA HCM Journey Admin user which must be in IDCS only, and should not exist in FA

### Prerequisites

Access to an OCI Process Automation instance in conjunction with a subscription to a Fusion-based Oracle Cloud Applications service

## Task 1: Create a required User in IDCS

To create the required user FA HCM Journey Admin in IDCS for Oracle HCM Cloud:

1.  As the Cloud Account Administrator, sign in to IDCS.

2.  In the IDCS navigation pane, click **Users**.

3.  On the Users page, click **Add**.

4.  In the Add Users dialog, add the FA HCM Journey Admin user, as follows:
    - First Name: FA HCM
    - Last Name: Journey Admin
    - User Name: fa\_hcm\_journey\_admin
    - Email: An email address where this user can receive email notifications

![IDCS Add User](images/idcs-add-user.png)

You may now **proceed to the next lab**.

## Learn More

* [OCI Process Automation](https://docs.oracle.com/en/cloud/paas/process-automation/index.html)
* [Use OCI Process Automation with Fusion Based Oracle Cloud Applications](https://docs.oracle.com/en/cloud/paas/process-automation/user-process-automation/process-automation-product-types.html)

## Acknowledgements

* **Author** - Kishore Katta, Product Management, Oracle Integration & OCI Process Automation
* **Last Updated By/Date** - Kishore Katta, October 2023
