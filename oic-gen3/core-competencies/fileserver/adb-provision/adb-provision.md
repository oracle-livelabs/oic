# Provision an Oracle Autonomous Database (ADW and ATP)

## Introduction

This lab walks you through the steps to get started using the Oracle Autonomous Database (Autonomous Data Warehouse [ADW] and Autonomous Transaction Processing [ATP]) on Oracle Cloud. In this lab, you will provision a new ATP instance.

Estimated Time: 5 minutes

Watch the video below for a quick walk through of the lab.

[Provision Autonomous Database Instance](youtube:a6Jm7lYaCWI)

> **Note:**  While this lab uses ATP, the steps are the same for creating an ADW database.

### Objectives

In this lab, you will:

-   Learn how to provision a new Oracle Autonomous Database

### Prerequisites

- This lab requires completion of the Get Started section in the Contents menu on the left.

## Task 1: Choose ATP from the services menu

1. Log in to the Oracle Cloud.
2. Once you log in, the cloud services dashboard shows all the services available to you. Click the navigation menu in the upper left to show top level navigation choices.

    > **Note:** You can also directly access your Autonomous Data Warehouse or Autonomous Transaction Processing service in the Quick Actions section of the dashboard

3. The following steps apply similarly to either Autonomous Data Warehouse or Autonomous Transaction Processing. This lab shows provisioning of an ATP database, so click **Oracle Database**, then **Autonomous Data Warehouse**.

4. This console shows that no databases yet exist. If there were a long list of databases, you could filter the list by the **State** of the databases (Available, Stopped, Terminated). You can also sort by **Workload Type**. In this example, **Transaction Processing** is the workload type.

## Task 2: Create an Oracle Autonomous Database instance

1. Click **Create Autonomous Database** to start the instance creation process.

2.  This brings up the *Create Autonomous Database* screen where you will specify the configuration of the instance.

3. Specify basic information for the autonomous database:

    | **Field**  | **Value** | Note |
    |---|---|---|
    | Compartment | (Defaut) | |
    | Display Name | `ATPDB` | Enter a memorable name for the database for display purposes |
    | Database Name | `ATPDB` | Use letters and numbers only, starting with a letter. Maximum length is 14 characters. |
    |
4. Choose a workload type. Select the workload type for your database from the choices:

    - **Transaction Processing** - For this lab 

5. Configure the database:

    - __Always Free__ - If your Cloud Account is an Always Free account, you can select this option to create an always free autonomous database. An always free database comes with 1 CPU and 20 GB of storage. For this lab, we recommend you check **Always Free** option.
    - __Choose database version__ - Select a database version from the available versions.
    - __OCPU count__ - Number of CPUs for your service. For this lab, specify __1 CPU__. If you choose an Always Free database, it comes with 1 CPU.
    - __Storage (TB)__ - Select your storage capacity in terabytes. For this lab, specify __1 TB__ of storage. Or, if you choose an Always Free database, it comes with 20 GB of storage.
    - __Auto Scaling__ - For this lab, keep auto scaling enabled, to enable the system to automatically use up to three times more CPU and IO resources to meet workload demand.
    - __New Database Preview__ - If a checkbox is available to preview a new database version, do NOT select it.

    > **Note:** You cannot scale up/down an Always Free autonomous database.


7. Create administrator credentials:

    - __Password and Confirm Password__ - Specify the password for *ADMIN* user of the service instance. 

8. Choose network access:
    - For this lab, accept the default, **Secure access from everywhere**.
    
10. Click **Create Autonomous Database**.


11.  Your instance will begin provisioning. In a few minutes, the state will turn from *Provisioning* to *Available*. At this point, your ATP database is ready to use! Have a look at your instance's details here including its name, database version, OCPU count, and storage size.

Please *proceed to the next lab*.

## Learn more

- [Oracle Autonomous Data Warehouse](https://www.oracle.com/in/autonomous-database/autonomous-data-warehouse/)

## Acknowledgements

- **Author** - Subhani Italapuram, Oracle Integration Product Management
- **Last Updated By/Date** - Subhani Italapuram, Sep 2025
