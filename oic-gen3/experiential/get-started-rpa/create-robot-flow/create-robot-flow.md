# Create Robot Flow

## Introduction

This lab walks you through the steps to create a end-to-end robot flow. When you create a robot flow, you define its trigger and the actions that the robot performs.

### Objectives

In this lab, you will:

* Create a Robot
* Specify Input and Output Triggers
* Install the Robot Designer Extension
* Add Robot Actions

### Prerequisites

This lab assumes you have:

* Completed the Robot Connection
* Chrome Browser with manage permission

## Task 1: Create a Robot

When you create a robot, you define its trigger and the actions that the robot performs.

1. In the navigation pane, select **Projects** and then click on the project created in the previous lab.

2. On the right side of the page, go to the **Robots** box and click **+ (Add)**.

3. In the **Create robot** panel, fill in the following fields:
    | **Field** | **Required** | **Value** |
    | --- | ----------- | ----------- |
    | Name          | Yes | Enter a name for the robot connection type. <br> For example: `LiveLabs Robot Flow`       |
    | Identifier    | Yes | This entry is autogenerated based on the Name value.  |
    | Version       | Yes | Keep as default: `1.00.00` |
    | Description   | No  | Provide additional information about the robot.|
    | Keywords      | No  | Enter text that people might use to search for the robot. |
    | | | |

    | ![Create robot flow panel](images/create-robot-add.png " ") |
    |-|

4. Click **Create**.

The Robot Designer will appear, with a default flow which includes an Open Application action.
![Robot Designer Canvas](images/robot-designer_after-create.png " ")

## Task 2: Specify Input and Output Triggers

The trigger defines the interface for the robot, including the input (incoming request) and the output (outgoing response). For this lab, we will provide a purchase order number as input, and capture the supplier name as output.

1. Select ![Create robot flow panel](images/click-to-edit-trigger-button-small.png " ") **(Click to edit trigger)**

    The trigger panel will appear on the screen.

2. On the **Input** tab, click **+ (Add)** and enter the following Input property values:

    * Name: `PONumber`
    * Type: `String` (default)

3. Select the **Output** tab, click **+ (Add)** and enter the following Output property values:

    * Name: `SupplierName`
    * Type: `String` (default)

4. Click **OK**.

## Task 3: Define Open Application Action

This action tells the robot to open a web browser and navigate to the Oracle ERP Cloud sign-in page. We will use the robot connection created in the previous lab to pull the service URL and credentials.

1. Double-click on the **Open Application** action.

    | ![Select robot connections button](images/robot-designer_open-browser_edit.png " ") |
    |-|

2. In the **Open Browser** panel, keep the default values for **Name** and **Description**.

3. We will assign the target URL dynamically using a Robot Connection. On the **Input** tab, select within the **URL** field and click on the **Robot connections** icon ![Select robot connections button](images/robot-connections-button.png " ").

    The **Robot connections** side panel will appear, with the previously created robot connection.

4. Returning to the **Robot connections** side panel, expand the newly created Robot Connection. Next, drag the **URL** parameter to the matching field under the **Input** tab.

    ![Drag the URL parameter to the Input tab](images/robot-designer_open-browser_assign-url.png " ")

5. Under **Browser**, select the browser which will be used by the robot flow. Keep all other values as default.

6. Click **OK** when done, then **Save**.

## Task 4: Install the Robot Designer Extension

The **Oracle Robot Designer Extension** is a Chrome browser plugin that is used to target and record robot actions. This extension must be installed to continue with this workshop.

1. From the Robot designer, click on the red **Update** button

2. Click the button **Download browser extension**.
    ![Click extension Update button](images/robot-designer_update-browser-extension.png " ")

    The extension file (ZIP) is downloaded to the default downloads folder.

3. Navigate to the location where the ZIP file downloaded, such as your **Downloads** folder.

4. Extract the ZIP file in the same folder.

5. In Google Chrome, open the **Extensions** menu, and select **Manage Extensions**.

6. On the Google Chrome Extensions page, select **Load unpacked**.

7. Navigate to the folder containing the unzipped files, select the *target* folder, and click on **Select Folder**.

    This loads the Robot Extension in your Chrome browser.

    ![Show loaded Robot Extension in Chrome browser](images/robot-designer_loaded-browser-extension.png)

After installing the browser extension, we can start adding robot actions.

## Task 5: Add Login Action

Start the robot flow by adding the Login action.

1. On the Robot Designer canvas, hover over the **Open Application** action and click on the **+** which appears below it.
![Add Open Application action](images/robot-designer_open-application_add-action.png " ")

    A menu of available actions appears.

2. From the **Actions** tab, select the **Login** action.
![Add Login action](images/robot-designer_open-application_add-login.png " ")

    The **Login** action appears on the canvas.

3. On the **Login** panel, within the **Username** field, select **Robot connections**
![Select robot connections](images/robot-connections-button.png "=20x*"). On the Robot connections side panel, expand the created robot connection and drag the `username` parameter to the **Username** field.
![Assign username](images/robot-designer_login_assign-username.png "")

4. Repeat these steps by dragging the `password` parameter to the **Password** field.

    Next, we will specify input details for Username and Password actions.

5. In another browser window, open the sign-in page for the Oracle Fusion environment that the robot will work in. Here's an example environment URL:
`https://eeho.fa.us2.oraclecloud.com/fscmUI/faces/FuseWelcome`

6. Return to the **Login** panel on the Robot window, click within the **Username locator** field, and select **Target a page element** ![Target a page element button](images/robot-taget-page-button.png).

7. On the **Target a page element** panel, select the target browser window to the Oracle Fusion login page. The title will be `Sign In`.

    ![Robot input username locator select](images/robot-input_username-locator_select.png)

    This starts the design Targeting on the ERP Cloud login page. This component pops up at the bottom of the Fusion Application window:

    ![Robot design Targeting](images/robot-designer_targeting-on.png "")

8. On the Oracle Fusion login page, point to the `User ID` field where the robot will enter the user name. 
    > **Note**: When using the targeting component, wait until the target icon appears, the field turns green, and your mouse icon changes to a hand before selecting the UI element.

    ![Robot input username locator select](images/robot-designer_smart-record_select-user-id.png "")

    The Targeting maps the `User ID` UI element value to the **Username locator** field in the robot.

    ![Robot input username locator select](images/robot-designer_username-locator_mapped.png "")

9. Repeat the previous steps for the following fields:

    * **Password locator**: Select the `password` UI element.
    * **Submit locator**: Select the `Sign In` button that the robot clicks to sign in to the Oracle Fusion application.

    Your current (incomplete) flow should look as follows:

    ![Current flow until sign-in](images/robot-designer_flow_sign-in-complete.png " ")

10. Click **OK**.

11. Above the Robot canvas, click **Save**.






    This adds an action `Enter "User ID" Text` to the robot flow.

    > **Note:** When using the recorder, wait until the target icon appears, the field turns green, and your mouse icon changes to a hand before selecting the UI element.

    Next we set the **Value** field by mapping the **Username** input variable.

 **Target a page element** panel, check **Create target** option and select `Sign In`.

    This starts the recorder on the ERP Cloud login page.

6. On the **RPA Smart Recording** panel, click on **Begin Recording**.

    We will now select field elements to generate associated Actions in the robot flow.

7. 



## Task 6: Add Robot Actions using the Record option

Build the robot flow by adding actions using the recorder.

1. Open a new browser window and navigate to the login page of ERP Cloud. This is the URL value which was set in the web login panel.

    ![ERP Cloud login](images/robot-designer_erp-login.png " ")

2. Return to the browser tab running the robot designer. Select the **Open Application** action (don't double-click). Selecting the actions enables the record button. ![Record button enabled](images/robot-designer_record-button.png " ")

3. On the **Smart Record** panel, click **Select browser tab to target**.

    ![Select browser tab](images/robot-designer_smart-record_select-browser.png " ")

    This starts the recorder on the ERP Cloud login page.

4. On the **RPA Smart Recording** panel, click on **Begin Recording**.

    We will now select field elements to generate associated Actions in the robot flow.

5. Hover the mouse over the **User ID** field until it lights-up green, and select it.
![Select browser tab](images/robot-designer_smart-record_select-user-id.png " ")

    This adds an action `Enter "User ID" Text` to the robot flow.

    > **Note:** When using the recorder, wait until the target icon appears, the field turns green, and your mouse icon changes to a hand before selecting the UI element.

    Next we set the **Value** field by mapping the **Username** input variable.

6. On the **Action Details** panel, within the **Value** field, select the **Robot connections** icon ![Select robot connections button](images/robot-connections-button.png " "). On the **Robot connections** side panel, expand the created robot connection and drag the **username** parameter to the **Value** field.

7. For the **Test value** field, enter a valid EPR username. For example `calvin.roth`.

8. Click **Save**.

    > **Note:** We add valid test values to allow the login to work and move to the next screen in the browser.

9. Next, hover the mouse over the **Password** field until it lights-up green, and select it.

10. Map the robot connection **password** parameter to the **Value** field.

11. For the **Test value** field, enter a valid ERP password.

12. Click **Save**.

13. Next, hover the mouse over the **Sign In** button until it lights-up green, and select it.

14. On the **Action Details** panel, keep all values as default and click **Save**.

15. Return to the browser tab running the robot designer. Click **Save** in the robot designer.

    Your current (incomplete) flow should look as follows:

    ![Current flow until sign-in](images/robot-designer_flow_sign-in-complete.png " ")

> **Note:** When clicking a button or link in recorder mode, the following events occur:
    > 1. The operation is added as action to the robot flow.
    > 2. The browser performs the actual UI operation.

## Task 7: Add Robot ERP Actions using the Record option

Continue the robot flow by adding actions from ERP Cloud using the recorder. After sign-in in the previous task, you should now be on the ERP Cloud landing page.

1. From the top menu in ERP Cloud, click on **Procurement** when the icon changed to a target. In the **Action Details**, keep all values as default and click **Save**. This will add the action `Click "Procurement"` and move to the procurement element.

2. Click on **Purchase Orders** when the complete tile is shaded and changed to a target. In the **Action Details**, keep all values as default and click **Save**. This will add the `Click "Purchase Orders"` action and move to the purchase orders element.

3. On the **Overview** page, move to the right of the screen and select the **Tasks** icon when the icon changes to a target.
    ![Select Tasks icon](images/erp-cloud_select-tasks.png " ")

    In the **Action Details**, keep all values as default and click **Save**. This will add the `Click "Tasks"` action and display a side panel.

4. On the side panel, go to the **Orders** section and click on **Manage Orders** when the icon changes to a target. In the **Action Details**, keep all values as default and click **Save**. This will add the `Click "Manage Orders"` action and move to the Manage Orders page.

    Next, we will search for a specific Purchase Order by providing an order number.

5. Move to the **Order** field and select the UI element when the icon changes to a target. Enter the following values in the **Action Details**.

    * Name: `Enter "PO number" Text`
    * Value: In the field, click ![Select Flow button](images/action-details_po-number_flow-button.png " ") **(Flow Input/Output)** and select the **Input** property **PONumber**. Double-click the property to have it mapped to the **Value** field.
    * Test value: Enter a valid `PO Number` which will be used in the search query to pull an actual purchase order. Example: `US164712`

    ![PO Number action details](images/action-details_po-number.png " ")

6. Click **Save**.

7. Click on **Search** when the complete tile is shaded and changed to a target. In the **Action Details**, keep all values as default and click **Save**. This will add the `Click "Search"` action and display the search results containing the specified purchase order.

8. For the listed purchase order, move to the **Supplier** column and select the supplier name after the icon changes to a target. Enter the following values in the **Action Details**.
    * Name: `Click "Get supplier name"`
    * Action: Get Text
    * Save To: Select ![Select Flow button](images/action-details_po-number_flow-button.png " ") **(Flow Input/Output)**, switch to **Output** and double-click on **SupplierName**.

9. Click **Save**.

10. In the "Smart Recording" panel, click on ![Smart Recording stop button](images/smart-recording_stop-button.png " ") **(Stop recording)** to end the recording.

11. In the **Robot Designer**, click on **Save**.

12. Close the robot designer by clicking on the **< (Go back)** button on the top left of the screen.

13. For the selected robot, click on **...** and select **Add Environment Pool**.

14. In the **Add Environment pool**, select the existing environment pool and click **Add**.

    ![Smart Recording stop button](images/environment-pool_add.png " ")

    The status of your robot should change to **Configured**.

15. For the selected robot, click on **...** and select **Activate**.

## Acknowledgements

* **Author** - Ravi Chablani, Principal Product Manager - Oracle Integration
* **Last Updated By/Date** - Ravi Chablani, March 2024