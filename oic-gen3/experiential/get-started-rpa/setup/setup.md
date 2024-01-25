# Setup

## Introduction

This lab walks you through the process of setting up a Robot environment to create Robot flows.

### About Robot Environments

The host where a robot runs, typically a Linux or Windows virtual machine (VM), is called an environment. It is common to group these VMs logically into environment pools to enable load balancing in production.

For this workshop, we will complete the steps to setup a robot on your local machine.

Estimated Lab Time: 15 minutes

### Objectives

In this lab, you will:

* Install JAVA Runtime and RCC tool
* Setup the Robot Agent
* Run the Robot Agent

### Prerequisites

This lab assumes you have:

* An Oracle Cloud account
* Successfully completed all previous labs

## Task 1: Install JAVA Runtime

The Java Runtime Environment (JRE) is software that Java programs require to run correctly. This is required to run the robot agent.

1. Verify if you already have JRE installed. Type the following command:

```
java --version
```




## Task 2: Install RCC tool

RCC is a command-line tool that allows you to create, manage, and distribute Python-based self-contained robots.

## Task 3: Setup the Robot Agent

You will download the Robot Agent from the Oracle Integration 3 console, then proceed to configure and install it on your local machine.

1. In the left Navigation pane, click **Design**, followed by **Agents**.

2. On the top right corner of the window, click on **Download**. Then, select **Robot Agent**. 
![Download Robot Agent](./images/download-robot-agent.png ' ')

    You should receive a confirmation about the agent getting downloaded.
    ![Download Robot Agent notification](./images/download-robot-agent-notification.png ' ')

3. Once the download has completed, navigate to the designated folder on your local machine to obtain the agent installation file. The default location is typically the **Downloads** folder.

4. Choose a folder where you would like to move the downloaded ```.zip```. From there, unzip the RPA agent file. 

5. Open the ```InstallerProfile.cfg``` file located in the agent folder using a text editor (e.g. Notepad, Sublime, etc). 



## Task 4: Run the Robot Agent





