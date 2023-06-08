# Cloud Native WebApp Testing: Squid VPN server
Cloud-native web app assessment and simulation tool for testing redundancy, resiliency, and least privilege of a Squid VPN server.


## Squid VPN Web Application

This project simulates testing a Squid VPN Web Application to evaluate its cloud-native characteristics. The application is designed to exhibit traits like redundancy, resiliency, and least privilege. It provides functionality for managing pods, scaling the application, checking status, and testing user privileges.

## Running the application

**1) Starting the server and checking the status of pods.**<br><br>

![Screenshot from 2023-06-08 21-06-28](https://github.com/vexecute/Cloud-Native-Web-App-Testing-Squid-VPN/assets/92919686/291f69a5-aa34-4db2-b0f6-c374214b6ae8) <br>

- you can see that there are four different pods/processes running. You can also scale more pods. Since the default is 4 it is displaying four pods. <br><br>

**2) Terminating or Killing a pod**<br><br>

![Screenshot from 2023-06-08 21-18-06](https://github.com/vexecute/Cloud-Native-Web-App-Testing-Squid-VPN/assets/92919686/99bb0f8c-13a6-43f8-b5aa-3a2922a3bec8) <br>

- here im killing a particular pod to check if the app is both redundant and resilient. <br>
- after killing the particular pod, you can see that the status of the pod is terminating now. <br><br>

![Screenshot from 2023-06-08 21-22-05](https://github.com/vexecute/Cloud-Native-Web-App-Testing-Squid-VPN/assets/92919686/c334e1cf-0c6b-4fb4-b1f6-337ea01e0042) <br>
 
- automatically in the next step the app will create a container for another pre-existing pod to match the scale count. <br><br>

![Screenshot from 2023-06-08 21-25-24](https://github.com/vexecute/Cloud-Native-Web-App-Testing-Squid-VPN/assets/92919686/dfc65dcc-acf0-45d0-8d42-5beba42de6d2) <br>

- withing seconds the container is created for the process "squid-proxy-50489" and it is scaled now.<br><br>

**3) Using get-user command to check the privilege of the current user**<br><br>

![Screenshot from 2023-06-08 21-57-13](https://github.com/vexecute/Cloud-Native-Web-App-Testing-Squid-VPN/assets/92919686/946ba358-6120-49b8-b379-4e4897a9ab60) <br><br>


## What is understood from the above process?

- first, we can see that the application is **"Redundant"**, which means there is plenty of pods that can be scaled even if any one pod is terminated/killed.<br>
- second, the application automatically recovered from the failure/termination of a pod and the service was again made available within seconds (without human/manual intervention). Thus it is understood that the app is **"Resilient"**.<br>
- third, is the least privilege access, when I use command **"get-user pod[NAME]"** you can see that the command **"whoami"** prints the current user's name as **"squid user"**, which means that the root user is not performing this task and here the least privilige user is considered as the squid user.
 
## Redundancy

Redundancy is an important characteristic of cloud-native applications. It ensures that the application continues to function even if instances (VMs or containers) are terminated or fail. In this project, you can test the redundancy of the Squid VPN Web Application by killing an instance while it's running and checking if the application still provides service. The application should be able to recover and continue serving traffic without human intervention.

## Resiliency

Resiliency is another critical aspect of cloud-native applications. It focuses on the ability of the application to recover from failures automatically. In this project, you can assess the resiliency of the Squid VPN Web Application by killing an instance while it's running and observing if the instance (VM or container) restarts and continues to provide service without requiring manual intervention. A resilient application should be able to handle failures gracefully and maintain service availability.

## Least Privilege

Least privilege is a security principle that restricts access rights for users and processes to only the necessary resources. Cloud-native applications should not run with administrative or root-level access unless absolutely required. In this project, you can check if the Squid VPN Web Application adheres to the principle of least privilege by examining the user privilege of the account running on the target Squid Server pod. The application should use a dedicated user with limited privileges specific to running the Squid proxy application and nothing else.

## Installation

**To run this application in your system you can follow the following steps.**<br><br>

Step 1. Install python.<br>
Step 2. `git clone https://github.com/vexecute/Cloud-Native-Web-App-Testing-Squid-VPN.git`<br>
Step 3. `python cloud-app.py` <br>

## Usage

To use this application, follow these steps:

1. Ensure that Python is installed on your system.
2. Run the `cloud-app.py` script using the following command:
3. The application will display a list of supported commands and usage information.
4. Enter commands to interact with the Squid VPN Web Application. Available commands include:
- `help`: Prints out the list of supported commands
- `status`: Prints the status of the application
- `web`: Simulate the application's status web page HTML
- `kill [POD_NAME]`: Simulate killing off a pod with the given [POD_NAME]
- `scale [NUMBER]`: Simulate autoscaling the application to run with the specified number of pods
- `get-user [POD_NAME]`: Simulate checking the privilege of the user account running on the target Squid Server pod
- `quit`: Terminate the program


you can explore the commands listed above and test different aspects of the application.




