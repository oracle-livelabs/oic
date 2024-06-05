# Run end-to-end demo

## Introduction

This demo lab will walk you through the steps to run the Robot which will enter a given Purchase Order in Oracle ERP Cloud and fetch the supplier name from the User Interface, and return that value as response of the flow.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:

* Provide a valid request payload to start the robot flow
* Observe the completion of instructions by the robot

This lab assumes you have:

* All previous labs successfully completed

## Task 1: Run Flow

1. On the Project overview, navigate to the robot flow and click on **...**, then select **Run**.

2. In the **Input** tab, fill in a valid purchase order number as a value of attribute **PONumber**.

    Input with sample purchase order number:
    ![Select Purchase Orders tile](images/robot-run_input-payload.png " ")

3. Click **Run** on the top-right side of the screen.

You should start seeing the following activities in the terminal:

    ```
    INFO  - Launching robot instance e0ccb43d-4af4-4aeb-81ec-a5f76d95bc48
    INFO  - Requesting messages from ControlRoom
    ```
After this message, the robot will bring up the assigned browser window and start the flow. During this time, wait until the robot completes all the steps.

## Task 2: Validate Robot Flow Status

Let's monitor the robot flow.

1. From the **Configure and run** screen, click on the link under **Instance ID**.

    The Robot instances tab appears and is filtered to show only the instance ID that you selected. Just after the start of the robot flow, the instance will have **Status** ``Pending``.

2. The robot will start a new browser session to perform the UI tasks. Wait until the robot completes the flow, the click the (**Refresh**) button until the status changes to ``Succeeded``.

3. Hover over the completed instance and move the mouse to the right of the screen. Click on the (**View details) button.

    This opens the **Activity Stream** for the selected instance. 






## Acknowledgements

* **Author** - Ravi Chablani, Product Management - Oracle Integration
* **Last Updated By/Date** - Ravi Chablani, May 2024
