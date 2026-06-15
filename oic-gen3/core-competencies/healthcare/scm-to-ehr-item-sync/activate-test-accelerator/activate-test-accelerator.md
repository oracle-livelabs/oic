# Activate and Test the Accelerator

## Introduction

In this lab, you will test the configured and activated integrations using Oracle Integration Cloud to validate that the recipe is functioning as expected.

After completing the setup and activation steps, it is important to verify that the integration flows can successfully interact with the FHIR-based EMR system and return accurate results. 

This lab helps ensure that the end-to-end integration—from request submission to response retrieval—is working correctly. You will also monitor the execution and analyze responses to confirm that the expected FHIR resources are being returned.

By the end of this lab, you will gain confidence in testing and validating healthcare integrations built using Oracle Integration.

Estimated Time: 15 minutes

### Objectives

In this section, you will:

- Activate the Project
- Run the Synchronize Items with Oracle Health scheduled process
- Verify file generation in Oracle WebCenter Content
- Monitor integration execution in Oracle Integration
- Validate file transfer to the SFTP location
- Confirm successful end-to-end processing

### Prerequisites

- All the previous labs completed successfully.

## Task 1: Verify Integration Readiness

Review the integration instance details and verify:

1. Item organization mappings are correct
2. Subinventory mappings are correct
3. Locator mappings are correct
4. Unit-of-measure mappings are applied
5. Transaction mappings are processed successfully
6. Validate the lookup table mappings configured earlier in the accelerator.

## Task 2: Activate All Integrations

1. In the left navigation pane, select **Projects**.
2. Select the **Oracle PLM Millenium Item Sync** project that you created, click Activate.
3. In the Activate Project panel:
    - Select the default deployment settings
    - Select an appropriate tracing option
    - Click Activate again.
4. Wait for the confirmation message indicating that the integration has been successfully activated.
5. Refresh the page to verify the updated status.

## Task 3: Generate Initial Full Publish - Execute this task if required, otherwise skip.

1. Sign in to Oracle Fusion Cloud SCM.
2. Navigate to Tools > Run the scheduled process : Product Hub Publication Job
3. Configure
    - Publish Items = Yes
    - Publish All Records = Yes
    - Spoke System = Oracle Health

4. Submit the process.
5. Monitor the process until it completes successfully.

## Task 4: Configure Ongoing Synchronization

1. Sign in to Oracle Fusion Cloud SCM.
2. Navigate to Tools > Scheduled Processes
3. Click on *Schedule New Process*
4. Search for *Synchronize Items with Oracle Health*
5. Configure:
    - Synchronize Item Master = Yes
    - Synchronize Item Locations = Yes
    - Synchronize Item Costs = Yes
6. Configure the process schedule.
7. Oracle recommends scheduling the synchronization no more frequently than every 15 minutes.

## Task 5: Monitor the Scheduled Process

1. Navigate to the Scheduled Processes page.
2. Monitor the process status.
3. Verify the process completes successfully with the status *Succeeded*, Wait for few minutes to the final status.
4. This process:
    - Extracts item master data
    - Extracts item location data
    - Extracts item cost data
    - Generates outbound files
    - Uploads files to Oracle WebCenter Conte

## Task 6: Verify Files in Oracle WebCenter Content

1. Access Oracle WebCenter Content. For example:
    https://fusion_instance.com/cs
2. Navigate to the configured content folder.
3. Verify publication files are generated, Search for Title *PIM*
4. Confirm files are uploaded to Oracle WebCenter Content.
5. Confirm:
    - File names are generated correctly
    - File timestamps are current
    - Files contain expected data
6. Validate:
    - Item master payloads
    - Item location payloads
    - Item cost payloads

## Task 7: Monitor Oracle Integration Execution

1. Sign in to Oracle Integration, In the project workspace, click Observe.
2. Monitor the running integration instances, Search for the following integrations:
    - Oracle PLM Millennium Sync
    - Oracle PLM Millennium Item Sync API
    - Oracle PLM Item Event Stub
3. Verify:
    - Integrations are triggered successfully
    - No failed instances are reported
    - Payload tracking information is available

## Task 8: Verify Error Notifications

If error notification emails are configured:

1. Verify the email contacts configured in:
    - OracleSCMOracleHealthEHR_EmailContacts
2. Confirm:
    - Error notifications are generated for failed integrations
    - Email recipients receive notifications successfully

## Task 9: Review Integration Tracking

1. Open the integration instance tracking page.
2. Review:
    - Execution summary
    - Processing duration
    - Payload details
    - Error messages (if any)
3. Ensure all orchestration flows complete successfully.

## Task 10: Expected Result

At the end of this section:

1. The scheduled process completes successfully.
2. Item master, item location, and item cost files are generated.
3. Oracle Integration processes the files successfully.
4. Lookup mappings are applied correctly.
5. The Oracle PLM Millennium Item Sync accelerator is validated successfully.

    Congratulations! 🎉

    You may now **proceed to the next lab**.

    You have successfully completed the *Oracle Integration3 - Sync Items from SCM to EHR* Live Lab!

    What You've Accomplished
    In this Live Lab, you have successfully:

    - Installed a prebuilt integration recipe in Oracle Integration Cloud
    - Configured the FHIR connection to interact with an EMR system
    - Explored and understood the design and flow of multiple integration processes
    - Activated integration flows for execution
    - Executed integration flows to retrieve FHIR resources such as:
        - Patient
        - Practitioner
        - Appointment
        - MedicationRequest
        - Coverage
    - Validated responses returned from the EMR (FHIR server)
    - Monitored integration execution using the Observe feature

## Learn More

* [Accelerator](https://docs.oracle.com/en/cloud/saas/supply-chain-and-manufacturing/26b/fasih/overview.html)

## Acknowledgements

* **Author** - Subhani Italapuram, Technical Director, Partner Enablement, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, May 2026
