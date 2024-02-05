# Setup

## Introduction

This lab walks you through the process of setting up a Robot environment to create Robot flows. This includes the installation of the robot agent and its dependencies.

### About Robot Environments

The host where a robot runs, typically a Linux or Windows virtual machine (VM), is called an environment. It is common to group these VMs logically into environment pools to enable load balancing in production.

For this workshop, we will complete the steps to setup a robot on your local machine.

Estimated Lab Time: 15 minutes

### Objectives

In this lab, you will:

* Install JAVA Runtime (optional)
* Obtain Robot Connectivity details
* Download and Install the Robot Agent
* Run the Robot Agent

### Prerequisites

This lab assumes you have:

* An Oracle Cloud account
* Successfully completed all previous labs

## Task 1: Install JAVA Runtime

The Java Runtime Environment (JRE) is software that Java programs require to run correctly. JRE is required to run the robot agent.

1. Verify if a JRE is pre-installed on the host machine by running the below command.

    For Linux and macOS, run this command in the **Terminal**. 

    For Windows, run this command in the **Command Prompt (CMD)**.

    ```java
    java --version
    ```

    If a similar response is displayed in the terminal, then a JRE is already installed and you can proceed to **Task 2**.

    ```Java(TM) SE Runtime Environment (build [your-build-number])```

2. If there is no JRE listed in the response, then one needs to be installed. Follow this link to download the latest JRE the applies to your system platform (Linux, macOS or Windows) and processor:

    https://www.oracle.com/java/technologies/downloads

3. Follow the **Installation Instructions** on the Java Downloads page.

## Task 2: Obtain OCI access details

Configure connection security between the robot and designated OIC instance. This includes obtaining the security credentials from the tenancy and designated OIC instance. The gathered information will be required in the next task.

1. Start from the Application Integration From the OCI console, navigate to 


## Task 3: Download and Install the Robot Agent

The Robot Agent must be downloaded and installed on your local host. The agent is downloaded from the Oracle Integration 3 console. During installation, you associate the agent with the OIC 3 instance where the robot flow will be built and run.

1. In the left Navigation pane, click **Design**, followed by **Agents**.

2. On the top right corner of the window, click on **Download**. Then, select **Robot Agent**.
![Download Robot Agent](./images/download-robot-agent.png ' ')

    You should receive a confirmation about the agent getting downloaded.
    ![Download Robot Agent notification](./images/download-robot-agent-notification.png ' ')

3. Once the download has completed, navigate to the designated folder on your local machine to obtain the agent installation file ```rpa_agent.zip```. The default location is typically the **Downloads** folder.

4. Choose a folder where you would like to move the downloaded ```.zip```. From there, unzip the RPA agent file.

5. Open the ```InstallerProfile.cfg``` file located in the agent folder using a text editor (e.g. Notepad, Sublime, etc).



## Task 3: Run Robot Agent





