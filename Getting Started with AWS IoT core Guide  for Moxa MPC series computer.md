# Getting Started with AWS IoT core Guide  for Moxa MPC series computer

# Document Information

## Revision History (Version, Date, Description of change)

| Version | Date        | Description of change |
| ------- | ----------- | --------------------- |
| 1       | 2021/04/19 | First release         |
|         |             |                       |

# Overview

Moxa's industrial-grade panel computers and displays are built to withstand the elements, and feature a ruggedized design that makes them ideal for HMI applications in outdoor, hazardous, and marine environments. Certifications include C1D2 and ATEX Zone 2, and marine standards such as DNV GL and CCS.

# Hardware Description

## DataSheet

Please based on the product series you purchased, click the link below accordingly.

**[MPC-2070 Series](https://www.moxa.com/products/industrial-computing/panel-computers-and-displays/mpc-2070-series)**

**[MPC-2101 Series](https://www.moxa.com/products/industrial-computing/panel-computers-and-displays/mpc-2101-series)**

**[MPC-2120 Series](https://www.moxa.com/products/industrial-computing/panel-computers-and-displays/mpc-2120-series)**

**[MPC-2121 Series](https://www.moxa.com/products/industrial-computing/panel-computers-and-displays/mpc-2121-series)**

For more information, visit our [Rugged HMI](https://www.moxa.com/ruggedhmi) portal site.

## Standard Kit Contents

The standard shipping Moxa MPC series computer package contains the following items:
**For MPC-2070/MPC-2120,**
- 1 x MPC-2070/MPC-2120 Series computer
- 8 x screw, for panel-mounting
- 1 x terminal block, 2-pin (for DC power input)
- 1 x terminal block, 10-pin (for DIO)
- 1 x terminal block, 2-pin for remote power switch
- 1 x Quick installation guide (printed)
- 1 x Warranty card

**For MPC-2101/MPC-2121**
- 1 x MPC-2101/MPC-2121 Series computer
- 1 x terminal block, 2-pin (for DC power input)
- 6 x screw, for panel-mounting
- 1 x M12 phone jack power cable
- 1 x M12 Type-A USB cable
- 1 x Quick installation guide (printed)
- 1 x Warranty card


## User Provided items

To setup and operate Moxa computer, users have to prepare the following items by themselves.

- 100/1000M Ethernet cables
- VDC Power source: 10 to 36 VDC

## 3rd Party purchasable items

N/A

# Set up your hardware

- **Powering on Moxa MPC series computer :**

    **For MPC-2070/MPC-2120,** these two models use a DC power input. To connect the power source to the 2-pin terminal block, use a 60 W power adapter. The terminal block is available in the accessories package. The DC pin assignments are show in the figure.

    ![images/Untitled.png](images
         

    **For MPC-2101/MPC-2121**, these two models can be supplied power through a DC power input using an M12 connector. The DC pin assignments are as shown in the following figure:

    ![images/Untitled%201.png](images/Untitled%201.png)

    ![images/Untitled%202.png](images/Untitled%202.png)

      It takes around 30 seconds for the system to boot up.

- **Accessing Moxa MPC computer Using a Linux/Windows PC or Mac**

    You can use a PC to access Moxa MPC computer by u**sing SSH over the network. Refer to the following IP addresses and login information:**

![images/image2.png](images/image2.png)

Login: moxa

Password: moxa

Root account login is disabled until you manually create a password for the account. The user moxa is in the sudo group so you can operate system level commands with this user using the sudo command.

**ATTENTION: For security reasons, we recommend that you disable the default user account and create your own user accounts or** 

Refer to System configuration of M[oxa MPC-2000 series computer-linux-user-manual for the d](https://www.moxa.com/getmedia/3564ac25-7fe4-42bc-8b20-c3463dcfd592/moxa-mpc-2070-series-manual-v1.0.pdf)etail steps.

- **Change the network settings of Moxa MPC-2000 series computer based on your network environment**

    Refer to the Configuring network settings  of M[oxa MPC-2000 series computer-linux-user-manual](https://www.moxa.com/getmedia/3564ac25-7fe4-42bc-8b20-c3463dcfd592/moxa-mpc-2070-series-manual-v1.0.pdf) for the detail steps.

# Set up your Development Environment

## Tools Installation (IDEs, Toolchains, SDKs)

The operation system of MPC-2070/2120-LX OR MPC-2101/2121-LX is a native 64-bits X86 Linux operating system. There is no need to install toolchains. You can install development tools in Moxa MPC computer directly.

Follow these steps to update the package menu:

1. Make sure a network connection is available.

2. Use apt-get update to update the Debian package list.

```bash
moxa@Moxa:~$ sudo apt-get update
```

3. Install the native compiler and necessary packages.

```bash
moxa@Moxa:~$ sudo apt-get install gcc build-essential flex bison automake
```

# Setup your AWS account and Permissions

Refer to the instructions at [Set up your AWS Account](https://docs.aws.amazon.com/iot/latest/developerguide/setting-up.html). Follow the steps outlined in these sections to create your account and a user and get started:

- Sign up for an AWS account and
- Create a user and grant permissions.
- Open the AWS IoT console

Pay special attention to the Notes.

# Create Resources in AWS IoT

Refer to the instructions at [Create AWS IoT Resources](https://docs.aws.amazon.com/iot/latest/developerguide/create-iot-resources.html). Follow the steps outlined in these sections to provision resources for your Moxa MPC computer:

- Create an AWS IoT Policy
- Create a thing object

Pay special attention to the Notes.

> **Important**
Before you continue to the next step, your Moxa computer must be configured, and running. The Moxa computer must be connected to the Internet and you will need to be able to access the computer by using its command line interface. Command line access can be through SSH terminal remote interface.

# Build the demo

Follow above section, **Accessing Moxa MPC computer Using a Linux/Windows PC or Mac,** using PuTTY to open a remote terminal to Moxa MPC computer on **Linux/Windows PC or Mac** and perform the following instructions in that window. 

Refer to the instruction at [Install the required tools and libraries for the AWS IoT Device SDK](https://docs.aws.amazon.com/iot/latest/developerguide/connecting-to-existing-device.html#gs-device-sdk-tools) and [Install AWS IoT Device SDK](https://docs.aws.amazon.com/iot/latest/developerguide/connecting-to-existing-device.html#gs-device-install-sdk) for Python on Moxa MPC computer directly. Follow the steps outlined in these sections to install AWS IoT Device SDK for your Moxa computer:

- Update the operating system and install required libraries
- Install git
- Install the AWS IoT Device SDK for Python.

Note: Due to using Python, there is no need to compile/build any programs. And we perform all steps in Moxa MPC computer, there is no need to load/upload any programs to it.

# Run the demo

Continue previous section, perform the instructions, [Install and run the sample app](https://docs.aws.amazon.com/iot/latest/developerguide/connecting-to-existing-device.html#gs-device-node-app-run), in that terminal window. 

To view the MQTT messages published by the sample app in the AWS IoT console, perform the instructions,[View messages from the sample app in the AWS IoT console](https://docs.aws.amazon.com/iot/latest/developerguide/connecting-to-existing-device.html#gs-device-view-msg).

# Debugging

1. Not able to login Moxa MPC computer's through SSH terminal.

    Use MPC's panel to identify the issues. Once the system is ready, a XFCE desktop screen will appear on MPC's panel. Refer to Getting Started of [Moxa MPC-2000 series computer-linux-user-manual](https://www.moxa.com/getmedia/3564ac25-7fe4-42bc-8b20-c3463dcfd592/moxa-mpc-2070-series-manual-v1.0.pdf) for the detail steps. After login Moxa computer check following items:

    a. Check if IP address of LAN1/LAN2 is in the same subnet of your PC.

    b. Check if you are able to operate OS normally. If not, gather all error message when you operate OS and then [CONTACT US](https://www.moxa.com/en/support/technical-support)

2. Moxa computer is not able to access internet.

    a. Check if IP address, mask and gateway of LAN1/LAN2 are configured in /etc/network/interfaces properly.

    b. Check if routing is correct.

    c. Check if nameserver is configured in /etc/resolv.conf

# Troubleshooting

Still need assistance with your Moxa product? [CONTACT US](https://www.moxa.com/en/support/technical-support)