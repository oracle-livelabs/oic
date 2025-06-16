# Enable Process Automation with OIC 3

## Introduction

This lab walks you through the process of enabling Process Automation with Oracle Integration, assuming you don't already have one enabled. If you do, you can skip this lab and move on to the next one.

To use Decisions with Oracle Integration, an administrator needs to enable Process Automation from an Oracle Integration service instance in the Oracle Cloud Infrastructure (OCI) Console.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:
* Enable Process Automation Instance

### Prerequisites

* All the previous labs completed successfully.

###	Background

Key points about enabling Process Automation with Oracle Integration:

-	You can enable Process Automation only with Oracle Integration 3 Enterprise Edition.

-	You must ensure that the user who enables Process Automation with Oracle Integration must exist in the identity domain of the Oracle Integration instance and must have MANAGE permissions on Process Automation.

-	You must ensure that you've set up the correct IAM policies to manage access to the Process Automation instance.

## Task 1: Set Up IAM Policies to Manage Process Automation Instance

To enable Process Automation with Oracle Integration, you need to create Oracle Cloud Infrastructure Identity and Access Management (IAM) policies that allow Oracle Integration administrators belonging to a specified IAM group to manage the Process Automation instance.

Set up the following IAM policies for Process Automation:

-	Syntax: allow group <group\_name> to manage process-automation-instances in compartment <compartment\_name>

Example: allow group domain\_admins to manage process-automation-instances in compartment oicpa\_compartment

-	Syntax: allow group <group\_name> to read metrics in compartment <compartment\_name>

Example: allow group domain\_admins to read metrics in compartment oicpa\_compartment

See [About IAM Policies for Process Automation](https://docs.oracle.com/en/cloud/paas/process-automation/admin-process-automation/iam-policies-process-automation.html#GUID-CE5FFEB8-DC37-4ABE-BB98-A14B633C6CAF) and [Create an IAM Policy in an Identity Domain.](https://docs.oracle.com/en/cloud/paas/process-automation/admin-process-automation/create-iam-policy-identity-domain.html#GUID-D5920ABB-18D2-478A-8442-486FBA5B9228)

## Task 2: Enable Process Automation

To enable a Process Automation instance with an Oracle Integration instance:

1.	Open the navigation menu and click Developer Services. Under Application Integration, click Integration.

2.	From the Compartment drop-down list, select the compartment in which you want to provision and enable a Process Automation instance with an Oracle Integration instance.The page is refreshed to show any existing service instances in the selected compartment.

3.	Choose an existing instance or create an Oracle Integration instance and select it. The Integration instance details page opens.

4.	Click the Enable link for Process Automation on the Integration instance information tab.

5.	When prompted, click Enable to confirm that you want to enable Process Automation.

Note the following:

-	The Oracle Integration icon turns orange and its status changes to Updating.

-	It can take several minutes for the enablement to complete.

-	Once complete, that is when a Process Automation instance gets enabled and provisioned with the Oracle Integration instance, the Oracle Integration icon changes back to green with an Active status and Process Automation shows as Enabled.

## Task 3: Assign IDCS Application Roles to Manage Access

After you've enabled an Process Automation instance, assign predefined IDCS application roles to users so that they can work with the features of the Decisions.

> Note:The user who enables Process Automation with Oracle Integration 3 is automatically granted the ServiceAdministrator role.

In Process Automation, there are two predefined IDCS application roles: ServiceDeveloper and ServiceAdministrator. These roles have to be assigned to users or groups in the Process Automation service instance application from the Oracle Identity Cloud Service (IDCS) admin console.

-	ServiceDeveloper: Any user who wants to access and work on Process Automation Designer has to be assigned the ServiceDeveloper role.

-	ServiceAdministrator: Any user who wants full administrative privileges within Process Automation including administrative tasks in Workspace has to be assigned the ServiceAdministrator role.

As a best practice, it is recommended that you assign these roles to groups, rather than individual users. For example, assign the ServiceDeveloper IDCS application role to a group in both the Oracle Integration and Process Automation service instance applications from the Oracle Identity Cloud Service admin console. In this way it will be easier to manage user access, as any user who is a member of the group can access the Oracle Integration and Process Automation design-time.

For information on how to assign IDCS application roles for Process Automation and Oracle Integration, see:

-	[Assign IDCS Application Roles to Groups in an Identity Domain](https://docs.oracle.com/en/cloud/paas/process-automation/admin-process-automation/assign-idcs-application-roles-groups-identity-domain.html#GUID-E7F7993C-BE58-4CAE-9999-63A3FD010B83)

-	[Assign Oracle Integration Roles to Groups in an Identity Domain](https://docs.oracle.com/pls/topic/lookup?ctx=appint&id=INTOO-GUID-3F03421B-BF8D-4924-84DE-D5FA54ACF92E)

Now that a Process Automation instance is enabled and provisioned with an Oracle Integration instance, and IDCS application roles assigned, you can Navigate to the OIC console and just create a sample project and check if Decisions is available in the project workspace. You should be able to see the **Add** decision button to create new decision model. If you are not able to see the same recheck your Application roles and Integration Roles.

You may now **proceed to the next lab**.

## Learn More

* [Enable Process Automation](https://docs.oracle.com/en/cloud/paas/process-automation/admin-process-automation/enable-process-automation-oracle-integration-3.html)


## Acknowledgements
* **Author** - Kishore Katta, Product Management, Oracle Integration & Process Automation
* **Last Updated By/Date** - Kishore Katta, June 2025
