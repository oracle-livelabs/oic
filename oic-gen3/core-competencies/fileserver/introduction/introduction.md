# Introduction

## About this Workshop

This workshop will walk you through the steps to create an end-to-end integration of reading a file from the File Server and inserting the data set in an Oracle Autonomous Transaction Processing(ATP) Table leveraging out of the box adapters.
- We shall leverage the features published on OIC 25.04 like File Server Events to trigger the integration flow and AI-driven SQL generation (generates SQL queries from natural language prompts, reducing manual effort) to insert the data into ATP.

    ![Integration Architecture](images/oicfileevent.png)

The architecture shows a horizontal integration flow using Oracle Integration Cloud (OIC). Files are uploaded to the OIC Embedded SFTP Server, triggering a File Event in OIC. The file content is read using the Stage File Action, then passed through Data Mapping & Transformation. Finally, the processed data is inserted into an Oracle ATP Database Table using the ATP Adapter.

Estimated Time: 60 minutes

### Objectives

In this workshop, you will learn how to:

- Enable the File Server in Oracle Integration 3 instance.
- Setup required artifacts to complete the live lab
- Create a Project
- Create Connections
- Design an Event based Integration Flow
- Test and Observe Integration Flow

### Prerequisites

- Oracle Integration Instance.
- Oracle Autonomous Database Instance in Oracle Cloud Infrastructure
- A Chrome browser.

You may now **proceed to the next lab**.

## Learn More

- [File Server Events](https://blogs.oracle.com/integration/post/oic-file-server-events)

## Acknowledgements

- **Author** - Subhani Italapuram, Technical Director, Oracle Integration Product Management
- **Last Updated By/Date** - Subhani Italapuram, May 2025
