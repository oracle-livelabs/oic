# Verify Care Request Creation in Oracle Fusion

## Introduction

After sending the HL7 message and triggering the Oracle Integration flow, the final step is to verify that the integration successfully created a Care Request in Oracle Fusion. Oracle Integration processes the incoming HL7 healthcare message, maps the required data fields, and invokes Oracle Fusion APIs to generate the corresponding Care Request record.

In this section, you will navigate to Oracle Fusion, locate the newly created Care Request, and validate that the data has been successfully transferred from the HL7 message into Oracle Fusion. This verification confirms that the end-to-end healthcare integration flow is functioning as expected

Estimated Time: 15 minutes

### Objectives

In this section, you will:

- Access the Oracle Fusion application
- Navigate to the Service Requests/Care Requests workspace
- Search for the newly created Care Request record
- Verify that the Care Request was successfully created by the integration
- Review the transferred healthcare/order details in the created record
- Confirm successful end-to-end execution of the Oracle Health EHR to Oracle Fusion integration flow

### Prerequisites

- All the previous labs completed successfully.

## Task 1: Log in to Oracle Fusion

1. Open a web browser.
2. Navigate to your Oracle Fusion Cloud URL.
3. Enter your credentials and sign in.

## Task 2: Navigate to Service Requests

1. From the Oracle Fusion home page, click the Navigator icon.
2. Navigate to Service > Service Requests

> **Note:** Depending on your Oracle Fusion environment, the menu may also appear under Customer Service or Service Workspace.

## Task 3: Search for the Newly Created Care Request

1. In the Service Requests page, use the search/filter options to locate the newly created record.
2. Search using one of the following criteria:
    - Recently Created Records
    - Patient/Customer Name
    - Subject/Title
    - Creation Date

## Task 4: Open the Care Request Record

1. Select the newly created Care Request from the search results.
2. Open the record details page

## Task 5:  Validate the Care Request Details

1. Review the record and confirm the following information is populated correctly:

    - Patient/Customer details
    - Order/Request information
    - Description/Notes from HL7 message
    - Creation timestamp
    - Status of the request

> **Note:** Ensure that the details match the data sent in the HL7 ORM/OMR message.

## Task 6: Confirm Successful Integration

If the Care Request is visible and contains the expected details, this confirms that:

    - Oracle Integration successfully received the HL7 message
    - The HL7 payload was transformed correctly
    - Oracle Fusion API call completed successfully
    - The end-to-end integration flow executed as expected

    You may now **proceed to the next lab**.

## Learn More

- [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)

## Acknowledgements

- **Author** - Subhani Italapuram, Technical Director, Partner Enablement, Oracle Integration
- **Last Updated By/Date** - Subhani Italapuram, Apr 2026
