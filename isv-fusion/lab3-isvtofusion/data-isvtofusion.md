# Lab 3 : Data Transfer from 8x8 Jitsi Application to Fusion Application

## Introduction

This lab will walk you through the steps to implement data transfer from 8x8 Jitsi video conference platform to Fusion application.

Estimated Time: 30 minutes

### Objectives

You will execute the following:

- Capture the ROOM_CREATED event data in OIC from 8x8 Jitsi platform Webhook configuration.OIC updates the event data in the
  Investigation Exec Summary field in the Fusion application page (HR Help Desk Service request page) through Fusion Cloud ERP
  adapter.
- The Oracle integration cloud implementation
- JaaS (Jitsi as a Service) configurations.

### Prerequisites

This lab assumes you have:

- Basic knowledge on OIC.
- OIC user with Service Invoker role
- Completed all the previous labs.

## Task 1: The Oracle Integration Cloud implementation

1. Download the **JITSIEVENTS_01.00.0000.iar** file from below link and    import into the OIC instance.

   [OIC Code](https://c4u04.objectstorage.us-ashburn-1.oci.customer-oci.com/p/EcTjWk2IuZPZeNnD_fYMcgUhdNDIDA6rt9gaFj_WZMiL7VvxPBNMY60837hu5hga/n/c4u04/b/livelabsfiles/o/labfiles/JITSIEVENTS_01.00.0000.iar).

2. Update the Oracle ERP Cloud adapter connection to point your fusion instance.

3. Pick any existing SR number from HR Help Service Request page and update the SR number in the UpdateFusion xslt.
 ![XSLT update](./images/xsltupdate.png)

4. Save and Activate the OIC interface.

5. Keep the OIC service url handy and it will be used in the next task.

 Click **Metadata URL**

  ![Get the endpoint url](./images/oicendpoint.png)

 Copy Endpoint URL.

 ![Get the endpoint url](./images/oicendpoint1.png)

## Task 2: JaaS (Jitsi as a Service) configurations

1. Login to [JaaS Portal](https://jaas.8x8.vc).

2. Go to  [Online Base64 Converter](https://www.base64decode.org/) and Click **Encode**

3. Enter the oic user credentials in the below format.
   **username:password**  (This user should have ServiceInvoker role assigned)
   Click **Encode**

4. Click **Webhooks** > **Add endpoint**.
 | **Element**          | **Value**                                            |
 | -------------------- | ---------------------------------------------------- |
 | Endpoint URL         | `enter the oic url created in the previous step`     |
 | Authorization header | `Basic <<base64encoded value in the previous step>>` |
 | Event                | `ROOM_CREATED`                                       |
![Webhook configuration](./images/webhookconfig.png)
![Endpoint url](./images/webhookendpoint.png)
Click **Add endpoint**

5. Launch the 8x8 video app from the HR Service Request Page through Start Meet link and Join the meeting.

6. You may notice the OIC instance are created and its triggered from the webhook configuration created in the previous step.

![OIC instances](./images/oicinstancecreation.png)

![InvestigationExecSummary field](./images/fusionfieldupdate.png)

Now you may see the Investigation Exec Summary field updated with the 8x8 ROOM_CREATED event data against the SR number provided the xslt in the Task1.

## Acknowledgements

- **Author** - Subburam Mathuraiveeran, Senior Cloud Engineer, Oracle North America Cloud Engineering
- **Last Updated By/Date** - Subburam Mathuraiveeran, Nov 2022
