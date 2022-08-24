# Lab 3 : Data Transfer from 8x8 Jitsi Application to Fusion Application

## Introduction

This lab will walk you through the steps to implement data transfer from 8x8 Jitsi video conference platform to Fusion application

Estimated Time: 30 minutes

### Objectives

You will execute the following:
- Oracle Integration Cloud implementation
- JaaS (Jitsi as a Service) configurations.

### Prerequisites
This lab assumes you have:
- Completed all the previous labs.
- https://www.ateam-oracle.com/post/trigger-oic-integration-using-oauth - This blog covers the configuration steps for triggering OIC interfaces using Oauth 2.0.

## Task 1: Oracle Integration Cloud implementation



## Task 2: JaaS (Jitsi as a Service) configurations

1. Login to https://jaas.8x8.vc

2. Click **Webhooks** > **Add endpoint**.

 | **Element**        | **Value** |       
 | --- | ----------- |
 | Endpoint URL | `enter the oic url created in the previous step`   |
 | Authorization header  | `Bearer tokenvalue (generated from IDCS application)`|
 | Event | `ROOM_CREATED`|

Click **Add endpoint**

3. Launch the 8x8 video app from the HR Service Request Page through Start Meet link and Join the metting.

4. You may notice the OIC instance are created that are triggered from the webhook configuration created in the previous step.


## Acknowledgements

* **Author** - Subburam Mathuraiveeran, Senior Cloud Engineer, Oracle North America Cloud Engineering
* **Last Updated By/Date** - Subburam Mathuraiveeran, Aug 2022
