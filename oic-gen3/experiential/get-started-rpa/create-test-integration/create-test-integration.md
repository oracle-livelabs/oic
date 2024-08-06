# Create and Test the Integration

## Introduction

After ensuring the robot performs the UI tasks as expected, we will now create an integration that calls it. This integration simulates an end-to-end testing scenario, where the integration passes the input values to the robot.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:

* Create a scheduled integration which invokes the robot and passes input values
* Add Scheduled parameters which capture the requested PO number
* Complete Mapper activity
* Configure Business Identifiers
* Activate the integration
* Run Integration to call the robot
* Validate Integration Run Status

### Prerequisites

This lab assumes you have:

* Activated the robot
* Successfully tested the robot in its environment
* All previous labs successfully completed

## Task 1: Create Scheduled Integration

Create a scheduled integration that will invoke the robot and pass input parameters.

1. On the project page, move to the **Integrations** box and click **Add**.

2. On the **Add integration** panel, click **Create**.

   ![Select Create](images/add-integration_create.png " ")

3. On the next screen, select **Schedule**

    ![Select Schedule pattern](images/add-integration_select-schedule.png " ")

4. Enter a name for the integration, leave all other fields as default, and click **Create**.

    ![Enter integration name](images/add-integration_enter-name.png " ")

    The Integration Designer will appear, with a default integration.

5. However the mouse just below the **Schedule** activity and click on the **+** button.

    ![Add Robot activity](images/integration_add-robot-activity.png " ")

6. In the popup **Actions** tab, scroll down until the bottom and select **Robot Flow** action.

    ![Select Robot flow action](images/integration_select-robot-flow-action.png " ")

7. On the **Configure Basic Info** screen, enter a valid name for the endpoint without spacing.

    ![Enter endpoint name](images/integration_add-robot-activity_enter-endpoint-name.png " ")

8. On the **Configure Configuration** screen, select the previously activated Robot flow.

   ![Select robot flow](images/integration_add-robot-activity_select-robot.png " ")

9. Click **Continue**, then **Finish**.

    The designer with Robot action will be displayed.

    ![Show robot action](images/integration_show-robot-action.png " ")

10. Move below the **Robot process** activity and click on the **+** button.

    ![Add activity below Robot call](images/integration_add-activity-below-robot.png " ")

11. In the **Configure assign** panel, take the following steps:

    1. Change **Name** to `Response`
    2. Click on the **Apply** button to save name change
    3. Click **+** to add a variable
    4. Select Datatype **String**

    ![Configure Assign action](images/assign-action_configure.png " ")

12. With the side panel displayed, take the following steps:

    1. Change **Variable** to ```vSupplierName```
    2. On **Input sources** tab, expand **$CallRobot > RPAFlowResponse > ResponseWrapper** and drag `SupplierName` to the **Value** textbox on the right.

    ![Configure Assign variable](images/assign-action_configure-variable.png " ")

13. Click **Save** to close the panel.

14. On the integration canvas, click **Save**.

## Task 2: Add Scheduled parameters

1. Double-click on the **Schedule** activity to open the **Configure schedule parameters** editor.

    ![Configure schedule parameters](images/integration_configure-schedule-parameters.png " ")

2. Click on the **+** to add a parameter.

3. Under **Parameter name**, enter `PONumber`.

    ![Configure schedule parameters](images/integration_configure-schedule-parameters_name.png " ")

4. Click anywhere on the integration canvas to save the parameter and close the panel.

5. Click **Save**.

## Task 3: Complete Mapper activity

1. Double-click the **Map** activity.

    ![Double-click map activity](images/integration_click-mapper-activity.png " ")

2. In the Map Editor, move to the **Target** side and click on the ![Mapper left arrow button](images/mapper_arrow-button.png) (**left arrow**) next to the `Request Wrapper`.

    The `PO Number` field should be visible on the Target side.

3. Drag the `PONumber` field from the Sources side to the `PO Number` field on the Target side.

    ![Mapping of PONumber](images/mapper_ponumber-mapping.png " ")

    This completes the mapping activities.

4. Click **Validate** and wait for the confirmation message `Map to CallRobot successfully validated`.

5. Close the mapper by clicking on the ![Go back button](images/go-back-button.png) (**Go Back**) button on the top-left corner of the screen.

6. Click **Save**.

## Task 4: Configure Business Identifiers

1. Click on the ![Business Identifiers](images/integration_business-identifiers-button.png) (**Business Identifiers**) button.

2. Drag the `$PONumber` from Sources to the first **Business identifier field**.

    ![Assign Business Identifiers](images/business-identifiers_assign.png)

3. Click **Save** to close the **Business Identifiers** panel.

4. Click **Save** on the integration canvas.

5. Close the canvas by clicking on the ![Go back button](images/go-back-button.png) (**Go Back**) button on the top-left corner of the screen.

    Under the **Integrations** box, you will find the integration with status `Configured`.

## Task 5: Activate the integration

1. On the right side of the integration, click on **...** (**Options**), then select **Activate**.

    ![Activate Integration](images/activate-integration.png " ")

2. In the **Activate integration** panel, select **Debug** tracing level and click **Activate**.

    After a few seconds, the integration status will change from `Activation in progress` to `Active`. You can manually refresh the screen to see the status change.

## Task 6: Run Integration to call the robot

Once the integration is `Active`, we can run it on-demand.

1. On the right side of the integration, click on **...** (**Options**), then select **Run**.

2. On the **Configure and run** panel, enter the previously obtained PO Number under the **Current Value** field (see sample value). Keep all other values as default.

    ![Configure and run parameters](images/configure-run_parameters.png " ")

3. Click **Run** to initiate the integration run.

## Task 7: Validate Integration Run Status

After clicking **Run** to start the integration, a side panel of **Activity stream** will appear. Here we will observe the status of the integration run.

1. After the robot run has completed, move to the **Activity stream** panel and click the ![Refresh Button](images/refresh-button.png) (**Refresh**) button until you see the message `Processing completed successfully`.

    ![Activity Stream run completed](images/activity-stream_run-completed.png " ")

2. Expand the **Invoke CallRobot** activity to verify the robot run.

    ![Activity Stream robot invoke call](images/activity-stream_invoke-robot-call.png " ")

3. Expand the **Message received by Assignment Response** activity to verify the returned supplier name of the provided PO number (see sample supplier name).

    ![Supplier name response](images/activity-stream_supplier-name-response.png " ")

You have successfully completed this lab.

## Acknowledgements

* **Author** - Ravi Chablani, Product Management - Oracle Integration
* **Last Updated By/Date** - Ravi Chablani, July 2024
