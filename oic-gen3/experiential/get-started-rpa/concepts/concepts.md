# Concepts

## Introduction

Robots and integrations help you achieve the same business goals using different technologies. A robot performs UI-based automation, whereas an integration performs API-based automation. You can build both robots and integrations using Oracle Integration.

## Robot Concepts

The following concepts related to Robots will be covered during this workshop.

### Robotic Process Automation

 Robotic Process Automation (RPA) is a technology that allows for automation of mundane, tedious, rule based, error-prone, repetitive tasks that a large segment of an enterprise workforce has to deal with. As opposed to other flavors of Integration or Process/Task automation such as API or DB connector based integration/automation, RPA technology allows for creation of automation (robots) that simulates user actions on the application's user interface. For legacy system where APIs are not available or for systems where APIs are not accessible to the integrator, RPA is often the only automation solution.

RPA use cases are generally categorized by how the robots used – attended or unattended.

- **Attended Robots** are like virtual assistants that assist individual employees with front-office tasks to boost personal productivity. Often, attended robots interact with applications on the employee’s desktop.

- **Unattended Robots** automate back-office tasks and are invoked as part of larger end-to-end business process or integration flows. Unattended robots are just another technical option for connecting to systems of record – effectively like APIs.

### What is RPA in Oracle Integration 3?

RPA is available as a first-class feature in Oracle Integration 3 (OIC3). It provides a ubiquitous, low skill, and non-disruptive mechanism to connect to and operate on data sources. These data sources are interfaces that a user can interact with from their desktop. OIC-RPA provides a framework to connect to applications and data sources via a web browser interface.

## Projects

Projects are the hubs of all your automation work and the place to go when you want to design automation solutions, including integrations and robots. Each project can focus on a specific business objective, where select users are given access to project assets. Users who are on different teams and who have different skill-sets can collaborate on designated projects to meet their team objectives.

Projects provide convenient deployment and unified observability, allowing pre-defined teams to work together to build, deploy, and monitor integrations and robots.

## Connections

A robot connects to an application using a robot connection. You specify the parameters that you define in a robot connection using a robot connection type.

### Robot Connection Type

The robot connection types are similar to templates, and allow you to specify the parameters required for a robot connection.
ß
Unlike an integration, a robot doesn't need information about an application's security protocols or its APIs. A robot typically needs only a little information about the application or web page that it's connecting to, such as a URL and credentials. You list the fields that a robot needs to connect to an application in a robot connection type.

A robot connection type doesn't list the values of the fields, and it's not application specific. Therefore, you can base robot connections to different applications on the same robot connection type. For example, any robot connection that requires only a user name, password, and URL to access an application can use one of the predefined robot connection types.

### Robot Connection

Once the parameters that a robot needs in a Robot Connection Type have been specified, you specify values for the parameters in a robot connection. For example, parameter ```username``` is specified in the Robot Connection Type, and the value ```'jane.doe@example.com'``` is entered in the Robot Connection for that specific parameter.

## Environments

A Robot Environment is the computer or virtual machine where instances of your robots run. An Environment Pool is similar to a cluster and is a collection of computers or virtual machines that can run specific robots. You must associate each robot environment with exactly one environment pool.




## Terminology

| Term          | Definition    |
| ------------- |---------------|
| *RPA*  | A service that automates repetitive manual tasks involving humans  interacting with software systems. RPA accomplishes this automation by interacting with the software systems through the user interface in the same way as human users. |
| *Robot Project* | An organizational construct for managing the artifacts to perform a defined RPA automation. Project artifacts may include Flows, Flow Activities, Configurations, and Events. |
| *Robot Flow* | An orchestration of Robot Activities for the purpose of automating all or a portion of an interaction with a Client Application. |
|*RPA Adapter*| A Connectivity Service Adapter designed to discover, configure, and invoke robot automation. |
| *Robot Agent* | Communication channel between Robot Runtime and UI plane. |