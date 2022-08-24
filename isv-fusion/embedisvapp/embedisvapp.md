# Lab 1 : Embed ISV application within Fusion Application Page

## Introduction
This lab will walk you through the steps to embed ISV 8x8 video conferencing application inside fusion application page using the application composer.

Estimated Time: 30 minutes

### Objectives
You will execute the following:
- Create VBCS application with 8x8 video app.
- Create new sandbox in the Fusion application.
- ISV integration within the Fusion application using Springboard.
- Embed the VBCS application within Fusion application page using application composer.
- Launch the 8x8 video app from fusion application page.

### Prerequisites
This lab assumes you have:
- Completed all the previous labs.


## Task 1: Create VBCS application

1. Login to Oracle Visual Builder.
2. Click **New** > **Create Application** > **Enter Application Name (ISVFusionIntegration) ** > **Finish**.
3. Create Web Application . Click **Web Apps** > **Create Web Application** > **Enter Application Name** > **Create**

   ![VBCS Webapplication](images/Screenshot1.png)

## Task 2: Add the 8x8 Video app within the VBCS web application

1. Import the launchapp.html file into the Resources folder. **Resources (Right Click) ** > **Import**.

2. Copy the code snippet from main-start file and paste in the main/main-start page code section.

   ![8x8 application within VBCS page](images/Screenshot2.png)

3. Click **Preview**.

4. Stage the application. Click **Hamburger icon (Right top corner)** > **Stage**.

5. Publish the application. Click **Hamburger icon (Right top corner)** > **Publish**.

6. Launch the live application. Click **All Application** > **ISVFusionIntegration** > **Live** > **isvfusionwebapp**.

## Task 3: ISV integration within the Fusion application using Springboard.

1. Login to Fusion Application with Administrator role

2. Click **System Administration** > **Administration** > **Edit Pages** > **Activate a Sandbox**.

3. Create a Sandbox. Click **Create Sandbox** > **Enter sandbox name (ISVFusionIntegration)**

     Select following options (Structure , Application Composer , Page Composer)

4. Click **Create and Enter**

5. Go to **Home** > **Help Dest** > **HR Service Request**

6. Go to **Tools** > **Structure**

7. Click **Create** > **Create Group** > Enter the Group Name > **Save and Close**

   ![Springboard Configuration](images/Screenshot6.png)

8. Click **Create** > **Create Page Entry**

9. Enter the details as per the screenshot below and Click **Save and Close**

   ![Springboard Configuration](images/Screenshot7.png)

10.Now you can launch the 8x8 video app from the Fusion Springboard navigator.

   ![Springboard Configuration](images/Screenshot8.png)


## Task 4: Embed the VBCS application within the Fusion application page using application composer.


1. Login to Fusion Application with Administrator role

2. Click **System Administration** > **Administration** > **Edit Pages** > **Activate a Sandbox**.

3. Create a Sandbox. Click **Create Sandbox** > **Enter sandbox name (ISVFusionIntegration)**

     Select following options (Structure , Application Composer , Page Composer)

4. Click **Create and Enter**

5. Go to **Home** > **Help Dest** > **HR Service Request**

6. Go to **Tools** > **Application Composer**

7. Click **Standard Objects** > **Service Request** > **Actions and Links** > **Actions** > **Create**.

  ![Fusion Start Meet link Configuration](images/Screenshot3.png)

 | **Element**        | **Value** |       
 | --- | ----------- |
 | Display Label | `Start Meet`   |
 | Type  | `Link`|
 | Edit Script | `return *Live url of the VBCS application`|

    Leave the rest of the values as default and Click **Save**.

6. Click **Service Request** > **Pages** > **Standard Layout (Under HR Help Desk Landing Page Layout)** > **Actions** > **Duplicate** > **Enter New Layout Name** > **Save and Edit**.

  ![Fusion Page Layout Configuration](images/Screenshot4.png)

7. Click **Edit icon**

Add Start Meet - Link from Available fields to Selected fields then Click **Save and Close**.

8. Click **Hamburger Icon > **Help Desk** > **HR Service Request**.

You may notice the Start Meet field has been added to the each Service Request Records.

 ![Start Meet link emdeded within Fusion Page](images/Screenshot5.png)

You may now **proceed to the next lab**.


## Acknowledgements

* **Author** - Subburam Mathuraiveeran, Senior Cloud Engineer, Oracle North America Cloud Engineering
* **Last Updated By/Date** - Subburam Mathuraiveeran, Aug 2022
