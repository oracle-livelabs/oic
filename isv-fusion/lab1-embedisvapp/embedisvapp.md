# Lab 1 : Embed ISV application within Fusion Application Page

## Introduction

This lab will walk you through the steps to embed ISV 8x8 video conferencing application inside fusion application page.

Estimated Time: 30 minutes

### Objectives

You will execute the following:

- Download the JaaS integration code
- Create VBCS application with 8x8 video app.
- Create new sandbox in the Fusion application.
- Embed the VBCS application within Fusion application page using Springboard.
- Embed the VBCS application within Fusion application page using page composer.
- Embed the VBCS application within Fusion application page using application composer.
- Launch the 8x8 video app from fusion application page.

### Prerequisites

This lab assumes you have:

- Basic knowledge on VBCS
- Basic knowledge on Oracle Fusion Cloud technical (sandbox , application composer , page composer ,springboard)

## Task 1: Download the JaaS integration code

 1. Go to [JaaS Portal](https://jaas.8x8.vc) and Sign in with trail account that created in the earlier lab.

 2. Click on **Integrate meetings iFrame** under **My Video app**.
 ![Download iframe html](./images/screenshot9.png)

 3. Click on **Download Integration Code**
 It downloads index.html file and this file will be used in the following lab.

## Task 2: Create VBCS application

 1. Login to Oracle Visual Builder.
 2. Click **New** > **Create Application** > **Enter Application Name (ISVFusionIntegration)** > **Finish**.
 3. Create Web Application . Click **Web Apps** > **Create Web Application** > **Enter Application Name** > **Create**

   ![VBCS Web application](./images/screenshot1.png)

## Task 3: Add the 8x8 Video app within the VBCS web application

1. Copy the content from **index.html** (downloaded in the task1)  and paste into **launchapp.html** file.

2. Copy the below code snippet and paste in the main/main-start page code section.

   
    <details>
      <summary>*main-start*</summary>
         ```html
         <copy>
        <!-- <div class=”oj-flex”> -->
    <div class="oj-flex-item" style="padding-top:10px">
    <div> 
    <h1 class="oj-flex-item oj-sm-12 oj-md-12"><oj-bind-text
                                                   value="[[ '8x8 Jitsi Integration Using VBCS ' ]]"></oj-bind-text></h1> 
    <iframe width=100% height="500" allowtransparency="true" style="background-color:#FFFFFF;border:none" :src="[[ $application.path + 'resources/launchapp.html' ]]"> </iframe>
    </div> 


     </div> 

        </copy>
         ```
   </details>
   ![8x8 application within VBCS page](./images/screenshot2.png)

3. Go to **isvfusionwebapp** > **Settings** > **Security**

    a. Uncheck **Require authenticated access**

    b. Select **Allow embedding in any application domain**.

    c. Check **Enable implicit grant for Service Connections**.

       ![VBCS Web application](./images/screenshot10.png)

4. Click **Preview**.

5. Stage the application. Click **Hamburger icon (Right top corner)** > **Stage**.

6. Publish the application. Click **Hamburger icon (Right top corner)** > **Publish**.

7. Launch the live application. Click **All Application** > **ISVFusionIntegration** > **Live** > **isvfusionwebapp**.

  Please keep the live url handy as it will be used in the following tasks.

## Task 4: ISV integration within the Fusion application using Springboard

1. Login to Fusion Application (User should have the required roles to create the sandbox)

2. Click **Home** > **Configuration** > **Sandboxes**

3. Create a Sandbox. Click **Create Sandbox** > **Enter sandbox name (ISVFusionIntegration)**

     Select following options (Structure , Application Composer , Page Composer)

4. Click **Create and Enter**

5. Go to **Home** > **Help Dest** > **HR Service Request**

6. Go to **Tools** > **Structure**

7. Click **Create** > **Create Group** > Enter the Group Name > **Save and Close**

   ![Springboard Configuration](./images/screenshot6.png)

8. Click **Create** > **Create Page Entry**

9. Enter the details as per the screenshot below and Click **Save and Close**

   ![Springboard Configuration](./images/screenshot7.png)

10.Now you can launch the 8x8 video app from the Fusion Springboard navigator.

   ![Springboard Configuration](./images/screenshot8.png)

## Task 5: Embed the VBCS application within the Fusion application page using application composer

1. Login to Fusion Application.

2. Click **Home** > **Configuration** > **Sandboxes**

3. Click **Enter Sandbox** which is created in the Task 4.

4. Go to **Home** > **Help Dest** > **HR Service Request**

5. Go to **Tools** > **Application Composer**

6. Click **Standard Objects** > **Service Request** > **Actions and Links** > **Actions** > **Create**.

   ![Fusion Start Meet link Configuration](./images/screenshot3.png)
   
   | **Element**        | **Value** |
   | --- | ----------- |
   | Display Label | `Start Meet`   |
   | Type  | `Link`|
   | Edit Script | `return *use the Live url from the previous task*`|

   Leave the rest of the values as default and Click **Save**.

7. Click **Service Request** > **Pages** > **Standard Layout (Under HR Help Desk Landing Page Layout)** > **Actions** > **Duplicate** > **Enter New Layout Name** > **Save and Edit**.
  ![Fusion Page Layout Configuration](./images/screenshot4.png)

8. Click **Edit icon**
   Add Start Meet - Link from Available fields to Selected fields then Click **Save and Close**.

9. Click **Hamburger Icon >**Help Desk**>**HR Service Request**.
   You may notice the Start Meet field has been added to the each Service Request Records.
 ![Start Meet link embedded within Fusion Page](./images/screenshot5.png)

## Task 6: Embed the VBCS application within the Fusion application page using page composer

 1. Login to Fusion Application 

 2. Click **Home** > **Configuration** > **Sandboxes**

 3. Click **Enter Sandbox** which is created in the Task 4.

 4. Go to **Home** > **My Client Groups** > **Profiles**

 5. Go to **Tools** > **Page Composer** then Click **Structure** tab

    ![Page composer](./images/screenshot11.png)

 6. Expand the Page Composer editor in the browser. Select **panelGroupLayout:vertical** tag. (Refer the screenshot below)

    Click **+ icon**

    ![Page Editor](./images/screenshot12.png)

 7. Click **Components** > **Web Page +Add** then Click **Close**

    ![Page Editor](./images/screenshot13.png)

 8. Right Click on **Web Page** > **Edit** in the Page composer editor

    a. Copy the vbcs web application live url in the **Source** input box . Go to **Style** tab and enter *800px* in the Width     and Height fields

    b. Click **Apply** then **OK**

    ![Page Editor](./images/screenshot14.png)

    ![Page Editor](./images/screenshot15.png)

 9. Right Click on **showDetailFrame: Web Page** > **Edit** in the Page composer editor

    ![Page Editor](./images/screenshot16.png)

    a. Enter "8x8" in the Text field. then Go to **Advanced** tab.

    b. Select **auto** for the **Stretch Content** field

    ![Page Editor](./images/screenshot17.png)

    c. Click **Apply** then **OK**

You may now **proceed to the next lab**.

## Acknowledgements

- **Author** - Subburam Mathuraiveeran, Senior Cloud Engineer, Oracle North America Cloud Engineering
- **Last Updated By/Date** - Subburam Mathuraiveeran, Nov 2022
