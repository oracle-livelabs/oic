# Use Cases - Read ONLY

## Introduction

In this section, this Live Lab demonstrates key Oracle Fusion Cloud SCM to Oracle Health EHR integration use cases using Oracle Integration and the Oracle Health accelerator.

The use cases focus on healthcare inventory synchronization, item data management, transaction processing, and procurement automation.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:

- Understand the use cases covered as per the accelerator.

### Prerequisites

Before starting this lab, ensure that:

- Completed all the previous labs successfully

## Use Case 1: Synchronize Item Master Data

1. *Objective:* Synchronize item master information from Oracle Fusion Cloud SCM to Oracle Health EHR.
2. *Business Scenario:*: Healthcare organizations require consistent item definitions across SCM and clinical systems to support procurement, inventory, and supply operations.
3. Flow

    1. Item data is created or updated in Oracle Fusion Cloud SCM.
    2. The Product Hub publication process generates item XML payloads.
    3. Oracle Integration retrieves the files from Oracle WebCenter Content.
    4. Item data is transformed and mapped.
    5. Data is transferred to Oracle Health EHR.

4. Verify:
    - Item number
    - Description
    - Organization mapping
    - UOM mapping
    - Item status

## Use Case 2: Synchronize Item Locations and Locators

1. *Objective:* Synchronize subinventory and locator information between Oracle Fusion Cloud SCM and Oracle Health EHR.
2. *Business Scenario:* Healthcare inventory systems require accurate stock locations and locator mappings for inventory visibility and operational efficiency.
3. Flow
    1. Subinventories and locators are configured in Oracle Fusion Cloud SCM.
    2. Synchronization processes generate location payloads.
    3. Oracle Integration transforms the location mappings.
    4. Oracle Health EHR receives the location data.
4. Verify:
    - Subinventory mappings
    - Locator mappings
    - Organization-location relationships

## Use Case 3: Synchronize Item Costs

1. *Objective:* Synchronize item cost information from Oracle Fusion Cloud SCM to Oracle Health EHR.
2. *Business Scenario:* Healthcare systems require updated item costs to support purchasing decisions and inventory valuation.
3. Flow
    1. Item costs are updated in Oracle Fusion Cloud SCM.
    2. Cost data is extracted during synchronization.
    3. Oracle Integration transforms cost information.
    4. Cost data is transferred to Oracle Health EHR.
4. Verify:
    - Cost values
    - Currency codes
    - Organization mappings

## Use Case 4: Inventory On-Hand Synchronization

1. *Objective:* Update inventory on-hand quantities based on Oracle Health transactions.
2. *Business Scenario:* Healthcare usage transactions should update inventory balances in Oracle Fusion Cloud SCM.
3. Flow
    1. Transactions are completed in Oracle Health.
    2. Oracle Integration retrieves transaction details.
    3. Inventory transactions are mapped.
    4. Oracle Fusion Cloud Inventory Management is updated.

4. Verify:
    - On-hand quantity updates
    - Transaction mappings
    - Inventory balances

## Use Case 5: Bill-Only Requisition Creation

1. *Objective:* Automatically create bill-only requisitions for non stock healthcare items.
2. *Business Scenario:* Healthcare organizations frequently process bill-only items that must create procurement requests automatically.
3. Flow
    1. Oracle Health generates a non stock transaction.
    2. Oracle Integration validates the transaction.
    3. Procurement requisitions are created in Oracle Fusion Cloud Procurement.

4. Verify:
    - Requisition creation
    - Procurement business unit
    - Charge account mapping

    You may now **proceed to the next lab**.

## Learn More

* [Configure the Accelerator](https://docs.oracle.com/en/cloud/saas/supply-chain-and-manufacturing/26b/fasih/configure-the-accelerator.html#u30252184)

## Acknowledgements

* **Author** - Subhani Italapuram, Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, May 2026
