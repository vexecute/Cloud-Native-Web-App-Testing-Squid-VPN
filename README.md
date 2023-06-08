# Cloud-Native-Web-App-Testing-Squid-VPN
Cloud-native web app assessment and simulation tool for testing redundancy, resiliency, and least privilege of a Squid VPN server.


# Squid VPN Web Application

This project simulates testing a Squid VPN Web Application to evaluate its cloud-native characteristics. The application is designed to exhibit traits like redundancy, resiliency, and least privilege. It provides functionality for managing pods, scaling the application, checking status, and testing user privileges.

## Redundancy

Redundancy is an important characteristic of cloud-native applications. It ensures that the application continues to function even if instances (VMs or containers) are terminated or fail. In this project, you can test the redundancy of the Squid VPN Web Application by killing an instance while it's running and checking if the application still provides service. The application should be able to recover and continue serving traffic without human intervention.

## Resiliency

Resiliency is another critical aspect of cloud-native applications. It focuses on the ability of the application to recover from failures automatically. In this project, you can assess the resiliency of the Squid VPN Web Application by killing an instance while it's running and observing if the instance (VM or container) restarts and continues to provide service without requiring manual intervention. A resilient application should be able to handle failures gracefully and maintain service availability.

## Least Privilege

Least privilege is a security principle that restricts access rights for users and processes to only the necessary resources. Cloud-native applications should not run with administrative or root-level access unless absolutely required. In this project, you can check if the Squid VPN Web Application adheres to the principle of least privilege by examining the user privilege of the account running on the target Squid Server pod. The application should use a dedicated user with limited privileges specific to running the Squid proxy application and nothing else.

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

you can explore and test different aspects of the Squid VPN Web Application using the provided commands.




