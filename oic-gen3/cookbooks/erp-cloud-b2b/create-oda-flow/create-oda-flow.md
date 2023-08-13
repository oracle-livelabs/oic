# Create ODA Conversation Flow

## Introduction

In today's rapidly evolving business landscape, the ability to seamlessly interact with and gain insights from complex processes is a significant advantage. Oracle Integration, with its powerful capabilities, enables the creation of streamlined workflows that automate and optimize critical business to business operations. In this tutorial, we're about to embark on a journey that goes beyond automation – we'll explore how Oracle Digital Assistant (ODA) can be seamlessly integrated to elevate your Purchase Order (PO) management to new heights.

Imagine a scenario where you've already mastered the creation of a dynamic PO change order workflow using Oracle Process Automation (OPA). Now, take it a step further: picture having an intelligent conversation with your application to inquire about purchase details and status. That's precisely what we'll achieve through the integration of Oracle Digital Assistant.

Estimated Time: 40 minutes

### Objectives

In this workshop, you will create a skill that can be used for interactions with a ERP Cloud, to check the Purchase Order Details and Status. As part of this process, you will:
* Define intents, utterances, entities.
* Design a conversation flow by using the Visual Flow Designer.
* Validate, debug and test your skill.

### Prerequisites
- Access to Oracle Cloud Account and Oracle Digital Assistant

## Task 1: Create a Skill

 1. This task assumes you are already signed in into the Oracle Cloud account and are able to navigate to the already provisioned Oracle Digital Assistant instance. With this as a prerequisite, navigate to the Oracle Digital Assistant UI in a browser, Click on the ![hamburger Icon](images/hamburger.png) to open the side menu.

2. Click **Development** and then select **Skills**.
  ![select skills](images/select-skills.png)


3. Click ![hamburger Icon](images/hamburger.png) again to collapse the side menu.

4. Click the **+ New Skill** button.
  ![new skill](images/tile-new-skill.png)

5. Enter the following details in the create skill dialoge window that appears as below.
    - **Display Name**:
          Purchase Order Assistant  
    - **One-Sentence Description**:
          A unique skill that assists users with the Status of Purchase Orders.  
    - **Skill Version**:
          1.0</copy>
    - **Platform Version**:
        Choose the latest from the drop down, ***23.06(Latest)***
    - **Dialoge Mode**:
        Please, Select the Visual radio button
    - **Primary Language(Natively-Supported)**:
        Please, Select ***English*** from the dropdown

      ![create-skill](images/create-skill.png)

Here's a reference of details entered in the window above, after entering details please click the **Create**  button


you have successfully created a skill now you can proceed to the next task

## Task 2: Create Intents

1. After creating a skill, the designer will open on the Intents ![intents icon](images/left-nav-intents.png) page. Click on the **+ Intent** button and create your first Intent. Lets call this intent as Greetings.

2. Select and copy all of the example sentences below to your clipboard:

```
<copy>
Hello there! How's it going?
Hey! Can you help?
Hi there! New user here.
Hello! What's your function?
Hi there! I'm lost.
Hey, any guidance available?
Hello! Need assistance please.
Hi there! What's possible here?
Hey! How does this work?
Hi there! Who are you?
Hello! Where do I start?
Hi there! What can I do?
Hey! I'm a bit confused.
Hello! Can you explain?
Hi there! Any tips?
Hi
Hello
Hello good morning!
Hello there, how are you?
Hi, how are you?
</copy>
```

3. Add them to the Utterences to Add section, click on the Advanced input mode and paste all the above sentences here.
     ![adding-utterences](images/add-utterences.png)

4. Now hit the **Create** button.
   ![create-button](images/create-utterences.png)    

5. Repeat the above steps for another Intent by naming the intent as  **Purchase Order** and add the below list of utterences to that particular intent and click on the **Create** button as shown below:

```
<copy>
how to know the status of my purchase order
I would like to know the status of my order
Order Status
please help me know the status of my purchase order
status of my order
status of my purchase
what is the status of my order
what is the status of my purchase order
</copy>
```

![purchase-order-intent](images/purchase-order-intent.png)

6. Train your Intents , by clicking on the **Train** on the right side of the page, click **Train Tm** and Submit. wait  for the training to complete, this may take few minutes.

     ![train-intents](images/train-intents.png)

## Task 3: Design the Dialog flow
In this section you will create a dialogue flow for Greetings and the Purchase Order Intents.

The conversation dialog looks something like below
![PO Bot Flow Dialog View](images/po-bot-flow-dialog-view.png)

We will create Two conversation dialogues.
1.  Greetings Conversation Flow - To greet the user and ask for what he/she looking for?

2. Purchase Order Conversation - Ask for the order number, verify and get the details of the PO.

**Create the Greetings conversation dialogue flow:**

1. Click on the Flow ![dialogue-flow](images/dialog-flows-icon.png) icon  on the left side of the page.

2. Click on **Add Flow** button.

  ![add-flow-button](images/add-flow-button.png)

3. In the **Create Flow** dialogue box enter the name of the flow  **Greetings** and hit the **Create** button, make sure to check the box "**Open created flow afterwards**".

 ![create-greeting-flow](images/create-greeting-flow.png)

4. Click on the **Start** , you will see three dots appear like this "**...**", click on the dotes and popdown shows up with text on it as "add start state", click on it to select a template.

 ![add-start](images/add-start-state.png)

5. Select the **Send Message** template and add the **Name** as ***welcomeMessage*** and hit the **Insert** button as shown in the picture below.

 ![select-send-message](images/select-send-message-template.png)

6. Then a side window opens up with the properties of the template to fill, under the **Component** tab , Please add the below text:

```
<copy>
Hello ${profile.firstName}, Welcome to the Purchase Order Assistant! How can I assist you today?   
</copy>
```


**Create the Purchase Order conversation dialogue flow:**

1. Click on the Flow ![dialogue-flow](images/dialog-flows-icon.png) icon  on the left side of the page.

2. Click on **Add Flow** button.

   ![add-flow-button](images/add-flow-button.png)

3. In the **Create Flow** dialogue box enter the name of the flow  **PurchaseOrderConversationFlow** and hit the **Create**
button, make sure to check the box "**Open created flow afterwards**".
   ![purchase-order-flow](images/purchase-order-conversationflow.png)

4. Once Visual Flow design editor opens, click on the **Configuration** tab and add two variables on the **Flow level** in the variables section by click on the **+ Add Variable** .   

   ![add-variable](images/add-variable.png)

5. Enter the following details to add variables one by one and hit **Apply** button.

**Name**:   OrderNumber
**Description**:  Purchase Order Number
**Variable Type**: String
![order-number-variable](images/order-number-variable.png)

6. Repeat the step above for adding another variable with the details mentioned below

**Name**:   PurchaseOrderDetails  
**Description**:  Details of the Purchase Order
**Variable Type**: Map
![purchase-order-details-variable](images/purchase-order-details-variable.png)

7. Click on the **Flow** tab to start building the conversation flow.

    ![flow-tab](images/click-on-the-flow-tab.png)

8. on the **Start** box click on the three dots **...** and then click on **add start state**

     ![add-start](images/purchase-order-add-start.png)

9. A window opens with options to select a template from. Please select the **Ask Question** template and fill the details as shown in the screenshot below and then hit the **Insert** button:

    ![ask order number](images/ask-question-template.png)

10. A side window pane opens up for this select template to fill all the details, click on the **Component** tab and enter the below details:

**Question**  :  Absolutely! To better assist you, could you please provide your Order Number?
**Variable**: select the *Order Number* from Flow Variables
     ![ask order number component](images/ask-order-number-component.png)

11. Click on the **Transition** tab and select **Add State ...**

      ![transition add state](images/transition-add-state.png)

12. In the template select **User Messaging** and then **Create Text Menu** and select **Create Action Menu**, in the  **Name** enter text **validateOrderNumber** and then hit the **Insert** button.

       ![validate-order-number](images/validate-order-number.png)

13. click on the **Component** tab and then click on the **Edit Response Items** button.

      ![edit-response-items](images/validate-order-number-component.png)

14. Copy the below details, paste it in the editor and hit the **Apply** button. This is a YAML code for it to work the indentation needs to be correct, make sure the indentation matches with the screenshot below:
        ```
        <copy>
         responseItems:
            - text: "Before we proceed, kindly verify, if the entered Order Number, ${OrderNumber} is correct!"
              type: text
              actions:
                - payload:
                    variables:
                      menuAction: "Yes"
                    action: "Yes"
                  label: "Yes"
                  type: postback
                  keyword: "1"
                - payload:
                    variables:
                      menuAction: "No"
                    action: "No"
                  label: "No"
                  type: postback
                  keyword: "2"
                  </copy>
                  ```

  ![yaml-code](images/yaml-code.png)

15. Click on the **Transition** tab and click on the **+** button besides **Action**

    ![adding-action](images/adding-action.png)

16. we are trying to define next state for the action buttons **Yes** and **No** , on the left box type **Yes** and on the right box pick **add state...** option from the dropdown.

    ![add-state-for-yes-action](images/adding-state-for-yes-action.png)

17. In the **Add State** window choose the **Variables** template

     ![add-variable](images/add-variable-template.png)

18. select the **Reset Variables** template , name it as **yesaction_resetVariable** and hit the **Insert** button.

     ![reset-variable](images/reset-variable.png)


19. once the **Reset Variable** component opens up select the **Purchase Order Details** variable in the **Flow variables** section.

    ![reset-purchase-order-detail](images/reset-purchase-order-detail.png)


20. Repeat steps 16-19 for **No** action and this time reset both the Flow variables **Order Number** and **Purchase Order Details**
    ![reset-both-variables](images/reset-both-variables.png)
    The Purchase order conversation flow designed so far
    ![PO Conversation flow Reset Variables](images/po-conversation-flow1.png)



21. Now come back to **yesaction_resetVariable**, click on the **Transition** tab and select the **add state...**

    ![yes-action-add-state](images/yes-action-add-state.png)


22. once the **add state** window opens, scroll down and select the **Service Integration** section.

    ![yes-action-service-integration](images/yes-action-service-integration.png)

23. After clicking that section scroll down through the list and look for **Call REST Service**, name it **callERPAPI** and hit the **Insert** button

   ![call-erp-api](images/call-erp-api.png)

24. Click on the **Component** tab and add the following details:

      - **REST Service** : rom the drop down select the api **ERP\_PO\_API**.
      - **Method**: GET
      - **Parameters**: Click on the **+** button and add the below details

       **1. Sold to legal Entity**
          - **Key**: sold\_to\_legal\_entity
          - **Value**: US1 Legal Entity
          - **Type**: Select **Query** from the dropdown and click on the ![right-icon](images/right-icon.png) to save the variable details.

        **2.Order Number**
        add second parameter value as below
         - **Key**: orderNumber
         - **Value**: ${OrderNumber}
         - **Type**: Select **Path** from the dropdown and click on the ![right-icon](images/right-icon.png) to save the variable details.
         - **Result Variable Service** : select the Flow variable **PurchaseOrderDetails** from the dropdown.
         ![Call ERP API Component](images/callerp-final1.png)
         ![Call ERP API Transitions](images/callerp-final2.png)

25. After the variables are successfully added in **Component**, select the **Transitions** tab, under the **Next Transition** select **Add state**
    ![Transition Rest Next State](images/transition-rest-next-state.png)

26. In the **Add State** window that opens up select the **Flow Control** section and navigate to **Switch** template and select it, name it as **determineIfValuePresent** and hit the **Insert** button.

  ![add-switch-component](images/add-switch-component.png)

27. Select the **determineIfValuePresent** In the **Component** tab under the **Expression** editor add the below free marker expression.

```
<copy>
${PurchaseOrderDetails.value.responsePayload.ordernumber?hasContent?then('success','failure')}
</copy>
```            

    ![free-marker-expression](images/free-marker-expression.png)

28. Go to the **Transition** tab , under the **Next Transition** section select the **Add State** from the dropdown.

 ![next-transition](images/next-transition.png)


29. when the **Add State** opens up, select the **Send Message** template and name it as **outputFailure** and hit the **Insert** button.

  ![output-failure](images/output-failure.png)

30. In the **outputFailure** window, go to the **Component** tab and copy the below message and paste it in the editor.

      Unfortunately, we couldn't locate any records matching the provided Order Number: ${OrderNumber}.


    ![output-failure-final](images/output-failure-final.png)     

31. Now go to the **determineIfValuePresent** state and click on the **Transitions** tab , then click on the **+** icon near the **Action** and add the **Action Name** as **success** and for **Transition To** select add state again, once the add state window opens select the **Send Message** template and name it as **api Response** and hit the **Insert** button.

32. In the **apiResponse** pane, under the **Component** tab , copy the below message and paste it.

```
<copy>
The Status is "${PurchaseOrderDetails.value.responsePayload.status}"

Please find the Order details below:

Order Number:  "${PurchaseOrderDetails.value.responsePayload.ordernumber}"
Description:   "${PurchaseOrderDetails.value.responsePayload.description}"
Supplier:   "${PurchaseOrderDetails.value.responsePayload.supplier}"
Creation Date:   "${PurchaseOrderDetails.value.responsePayload.creationDate}"
Total Amount :   "${PurchaseOrderDetails.value.responsePayload.totalAmount}"
Sold to Legal Entity:   "${PurchaseOrderDetails.value.responsePayload.sold_to_legal_entity}"
Letter of Credit Id:   "${PurchaseOrderDetails.value.responsePayload.locId}"
</copy>
```

33. After this, click on the **Transitions** tab , under the **Next Transition** , click on **add state** and navigate towards the **resetVariables** template, name it as **resetVariables** and hit then **Insert** button.

    ![apiresponse-transition](images/apiresponse-transition.png)

34. In the **resetVariables** pane, select both flow variables **OrderNumber** & **PurchaseOrderDetails** to reset.

     ![reset-variables-both](images/reset-variables-both.png)
    The conversation flow designed so far
    ![PO Conversation Flow](images/po-conversation-flow2.png)


35. Click on the **Transitions** tab and under the **Next Transition** select **add state** and follow this path  **User Messaging>>Create Text Menu>> Create Action Menu**, name it as **anotherOrderNumber** and hit the **Insert** button. In the **Component** tab click on the **Edit Response Items** and copy the below text add the text and hit on the **Apply** button.


```
<copy>
         responseItems:
           - text: Are you interested in checking the Status of a different Order Number?
             type: text
             actions:
              - payload:
                  variables:
                    menuAction: "Yes"
                  action: "Yes"
                label: "Yes"
                type: postback
                keyword: "1"
              - payload:
                  variables:
                    menuAction: "No"
                  action: "No"
                 label: "No"
                 type: postback
                 keyword: "2"
                 </copy>
                 ```
The above code is a **YAML** code make sure the indentation matches with the screenshot below:
  ![another-order-number](images/another-order-number-yaml.png)

36. Now click on the **Transitions** tab and under the **Next Transition** drop down select the **askOrderNumber** state.

  ![select-askordernumber-state](images/select-askordernumber-state.png)

37. under the **Action** section, add **Action Name** as **No** and in the **Transition To** select **add state** and select the **Send Message** template and name it as **ThankYouMessage**. Go to the **Component** tab is opened copy the below message and paste it in the editor.

```
<copy>
Thank you for your time. It was a pleasure to assist you. Please feel free to reach out any time you need more assistance with your Purchase Order, until then, Goodbye and takecare!
</copy>
```

  ![askanotherordernumber-noaction](images/askanotherordernumber-noaction.png)

  ![thankyoumessage](images/thankyoumessage.png)

38. Now lets go to the **outputFailure** state and  click on the **Transitions** tab in the **Next Transition** dropdown select **resetVariables** state.

  ![outputfailure-nexttransition](images/outputfailure-nexttransition.png)

39. Finally, lets go back to the **noaction_resetVariable** state and click on the **Transitions** tab in the **Next Transition** dropdown select the **Add State...** state.
  ![No Action Reset Variable](images/noaction-resetvariable-addstate.png)

40. In the **Add State** window Select Template **Ask Question** and name it as *reEnterTheCorrectOrderNumber*. Click **Insert**.
  ![ReEnter Correct Order](images/ask-question-addstate.png)

41. Go to the **Component** tab, copy the below sentence and paste it in the editor, then under the variables select the **OrderNumber** variable in the **Flow** scope
  ![ReEnter State Component](images/reenter-state-component-details.png)

42. Click on **Transitions** tab and Select **Next Transition** as *callERPAPI*
  ![Reenter Transition](images/reenter-transition.png)

43. Your final conversation flow should look as below:
    ![PO Conversation Flow Final](images/final-flow.png)

44. Next, go head and click on the **Main Flow** tab under the **Flow Designer** section. we need to map the conversation design flow the appropriate intents for that you need to create an **Intent Event Handler**. In the Main flow window expand the **Intent Events** section and click on the **+** icon besides it. A window opens up for mapping the Intent with the appropriate mapped flow, make sure to match **Greetings** Intent with **Greetings** mapped flow and hit the **Create** button. Repeat the same for **Purchase Order** Intent to map it with **PurchaseOrderConversationFlow**

   ![Map Intent to PO Flow Add](images/map-intent-to-flow.png)

   ![Map Intent to PO Flow ](images/map-intent-to-flow-po.png)

45. The final mappings should look like below. With this you have successfully designed the conversation flow for Purchase Order Assistant, you can now proceed to the next Task.

   ![Final Intent Mappings](images/final-mappings.png)

## Task 4: Test your Skill

In this section we will just test the happy path scenario of the conversation dialogue flow we built in the previous section.

  1. Click on the **Validate** button on the top to make sure there are no errors.

     ![validate](images/validate.png)

  2. Then click on the **Preview** button to Test the bot.

     ![preview](images/preview.png)

  3. **Conversation Tester** window opens up and in the **Type Here** section type "Hi" and hit enter, the bot should respond with a Greeting message as shown in the screenshot below.

     ![conversation-tester-hi](images/conversation-tester-hi.png)

  4.  Then enter the sentence **Purchase Order Status** and hit enter, you should see the bot asking for you to enter the "Order Number " as below:

     ![conversation-po](images/conversation-po.png)

  5. Then enter the order number created as part of previous lab and then click on **Yes** the bot returns with details of the order number and asks if you would like to check status of another order number,  click on **No** to see the bot responding with "Thank you" message.

    ![conversationend-part1](images/conversation-end-part1.png)

    ![conversationend-part2](images/conversationend-part2.png)

**Congratulations** on successfully completing the Oracle Digital Assistant (ODA) tutorial, where we explored its impact on Purchase Order (PO) management. Let's summarize the key takeaways:

1. **Effortless Conversations:** Through ODA integration, you've enabled intuitive interactions. Users can effortlessly engage in natural language conversations to inquire about PO details and statuses.

2. **Enhanced User Engagement:** ODA has elevated user engagement by simplifying access to critical information, making the user experience more streamlined and engaging.

3. **Real-Time Insights:** ODA offers instant access to real-time PO updates, aiding data-driven decisions and timely actions.

4. **User-Centric Design:** The integration enhances user experience by allowing users to bypass complex navigation and interact naturally with the application.

5. **Unified Workflow:** Your integrated solution seamlessly combines initiating change orders, querying details, and monitoring progress in one unified application.

6. **Future Potential:** This tutorial offers a glimpse of ODA's potential; there are numerous opportunities for its integration into various business processes.

As you move forward, the insights gained here will empower you to optimize PO management. Oracle Digital Assistant's capabilities have the potential to reshape how your organization interacts with applications and processes. By implementing these features effectively, you can drive efficiency and informed decision-making. Thank you for joining us on this journey. The possibilities are vast; embrace ODA's capabilities to propel your organization toward a future marked by enhanced productivity and meaningful interactions.

## Learn More
* [Learn Oracle Digital Assistant](https://docs.oracle.com/en-us/iaas/digital-assistant/index.html)

## Acknowledgements
* **Author** - Vijaya Vishwanath, Sr. Cloud Solution Engineer
* **Last Updated By/Date** - Kishore Katta, August 2023
