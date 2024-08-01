# Project Concepts

## Introduction

This lab will walk you through the projects and project life cycle in Oracle Integration.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Understand concepts of a project.
- Understand how project helps you.

### Prerequisites

This lab assumes you have:

- Completed all the previous labs

## About the projects

You can design, manage, and monitor integrations from a single, self-contained workspace known as a project. This eliminates the need to navigate to other parts of the Oracle Integration user interface (which is required with standalone integrations or integrations in packages).

## How project helps you

With everything at your fingertips, you'll build faster. And, with easy updates to integrations based on accelerators, you'll future-proof your prebuilt integrations. Finally, deploy quickly and with confidence using project deployments. Keep reading to learn more.

1. Manage the releases of your integrations

    With project deployments, you can move integrations to higher environments, such as testing or production, quickly and efficiently. A project deployment represents the current snapshot of all the integration versions that must be in the environment you're promoting to. Enjoy improved stability in your higher environments and easier rollbacks when things go wrong.
2. Control access to integrations and their components using fine-grained access control

    With projects, you control the users and groups who can edit, view, and monitor an integration and its related components using role-based access control (RBAC). Designing integrations within a project is the only way to control access at this fine-grained level.
3. Build, manage, and monitor everything in one place

    A project helps you get started quickly and confidently because you build all the components that an integration needs within a project. You don't need to click all over the user interface to find the right page to create a connection, lookup, or JavaScript library. It's all right there within your project, including the ability to monitor your integrations.

4. Build faster by reusing components

    After you've built an integration or two within a project, creating additional integrations is even faster and easier. The connections, JavaScript libraries, and lookups from existing integrations are all at your fingertips, offering easy one-stop shopping. Just grab what you need from the streamlined user interface and start building.

5. Future-proof your prebuilt integrations with easy updates

    Accelerators provide prebuilt integrations that you can easily customize, but what happens to your customized integration when a new version of the accelerator is released? When you install the accelerator in a project, you can automatically update to the new version without reworking your customizations. Use accelerators with confidence, knowing that you can always accept the newest version without having to set aside time to modify and troubleshoot your integration.

    See Extend an Integration in an Accelerator Project and Upgrade an Accelerator Project and Merge Extensions.

6. Facilitate the exchange of business documents using projects

    In a project, you can design, manage, and monitor integrations in B2B standalone mode. Use an AS2 Adapter connection as a trigger or an invoke connection, or use an FTP Adapter connection as an invoke connection. Track the processing of B2B messages as integration instances during runtime in the project.

## Restrictions
Be aware of the restrictions for projects.

Contents of a project

- You can create a maximum of 100 integrations, 50 project deployments, 20 connections, 50 lookups, and 20 JavaScript libraries in a project.

- To stay within the project deployment limit, delete old versions periodically. If you need to keep older versions for auditing purposes, you can export the project deployments and archive them using your organization's archiving tools, such as a source control system.

- Lookups and JavaScript libraries are visible and usable only in a single project.

- Your uncluttered view shows you only the assets in which you are interested.

- Similarly, assets created in standalone integrations or integrations in packages are not visible or usable in a project.

- You can use certificates, which are defined globally, from any project.

## Security and other restrictions
- You cannot invoke one project from another project.
- You cannot migrate a package of integrations to a project.
- You cannot add an OCI object storage action to an integration in a project.
- You cannot clone individual JavaScript libraries within a project.
- You cannot design an integration in B2B trading partner mode in a project. If you import an integration in B2B trading partner mode into a project, it fails during runtime.

You may now **proceed to the next lab**.

## Learn More

- [About Projects](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/release-management.html)

- [Design, Manage, and Monitor Integrations in Projects](https://docs.oracle.com/en/cloud/paas/application-integration/integrations-user/designing-managing-and-monitoring-integrations-projects.html)

## Acknowledgements

* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, July 2024
