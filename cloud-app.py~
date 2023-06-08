#!/usr/bin/env python
# encoding: utf-8

"""
  This is a simple python script to simulate testing whether a web app is cloud-native
  Well-written Cloud native apps exhibit characteristics like redundancy,
  resiliency, and runs with least privilege.

    Redundancy: Kill an instance (VM or Container) of the App while it's running
    , and check if the App continues to work & provide service

    Resiliency: Kill an instance (VM or Container) of the App while it's running
    , and check if the instance (VM or Container) restarts/recovers with no
    human intervention, and continues to provide service

    Least-Privilege: Check if the App is not using admin or root level access
"""

import cac


""" Main program. """

# initial user prompt and usage information
cac.printCommandList(True)

print("Initializing application...")

# initialize app for simulation.
app = cac.initWebApp()

# continously take user commands.
user_input = input("Please type a command: (e.g. 'help')\n");

try:
  while user_input != 'quit':
    output = cac.parseUserInput(user_input, app)
    user_input = input("Please type a command: (e.g. 'help')\n")
except KeyboardInterrupt:
  pass

print("Program terminating...")
