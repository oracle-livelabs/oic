# Test the Recipe

## Introduction

In this lab, you will test the configured and activated integrations using Oracle Integration Cloud to validate that the recipe is functioning as expected.

After completing the setup and activation steps, it is important to verify that the integration flows can successfully interact with the FHIR-based EMR system and return accurate results. You will execute multiple integration flows such as Search Patient, Practitioner, Appointment, MedicationRequest, and Coverage, using sample input parameters.

This lab helps ensure that the end-to-end integration—from request submission to response retrieval—is working correctly. You will also monitor the execution and analyze responses to confirm that the expected FHIR resources are being returned.

By the end of this lab, you will gain confidence in testing and validating healthcare integrations built using Oracle Integration.

Estimated Time: 15 minutes

### Objectives

In this lab you will learn:

- How to Test the Recipe

### Prerequisites

- All the previous labs completed successfully.

## Task 1: Activate All Integrations

1. In the left navigation pane, select **Projects**.
2. Select the **Search FHIR Resources** project that you created, click Activate.
    ![Activate the Project](images/project-activate.png)

3. In the Activate Project panel:
    - Select the default deployment settings
    - Select an appropriate tracing option
    - Click Activate again.
4. Wait for the confirmation message indicating that the integration has been successfully activated.
5. Refresh the page to verify the updated status.

## Task 2: Run the Integration Flow (Search Patient)

1. In the left navigation pane, select **Projects**.
2. Select the **Search FHIR Resources** project that you created, click on *Edit* icon.
3. Navigate to the Integrations section within the project workspace.
4. Locate the integration flow “Search Patient”.
5. Click Actions (...) and select Run.
6. In the Run dialog:
    - Provide the required input under URI Parameters (e.g., patient identifier or phone)
    - For example, enter:
        - id = 90269459 (sample patient identifier) OR 90255893 OR 90256829
    - Click Run to execute the integration.

## Task 3: Monitor Integration Execution

1. In the project workspace, click Observe.
2. Monitor the running integration instances.
3. Verify that each flow is triggered and completed successfully.

## Task 4: Test Additional Integration Flows

1. Repeat the above steps to test (Task 2: task4-6 and Task3) the following flows.
2. Use the sample data provided below while entering values in the URI Parameters section

    - Search Practitioner
        - Sample Input:
            - id = user-ee80c502-1f66-4cf7-98c2-e1f266e5fe56 OR user-7af2885d-d180-4264-b74f-523d23d91c9c

    - Search Appointment
        - Sample Input:
            - id = 105794721 OR 105794731
    - Search MedicationRequest
        - Sample Input:
            - id = 95923465 OR 131264211
    - Search Coverage
        - Sample Input:
            - id = 98068045 OR 125144909

    Congratulations! 🎉
    You may now **proceed to the next lab**.

    You have successfully completed the *Search FHIR Resources in EMR* Live Lab!

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

* [Using Agentic AI](https://docs.oracle.com/en/cloud/paas/application-integration/aiagents/welcome-agentic-ai.html)

## Acknowledgements

* **Author** - Subhani Italapuram, Technical Director, Partner Enablement, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Apr 2026
