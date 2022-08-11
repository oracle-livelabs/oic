# Lab 1 : Embed ISV application within Fusion Application Page

## Introduction
This lab will walk you through the steps to embed ISV 8x8 video conferencing application inside fusion application page using the application composer.

Estimated Time: 30 minutes

### Objectives
You will execute the following:
- Create VBCS application with 8x8 video app.
- Create new sandbox in the Fusion application.
- Embed the VBCS application within Fusion application page using application composer.
- Launch the 8x8 video app from fusion application page.

### Prerequisites
This lab assumes you have:
- Completed all the previous labs.


## Task 1: Create VBCS application

1. Login to Oracle Visual Builder.
2. Click **New** > **Create Application** > **Enter Application Name (ISVFusionIntegration) ** > **Finish**.
3. Create Web Application . Click **Web Apps** > **Create Web Application** > **Enter Application Name** > **Create**


## Task 2: Add the 8x8 Video app within the VBCS web application

1. Create launchapp.html file in the local desktop and copy the below code snippet in the file.

2. Import the launchapp.html file into the Resources folder. **Resources (Right Click) ** > **Import**.

3. Copy the below code snippet in the main-start page.

4. Click **Preview**.

5. Stage the application. Click **Hamburger icon (Right top corner)** > **Stage**.

6. Publish the application. Click **Hamburger icon (Right top corner)** > **Publish**.

7. Launch the live application. Click **All Application** > **ISVFusionIntegration** > **Live** > **isvfusionwebapp**.

    ![Integration Progress after FTP Invoke](images/integration-progress-1.png)

## Task 3: Embed the VBCS application within the Fusion application page


1. Login to Fusion Application

2. Click **System Administration** > **Administration** > **Edit Pages** > **Activate a Sandbox**.

3. Create a Sandbox. Click **Create Sandbox** > **Enter sandbox name (ISVFusionIntegration)**

     Select following options (Structure , Application Composer , Page Composer)

4. Click **Create and Enter**

5. Go to **Home** > **HR Service Request**

6. Go to **Tools** > **Application Composer**

7. Click **Standard Objects** > **Service Request** > **Actions and Links** > **Actions** > **Create**.

 | **Element**        | **Value** |       
 | --- | ----------- |
 | Display Label | `Start Meet`   |
 | Type  | `Link`|
 | Edit Script | `return *Live url of the VBCS application`|

    Leave the rest of the values as default and Click **Save**.

6. Click **Service Request** > **Pages** > **Standard Layout (Under HR Help Desk Landing Page Layout)** > **Actions** > **Duplicate** > **Enter New Layout Name** > **Save and Edit**.

7. Click **Edit icon**

Add Start Meet - Link from Available fields to Selected fields then Click **Save and Close**.

8. Click **Hamburger Icon > **Help Desk** > **HR Service Request**.

You may notice the Start Meet field has been added to the each Service Request Records.

You may now **proceed to the next lab**.


## Acknowledgements

* **Author** - Subburam Mathuraiveeran, Senior Cloud Engineer, Oracle North America Cloud Engineering
* **Last Updated By/Date** - Subburam Mathuraiveeran, Aug 2022
