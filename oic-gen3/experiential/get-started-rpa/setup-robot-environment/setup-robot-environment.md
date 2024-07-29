# Setup Robot Environment

## Introduction

This lab walks you through the process of setting up a Robot environment to create Robot flows. This includes the installation of the robot agent and its dependencies.

### About Robot Environments

The host where a robot runs, typically a Linux or Windows virtual machine (VM), is called an environment. It is common to group these VMs logically into environment pools to enable load balancing in production.

For this workshop, we will complete the steps to setup a robot on your local machine.

Estimated Lab Time: 15 minutes

### Objectives

In this lab, you will:

* Install JAVA Runtime (optional)
* Install and configure the Robot Agent
* Start the Robot Agent

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

## Task 2: Install and configure the Robot Agent

The Robot Agent must be downloaded and installed on your local host. The agent is downloaded from the Oracle Integration 3 console. During installation, you associate the agent with the OIC 3 instance where the robot will be built and run.

1. In the left Navigation pane, click **Design**, followed by **Agents**.

2. On the top right corner of the window, click on **Download**. Then, select **Robot Agent**.
![Download Robot Agent](./images/download-robot-agent.png ' ')

    You should receive a confirmation about the agent getting downloaded.
    ![Download Robot Agent notification](./images/download-robot-agent-notification.png ' ')

3. Once the download has completed, navigate to the designated folder on your local machine to obtain the agent installation file ```rpa_agent.zip```. The default location is typically the **Downloads** folder.

4. Choose a folder where you would like to move the downloaded ```.zip```. From there, unzip the RPA agent file.

5. Open the ```InstallerProfile.cfg``` file located in the agent folder using a text editor (e.g. Notepad, Sublime, etc) and enter a value for the **DISPLAY_NAME** attribute without spaces. For example, `DISPLAY_NAME=LiveLabs-RobotAgent`

    Keep all other values as default.

6. **Save** and **Close** the configuration file.

## Task 3: Start the Robot Agent

You must start the robot agent from the computer on which it is installed. If a robot agent isn't running, the agent can't run any robots.

1. Return to the unzipped RPA Agent folder.

2. Locate the `.jar` file and note the version number. It should be in the following format: `orpa-agent-x.x.xx.jar`

3. To run the command:

    * On Linux/MacOS: Open the **Terminal** app, and navigate to the location of the unzipped folder.  
    * On Windows: Right-click on the unzipped folder and select **Open in Terminal**

4. Run the following command in the terminal:

    ```java
    java -jar orpa-agent-x.x.xx.jar
    ```

    Replace x.x.xx with the actual version number (e.g. `0.1.77`)

5. The robot agent is running successfully when you see below message in the terminal:

    ```java
    INFO  - Requesting messages from ControlRoom`
    ```

You have successfully completed this lab.

## Acknowledgements

* **Author** - Ravi Chablani, Principal Product Manager - Oracle Integration
* **Last Updated By/Date** - Ravi Chablani, June 2024